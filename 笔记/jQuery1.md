# jQuery

## 一.jQuery是什么

<u>一个优秀的js函数库</u>

## 二.基本使用

### 1.安装

cdn引入 

npm node -i jQuery

官网下载

### 2.引入js库

<script type ="text/JavaScript" src ="js/jquery.js"></script>

## 三.jQuery函数

### 1.核心函数

`$(param)`

1.1参数为 元素 ,选择器 查找 并把他们封装成jQuery对象

1.2参数为函数 执行回调

1.3 DOM对象 将dom对象封装成jQuery对象

1.4参数html 创建标签对象封装成jQuery对象

```
$(function(){//绑定文档加载完的监听
    $('#btn1').click(function(){
        console.log(1)
    }) 
})
```

```
$(function(){
    $('#btn1').click(function(){
       console.log(this.innerText) //这个this是dom元素
      
      $('<input type="text">').appendTo('div')
       console.log("++"+$.trim("   w i   " ))
       $('button').each(function(index,element){
        console.log(index)
        console.log(element)
       })
       
    }) 
})
```

`$(this).html()`只有包装才能使用对象的方法,老是强调读写合一,这里即是读,如何去写 ? 则为 `传参`



## 四.jQuery对象

<u>执行jQuery函数返回的对象</u>

`$(params)包含dom元素对象的伪数组.xxx()`并封装成数组对象返回

### 1.基本特征

1.size()/length

`原因：jquery1.8后废弃了size() 用length代替。引用的 [jquery]版本在 是废除了 .size()之后的版本。`

2.each()

```
 $('button').each(function(index,ele){
        console.log(index)
        console.log(ele)
    })
```

3.[index]/get(index)

`console.log($('button').get(1))`

4.index(selector/element)

 `console.log($('button').index($('#btn3')))`

## 五.使用jQuery核心函数

### 1.选择器

有特定规则的字符串

<u>就是css的选择器语法规则并进行扩展</u>

#### 1.基本选择器

<u>元素类,id通配符,并集,交集\</u>

#### 2.层次选择器

查找子后代兄弟

后代

```
$('ul span')
```

子代

```
$('ul >span')
```

兄弟

```
$('.box+li')一个
```

```
$('.box~li')所有
```



#### 3.过滤选择器

```
$('.div:first')
$('.div:last')
$('.div:not(.box)')//不是box的div
$('.div:gt(0):it(2)')大于0小于3 //多个选择器是依次执行的
$('div:contains(johon)')//查内部text
$('div[id]')//有id的div
$('div[id=hello]') //id等于hello的div
```

#### 4.表单选择器

```
$(div:input)//建议看文档
$(:input:disabled)

```

## 六.工具方法

```
$.each()
//$.each([1,2,3],function(i , n){
//
//})
$.trim()//去除左右两端的空格
$.type()
$.isArray()
$.isFunction()

$.parseJSON() //解析JSON字符串
$.parseJSON('{"name":"jhon"}')

$.extend() //合并对象
//$.extend({},{})
//不修改默认 
var empty = {};
var defaults = { validate: false, limit: 5, name: "foo" };
var options = { validate: true, name: "bar" };
var settings = jQuery.extend(empty, defaults, options);
$.grep()//过滤数组使用过滤函数
//$.grep([0,1,2],function(n,i){ return n>0})
```

```
$.inArray('我',arr) //确认一个参数是否在数组里
$.toArray()//把dom元素集合转为数组
//$('li').toArray()
$.unique()//删除数组中重复元素,只处理删除DOM元素数组，而不能处理字符串或者数字数组。
//$.unique(document.getelementbytagname('div'))

$.merge([],[])数组合并 不会去重 ,合并会改变第一个数组的值

$.map()数组扩展
//$.map(arr , function(n){ return n +1})
```

```
$.noop()//传递一个空函数
$.proxy()//强制转换函数作用域 
//$.proxy(x,y) x =function  y= obj
$.when()?异步同步
$.param()?序列化
```

```
$.contains() //判断一个dom节点是否包含另一个dom

```


```
选择块函数
$(function(){
    let $list1 = $('.top > li')
    let $buttom = $('.buttom >li')
   $list1.click(function(){
    $buttom.css("display","none")
    let index = $(this).index()
    $buttom[index].style.display='flex'
   })
})
```

```
选择块后一个隐藏前一个
$(function(){
    let currindex  =0;
    let $list1 = $('.top > li')
    let $buttom = $('.buttom >li')
   $list1.click(function(){
    $buttom[currindex].style.display='none'
    let index = $(this).index()
    $buttom[index].style.display='flex'
    currindex=index
   })
})
```

## 七.属性

`attr`添加属性 <u>操作属性值为非布尔值</u>

`$("img").attr({ src: "test.jpg", alt: "Test Image" });`

`removeAttr`移除属性

`$("img").removeAttr("src");`

`addClass`追加类

`removeClass`移除类

`html()`html操作 innerhtml相似

`text`text innertext相似

`val()`value相似

`prop` 添加属性 <u>操作属性值布尔型</u>

`removeprop`

## 八.css

### 1..css的使用

```
$('p').css('color')
$('p').css('color','blue')
$('p'.css(function(i,value){
return
})
```

### 2.offset与position

1.offset获取相对偏移(当前文档)

```
var p = $("p:last");
var offset = p.offset();
p.html( "left: " + offset.left + ", top: " + offset.top );

//传入参数是设置坐标
$("p:last").offset({left:10,top:20})
```

2.position获取相对偏移(父元素)

```
var p = $("p:laast");
var position = p.position
p.html("left"+position.left +"top"+position.top)
```

### 3.scrolltop与scrollleft

scrollTop读取/设置滚动条的坐标

```
//读取
var p = $("p:first");
$("p:last").text( "scrollTop:" + p.scrollTop() );
//设置
$("div.demo").scrollTop(300);

经典案例
$(function(){
   $('.top1').click(function(){
    let allLength = $('html').scrollTop()
    console.log(allLength)
    let timer = 500
    let intancesTimer = 10
    let intance = allLength/(timer/intancesTimer)
    
   let interval =  setInterval(() => {
       allLength -= intance
       if(allLength<=0){
        allLength = 0;
        clearInterval(interval);
       }
        $('html').scrollTop(allLength)
    }, intancesTimer);
   })
})
```

### 4.元素的尺寸

1.尺寸

`$('div:last>li').width(),$('div').height()`

2.内部尺寸(+padding)

`$(div:first>li).innerWidth(),$(div:first>li).innerHeight()`

3.外部尺寸(+margin+border)

`$(div:first>li).outerWidth(),$(div:first>li).outerHeight()`

## 九.筛选

### 1筛选(jQuery对象的返回)

过滤是和原有

```
$lis.eq(1)
    console.log($('.buttom>li').eq(0)) //返回jQuery对象可以使用jq的方法
    console.log($('.buttom>li')[0])    //返回dom对象可以使用dom的方法
$lis.first()
$lis.last()
$lis.filter('[title=hello]') //属性等于hello
$lis.not('[title=hello]') //属性不为hello
$lis.has('span') // 有span的li
.hasClass()//类是否存在
.is()判断是否在一个给定表达式

//取反,提交勾选表单
$(function(){
    
   $('button').eq(0).click(function(){
   $('input').prop('checked',true)
   })
   $('button').eq(1).click(function(){
    $('input').prop('checked' ,false)
    })
    //原生取反
    $('button').eq(2).click(function(){
      $('input').each(function(){
        this.checked = !this.checked
      })
    $('#cheackall').prop('checked',$('input').not(':checked').length ===0)
        })
    $('button').eq(3).click(function(){
           $('input').filter(':checked').each(function(){
            alert(this.value)
           })
    })
    $('#cheackall').click(function(){
        $('input').prop('checked',this.checked)
    })
    $('input').click(function(){
        console.log($('input').not(':checked').length ===1)
        $('#cheackall').prop('checked',$('input').not(':checked').length ===1)
    })
})
```

### 2.查找

.查找是与后代,兄弟 ,父代

```
.children()//查子元素
//console.log($('.buttom').children('li:first').html())
.find()//查后代元素
.parent()//查父元素
.prevall()//查前面所有的 .prev()
.siblings()//查所有兄弟元素
```

## 十.文档处理
### 1.增删改

```
.append()//内部插入最后
$("p").append("<b>Hello</b>");
.appendTo()//内部插入 
$("<b>Hello</b>").appendTo("p")
.prepend()//内部插入最前
.prependto()//
.before() //外部插入 (在前面)
$uli.children('li[title = hello]').before()
.after() // 外部插入(在之后)
.replacewith() //按照代码替换
$("p").replaceWith("<b>Paragraph. </b>");
.replaceall()//按照选择器替换
$("<b>Paragraph. </b>").replaceAll("p");

$('ul').remove() //删除的是ul
$('ul').empty() //把ul转空 删除的是li

```
正删改经典案例

```
$(function(){
  $('button').click(function(){
    $(`<tr>
    <th>`+$('input').eq(0).val()+`</th>
    <th>`+$('input').eq(1).val()+`</th>
    <th>`+$('input').eq(2).val()+`</th>
    <th><a href="javascript:;">Delete</a></th>
    </tr>`)
    .appendTo('table')
    .find('a').click(Onki)
    
  })
  
  $('a').click(Onki)
 function Onki (){
    if(confirm()){
    $(this).parent().parent().remove()
    }
  }

})

```



### 2.包裹

?

## 十一.事件

### 1.事件绑定

`页面完成时读取 $(function(){})`

<u>点击监听</u>1.`.click()`2 `.on()` *在选择元素上绑定一个或多个事件的事件处理函数* 3. `.bind`

```
 $('#foo').bind('mouseenter mouseleave', function() {
  $(this).toggleClass('entered');
});多绑一
$("button").bind({
  click:function(){$("p").slideToggle();},
  mouseover:function(){$("body").css("background-color","red");},  
  mouseout:function(){$("body").css("background-color","#FFFFFF");}  
});一绑一
function handler(event) {
  alert(event.data.foo);
}
$("p").bind("click", {foo: "bar"}, handler)
附加数据,传值给function

取消默认行为 阻止事件气泡 //往函数里放
```



```
$('out').on('click',function(){})
```

鼠标事件1.鼠标进入 `.mouseenter` 2.鼠标离开`.mouseleave` 3.`.hover(fn,fn)` 4. `.mousedown`鼠标按下事件 5.鼠标移动事件 `.mousemove`

6.鼠标在元素上离开 `.mouseout`*与 mouseleave 事件不同，不论鼠标指针离开被选元素还是任何子元素，都会触发 mouseout 事件。只有在鼠标指针离开被选元素时，才会触发 mouseleave* 事件

7.鼠标在元素上方 `.mouseover`

一次性绑定 `.one('有效事件',function(){})`

双击事件绑定 1.`.dblclick`

焦点事件 1.`.focus`2.`.focusin`可以在父元素上检查子元素是否获得焦点

失去焦点事件 `.focusout`

键盘事件1.keydown 2.keypress3.keyup

滚动事件 1.`scroll` 用户滚动指定的元素时，会发生 scroll 事件。

离开页面事件 1.`unload`用户离开页面发生的事件

文本选择事件 1.`select`当 textarea 或文本类型的 input 元素中的文本被选择时，会发生 select 事件。



### 2.事件解绑

*解除事件监听* 1.`.off`解除所有监听 ;解除指定事件名的监听; 2. `.unbind` 解除所有监听 ;解除指定事件名的监听;解除指定事件的函数

```
$("p").bind("click", foo);
```

阻止事件冒泡:`event.stopPropagation()`

阻止事件默认行为: `event.preventDefault`

### 3.事件委托

将多个子元素的事件监听委托交给父元素处理

对子元素操作的时候,事件会冒泡到父元素

父元素不会直接处理事件,根据event.target得到发生事件的子元素, 通过这个子元素调用这个回调函数

`delegate`

```
 $('table').delegate('a','click',function(){
    console.log(this)
    if(confirm()){
          $(this).parent().parent().remove()
         }
  })
  $('button').click(function(){
    $(`<tr>
    <th>`+$('input').eq(0).val()+`</th>
    <th>`+$('input').eq(1).val()+`</th>
    <th>`+$('input').eq(2).val()+`</th>
    <th><a href="javascript:;">Delete</a></th>
    </tr>`)
    .appendTo('table')
   添加一个新的tr,为了给新的a添加监听 我们给予a委托事件,委托的的父元素必须与添加的父元素一致
    
  })
```

`undelegate`

```
$('table').undelegate('click')
```



### 4.事件的坐标

event.clientX ,event.clientY相对于视口

event.pageX 相对于页面

event.offsetX 相对于事件元素

## 十二.效果与内置动画

### 1.淡入淡出

`fadeIn`(slow/normal/fast/time,function(){})

带动画显示

`fadeOut`

带动画的隐藏

`fadeToggle`

隐藏显示



### 2.滑动

sildedown

动画展开

slideup

动画收缩

slidetoggle

展开/收缩

### 3.显示与隐藏

显示show() 隐藏 hide() toggle()

### 4.自定义动画

`animate`

```
.animate({width:100px,height:200},1000)
```

`stop`

停止动画

`delay`延迟动画队列

```
$('#foo').slideUp(300).delay(800).fadeIn(400);
```

## 十三.多库共存

```
api:jQuery.noConflict()
```

如果有两个库都有$,就存在冲突

在一个引入了jQuery库的项目中，又引入了含有$变量的其他第三方库，导致了第三方库的$不可用

释放$的使用权,让另一个库可以正常使用,然后使用jQuery

## 十四.jQuery插件

### 1.自定义

函数扩展

在jquery添加新函数

```
jQuery.extend({
  min: function(a, b) { return a < b ? a : b; },
  max: function(a, b) { return a > b ? a : b; }
});
jQuery.min(2,3); // => 2
jQuery.max(4,5); // => 5
```

扩展 jQuery 元素集来提供新的方法

```
jQuery.fn.extend({
  check: function() {
    return this.each(function() { this.checked = true; });
  },
  uncheck: function() {
    return this.each(function() { this.checked = false; });
  }
});
```

### 2.laydate库

![image-20230926151038922](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230926151038922.png)

```
laydate.render({ 
  elem: '#test' //或 elem: document.getElementById('test')、elem: lay('#test') 等
});详情请见官方文档//https://layuiweb.com/doc/modules/laydate.html
```

### 3.easyUI

?

### 4.jQueryui

1.2mb
