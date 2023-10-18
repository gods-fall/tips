# Sass

## 1.安装使用 

<u>编译</u>(看起来很麻烦,也许是特殊场景)

<u>live插件安装</u>编译 

### 1.<u>node sass 模块</u> 

`npm install -g node-sass`

## 2.变量使用

*sass使用$标识变量*  变量支持块级作用域，不在嵌套规则内定义的变量则可在任何地方使用（全局变量）。将局部变量转换为全局变量可以添加 `!global` 

`$color:#f90`



```scss
#main {
  $width: 5em !global;
  width: $width;
}
```

### 1.数据类型 

maps  ky键值对 相当于js的obj

数组 (list)，用空格或逗号作分隔符，`1.5em 1em 0 2em, Helvetica, Arial, sans-serif`

其他正常

### 2.数据运算

```
 font: #{$font-size}/#{$line-height};
```

3.函数与关键词参数

4.差值语句

```
$name: foo;
$attr: border;
p.#{$name} {
  #{$attr}-color: blue;
}
```

