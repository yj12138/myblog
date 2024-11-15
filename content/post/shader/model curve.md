+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= '模型曲面'
+++

```HLSL
Shader "Custom/Curved" {
	Properties {
		_MainTex ("Base (RGB)", 2D) = "white" {}
		_QOffset ("Offset", Vector) = (0,0,0,0)
		_Brightness ("Brightness", Float) = 0.0
		_Dist ("Distance", Float) = 100.0
	}

	SubShader {
		Tags { "Queue" = "Transparent"}
		Pass
		{

	        Blend SrcAlpha OneMinusSrcAlpha
			CGPROGRAM
			#pragma vertex vert
			#pragma fragment frag
            #pragma multi_compile __ CURVED_ON

			#include "UnityCG.cginc"

            sampler2D _MainTex;
			float4 _QOffset;
			float _Dist;
			float _Brightness;

			struct v2f {
			    float4 pos : SV_POSITION;
			    float4 uv : TEXCOORD0;
			    float3 viewDir : TEXCOORD1;
			    fixed4 color : COLOR;
			};

			v2f vert (appdata_full v)
			{
			   v2f o;
			   UNITY_INITIALIZE_OUTPUT(v2f,o);
            //    模型 -> 视图
			//    float4 vPos = mul (UNITY_MATRIX_MV, v.vertex);
               float3 vPos = UnityObjectToViewPos(v.vertex);
            //    弯曲模型
        #ifdef CURVED_ON
			   float zOff = vPos.z/_Dist;
			   vPos += _QOffset*zOff*zOff;
        #endif
            // 视图-> 裁剪
			//    o.pos = mul (UNITY_MATRIX_P, vPos);
			   o.pos = UnityViewToClipPos(vPos);
			   o.uv = v.texcoord;
			   return o;
			}
			half4 frag (v2f i) : COLOR0
			{
			  	half4 col = tex2D(_MainTex, i.uv.xy);
			  	col *= UNITY_LIGHTMODEL_AMBIENT*_Brightness;
				return col;
			}
			ENDCG
		}
	}

	FallBack "Diffuse"
}
```
