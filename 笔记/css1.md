css层叠样式表

<style>
    h1 {
        color:
        font-size:
    }
</style>

外部样式

样式  关联



<link rel = "stylesheet" href="">

行内 优先 大于外内部优先

内部样式=外部样式优先级 看顺序

选择器 找到要添加样式的元素

声明块 声明

选择器 {:  ;}

/**/

通配选择器

*{}

元素选择器

h2 {}

类选择器

添加class=""名

写选择器 

.class名{}

一个标签不能写很多个class属性但是可以写有很多class值,不能使用纯数字

id选择器

添加id 

写选择器

#id名{} 不能是数字开头一个元素可以有class和id  多元素 id 不能相同

复合选择器

交集选择器

且 紧紧连着 

p.bea 元素必须开头 .bea.bea

并集选择器

或,

父元素 直接包裹某个元素的元素

祖先元素 父亲的父亲

后代元素

兄弟元素具有相同父元素的元素

后代选择器

ul  li {}

ul li a {}

类的儿子



子代选择器

div >a

div>p>a

类的子代

兄弟选择器

div +p {} 紧紧相邻的向下

通用

div~p{}所有的 向下







属性选择器

[title]{}属性

属性和值

^="a"开头

$=""结尾

*=""有



伪类选择器

a:link{}

a:visited{}

动态伪类

a:hover

a:active

input:focus

结构伪类

:first-child

:last-child

:nth-child(n) 2n 0开始 an+b

first-of-type

last

nth

否定伪类

:not(){}

ui伪类

:checked

:disabled

目标伪类

:target{}

语言伪类

:lang()

伪元素

div::first-letter

first-line

selection

placeholder

before{

content :}

after

优先级

id>类 > 元素>通配

权重

a id b class 伪类 属性 c元素 伪元素

三大特性 

层叠性 继承性 优先级

并集选择器是分开算的

属性

颜色 rgba  hexa # 00-0f  

字体

font-size3px

字体族 

font-family :

斜体

font-style : normal  italic

字体粗细

font -weight :lighter normal bold 数值

复合

font:  bold 100px  "字体族"

文本颜色

color:

文本间距

letter-spacing:

文本修饰

text-decoration:; overline  underline line-through none   dotted虚线 wavy波浪线   

文本缩进

text-indent :

文本对齐 

水平

text-align: left center right 

行高

line-height:

1.5

垂直

height = line - height单行文字

vertical-align:  baseline  middle

列表

list-style-type: 列表符号

list-style-position: 位置

list-style-image: 自定义 符号

复合

list-style::

表格

边框

table {

border-width :

border-color:

border-style: solid /dash  /dott/inset

复合 border 





控制列宽

table-layout fixed  /

控制单元格间距

border-spacing:1px

合并相邻单元格边框

border-collapse: separate/collapse

隐藏没有内容的单元格

empty-cells: show/ hide



背景

background-color: transparent透明色

background-image:url:();

设置背景的重复方式

bg-repeat:no-repeat   repeat-x  y;

控制背景的位置

background-position: left  top   /  bottom/center/  水平 垂直

​									: 10px 20px;

背景模糊

backdrop-filter:blur()



复合

background:

鼠标

cursor:move;wait url:(),pointer;

长度单位

rem % em font-size倍数



块元素 行内块元素(可以通过css控制)   行内元素

![image-20230712174745506](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230712174745506.png)

修改元素显示

display:  block/inline-block/inline;

盒子模型

内容区 content

父容器

min-width

max-width

min -height

max-height

 

内边距padding

padding-left /right/top/bottom

边框border

border-color 

border-style 

border-width  /*left   */



border-left /right /top/bottom

外边距margin

margin- left

margin-right

margin-top

margin-bottom

margin:100px auto;

还能是赋值

塌陷

子元素的top和bottom被父元素抢走

加边框

加padding

overflow:hidden 溢出隐藏

合并

上下存在 

浮动 float 开白

溢出

overflow:hide/auto/visable

over-flow-x 

​               -y难崩

元素的显示与隐藏

visibility:hidden 占位

display:none 不占位

body有8px外边距

行内块幽灵空白

vdikoualign

浮动

float:left/ right

浮动的影响

父 后

解决

父元素的高度

后面元素 行内块

clear:left/right 清除浮动影响 /both

![image-20230713103937059](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230713103937059.png)

定位

相对 相对发生位置变化之前 没有脱离文档流

position:relative

lrtb:

绝对定位 参考包含块

position:absolute

1没有脱离文档流的父元素

2脱离文档流的元素 第一个开启定位的祖先元素

固定

找视口视口是我爹

position:fixed

粘性

position:sticky;

top:/l/r/b

层级调整

z-index:

包含块的拖累

![image-20230713163600145](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230713163600145.png)

布局

版心

不给宽 

不给高960-1200

![image-20230713173150110](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230713173150110.png)

![image-20230713173926235](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230713173926235.png)

重置默认样式

reset.css

normalize



css3      caniuse

私有前缀 -xxx-

webkit moz

长度单位

vw   视口的百分之 宽

vh

盒子模型新争

box-sizing: content-box/border-box

resize:hor/ver/both 与   overflowhieden

box-shadow : 阴影   /水平 垂直 颜色\模糊程度/inset

opacity:0/1/0.5;

背景

background-origin: padding-box/content-box/border-box

设置背景图原点

background-clip:/text/

不可见/背景裁切

background-size:/contain/cover

多背景图

background:,

边框

圆角

border-radius:

border-top-left-radius:



![image-20230715131226082](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230715131226082.png)

文本阴影

text-shadow:

文本换行

white-space:/pre /pre-wrap/pre-line/nowrap强不换行

文本溢出

overflow:hidden

text-overflow: clip/ellipsis

文本修饰

text-decoration: overline dashed blue

文本描边

text-stroke: blue/color

渐变

线性渐变

background-image: linear-gradient(red,yellow,blue);

background-image: linear-gradient(to right top/20deg,red 100px,yellow,blue);

径向渐变

background-image: radial-gradient(red,yellow,blue);

background-image: radial-gradient(at right top/100px 50px/circle,red,yellow,blue);





重复渐变

没发生渐变区域发生渐变

基础

repeating-



web字体

@font-face{

font-family:"";

src:url()

}

字体图标

阿里图标库



2d变换

位移 参考自身

transform: translate x/y()

缩放 

transform: scale x/y();

旋转 绕着z轴旋转

:rotateZ deg

扭曲

skew xy deg

多重变换

:

变换原点 对位移无影响

transform-origin: left top/px px;

3d变换

空间与景深

transform-style: preserve-3d; 父类开启3d空间

perspective:; 500 -1200  800-1000

transform:rotateX();

透视点

perspective-orgin:100px 100px;



3d位移

z 和3d 



旋转3d

x y           3d

3d缩放

z

3d多重变换

origin

:



背部可见性

backface-visibility:

hidden



过渡

transition:;

transition-Property: height,w

设置过渡时间

transition-duration:;  s/ms 1,5



过渡的延词

-delay:2s;

过渡的效果 

transition-timing-function:ease/linear/ease-in/ease-out/ease-in-out/steps(1s,start/end)/

复合



css动画



animation-name: wangyoudong;

animation-duration:3s 持续时间

animation-delay:;   延词时间

animation-timing-function:

animation-iteration-count:3 播放次数infinite

-direction:normal/reverse/alternate动画的方向

-fill-mode:

-paly-state:

@keyframes name  {

from{}

to{}

}

0 25%    50%{}



多列布局

column-count:5直接指定列

-gap:50px

-rule-width/style/color

多列图片

column-count:5



伸缩盒模型

flexible box

容器 

display:flex; inline-flex

父元素开启flex 子元素会铺满父元素

伸缩项



主轴方向

flex-direction:row;/row-reverse/column

主轴侧轴换

flex-wrap:wrap;wrap-reverse

主轴对齐

justify-content:flex-start/flex-end/center/space-around/space-between/space-evenly

侧轴对齐

一行

align-items:flex -end/flex-start/center/stretch(无高)



多行

align-content:flex-start/flex-end/center/



水平垂直居中

妈妈sil

基准长度 狗屎

inner {

flex-basis:300px;}

![image-20230715194007546](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230715194007546.png)

伸

inner

flex-grow:1;/

缩

别换行

flex-shrink:1;

复合:

![image-20230715200358610](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230715200358610.png)

排序

inner2{order:-1;}

单独对齐

align-self: center



响应式布局

媒体查询

打印机

@media print/screen {



}

媒体特性

@media(max/min-width:800px){}

and/ ,/

常用雀值

![image-20230715203144310](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230715203144310.png)

object-fit css

![img](https://img-blog.csdnimg.cn/b13d8a6d157a4d759df040cb3997d8c8.png)f
