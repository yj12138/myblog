+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= 'React 基础'
+++

# React 语法

## Use Hook

### useState 状态数据绑定

```js
function MyButton() {
  const [count, SetCount] = useState(0);
  function ClickCB() {
    SetCount(count + 1);
  }
  return (
    <div>
      <Button onclick={ClickCB}> Click {count} </Button>{" "}
    </div>
  );
}
```

### useRef 控件绑定

```js
function VideoPlayer(){
    const videoRef = useRef(null)
    useEffect(()={
        videoRef.current.src = ""
    })
    return(
        <div>
        <Video ref={videoRef}>
        </div>
    )
}
```

### useEffect 渲染完成回调

```js
function Test() {
  const [count, SetCount] = useState(0);
  useEffect(() => {
    return () => {}; // 返回一个函数在销毁时回调
  }, [count]); // [] 只在渲染完成时回调，
  return <div></div>;
}
```
