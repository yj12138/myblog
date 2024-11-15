+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= '圆形范围圈'
+++

```glsl
Shader "Dawn/FlowDottedCircle"
{
    Properties
    {
        _Color("Color",color) = (1,1,1,1)   // 颜色
        _InnerRadius("InnerRadius",Range(0,0.5)) = 0.4  //内径
        _OuterRadius("OuterRadius",Range(0,0.5)) = 0.5  //外径
        _Speed("Speed",Range(0,1)) = 1.0    // 旋转速度
        _DottedNumber("DottedNumber",Range(10,100)) = 10  // 线段数
    }
    SubShader
    {
        Tags { "RenderType"="Transparent" "IgnoreProjector" = "True" "PreviewType" = "Plane"}
        LOD 200
        Cull Off
        Lighting Off
        ZWrite Off
        Blend SrcAlpha OneMinusSrcAlpha
        Pass
        {
            CGPROGRAM
            #pragma target 2.0
            #pragma vertex vert
            #pragma fragment frag
            struct appdata_t {
                float4 vertex : POSITION;
                fixed4 color : COLOR;
                float2 uv     : TEXCOORD0;
            };
            struct v2f {
                float4 vertex : SV_POSITION;
                float2 uv    : TEXCOORD0;
            };
            fixed4 _Color;
            float _InnerRadius;
            float _OuterRadius;
            float _Speed;
            float _DottedNumber;
            v2f vert(appdata_t i)
            {
                v2f o;
                o.vertex = UnityObjectToClipPos(i.vertex);
                o.uv = i.uv;
                return o;
            }
            fixed4 frag(v2f i) : SV_TARGET
            {
                fixed4 color =  _Color;
                float2 tempuv = i.uv - float2(0.5,0.5);
                float angle = _Time.y * _Speed;
                float2 rotuv = 0;
                rotuv.x = tempuv.x * cos(angle) - tempuv.y * sin(angle);
                rotuv.y = tempuv.x * sin(angle) + tempuv.y * cos(angle);
                tempuv = rotuv;
                float dis = distance(tempuv,float2(0,0));
                float d = step(_InnerRadius,dis) - step(_OuterRadius,dis);
                float pi = 3.1415926;
                float twopi = pi * 2;
                angle = atan2(tempuv.y,tempuv.x) + twopi;
                float angleSpace = 2 * pi / _DottedNumber;
                float temp = fmod(angle,angleSpace);
                temp = step(angleSpace,temp * 2);
                float alpha = color.a * d * temp;
                color.a = alpha;
                return color;
            }
            ENDCG
        }

    }
    // FallBack "Diffuse"
}
```
