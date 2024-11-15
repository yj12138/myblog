+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= '尺寸单位'
+++

## px

像素单位

## em

相对单位 相对于父元素

```css
div {
  font-size: 12px;
}
div > p {
  width: 10em; /* 结果为120px */
  height: 10em; /* 结果为120px */
}
```

## rem

相对单位 相对于 html 根元素

```CSS
html {
 font-size: 14px;
}
div {
 font-size: 12px;
}
div > p {
 width: 10rem;    /* 结果为140px */
 height: 10rem;   /* 结果为140px */
}
```
