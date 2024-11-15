+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= 'fx 反射框架'
+++

## import

```go
import "go.uber.org/fx"
```

## create options

### fx.Provide()

注册对象构造函数，以便在使用时创建对象引用加入到容器

### fx.Populate()

解引用，取出容器中的值

### fx.Invoke()

注册在启动之前调用的函数

```go
options = append(options,
    fx.NopLogger,
	    fx.Provide(
	    log.NewLogger,
	),
	fx.Populate(&dal.DB),
	fx.Populate(&eventBus),
	fx.Invoke(
	listener.NewStartListener,
	),
)
```

## 创建 App

```go
app := fx.New(options)
```

## 启动

```go
if err := app.Start(context.Background()); err != nil {
    panic(err)
}
```

## 结束

```go
<-app.Done()
```
