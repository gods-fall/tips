# less

只给我们的相遇

## 一.安装

安装我认为是老一套, 两种方法,1.npm `node i -g less`2.cdn引入

## 二.概念

一门向后兼容的css扩展语言,好学,

## 三.变量

### 1.把常用值变公共

```
@link-color:#ffffff
//1.变量控制属性值
.link {
color:@link-color;
}
2.变量差值
@public-class:banner
//控制类名
.@{public-class} {
}
@public-imageURL: "../image"
//控制路径地址
image {
background:url({@public-imageURL}/xxx/xx.jpg)
}
@public-color:color
image {
{@public-color}:#ffffff
}
3.变量变量
@public: #ffffff
.seetion {
	@color:@public
	.hello {
		color:@@color
	}
}

4.惰性求值
变量在使用之前不必声明
image {
color:@public
}
@color:@let
@let:#ffffff
当定义一个变量两次时，使用变量的最后一个定义，从当前范围向上搜索。这类似于 css 本身，其中定义中的最后一个属性用于确定值。

```

### 2.属性能做变量

```
.weight {
color:#ffffff
background-color:$color
}
```

## 三.父选择器

```
&:hover {
//老生常谈nth-child(2n+1)
}

.button {
&-ok {}
//2.我觉得这个还不错
}
.button-ok {
  background-image: url("ok.png");
}
.button-cancel {
  background-image: url("cancel.png");
}
.button-custom {
  background-image: url("custom.png");
}
&可以表示所有父选择器


```

## 四.扩展