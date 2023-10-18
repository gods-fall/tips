# es6

## 1.啥东西干啥的

ecmascript

## 2.let

let特性:

1.变量不能重复声明

2.块级作用域  

```
变量只是在代码作用域里面有效
作用域分为,全局,函数
```

3.不存在变量提升

```
什么是变量提升 
console.log(song);
输出undefined,不会报错
var song = '变量提升'
使用let会直接报错 let不允许变量提升
```

4.不影响作用域链

```
{
	let school = '尚硅谷'
	function fn(){
	console.log(school)该作用域里不存在school变量所以要去上去上级作用域找
	}
}
```

与var相比:var全局作用域

```


for(var i =0;i<items.length;i++) {
    item[i].style.background = 'pink';
    
  }
  //报错,报错原因打印3,数组最大索引2
  
for(let i =0;i<items.length;i++) {
    item[i].style.background = 'pink';
    
  }
```



## 3.const 

常量赋值给初始,也是块级作用域

const SCHOOL =0;

<u>对于数组或者常量的修改不算对常量的修改(6)</u>

```
const team = ['uzi','uzi','uzi','uzi'];
team.push('meiko');
xxx team = 100

```

## 4.解构赋值

按照一定模式从两位里面取值对变量赋值

```
let team = ['','','']
let ['','',''] = team
let team = ['jas','dreaming','dawn']
  let [a,b,c]  = team
  
    console.log(a)
    console.log(b)
    console.log(c)

let teamObj = {love:11,哈基米:12,$div:12}
let{love,哈基米,$div} = teamobj;
```





## 5.反引号-模板字符

### 1.内容可以直接出现换行符

### 2.直接变量拼接

```
 let name  = 662
  console.log(`${name},我喜欢你`)
```

## 6.对象的简写

```

let name = hsnagguigu
let casa = function casa(){
console.log()
}

let timeobj = {
name ,
casa
}

```



## 7.箭头函数

```
let fn = (a,b) =>{

}
```

### 1.箭头函数的this是静态的,它始终指向函数声明所在作用域下的值



### 2.不能作为构造实例化对象

```
let person =()=>{
this.name = name 
//这是错误的
}
```

### 3.不能使用 argument变量



![image-20230801123102371](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801123102371.png)

### 4.箭头函数的简写

省略小括号

```
let name = (a)=>{

}//当有一个形参

```

省略大括号

```
let name = a =>{}

let name = (a) = >n*n
```

## 5.this保存法

```
let _this = this 

```



给函数参数赋初始值

![image-20230801123243297](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801123243297.png)

![image-20230801123418502](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801123418502.png)

## 6.rest参数 

获取函数的实参 ,必须放到参数的最后

```
function date(...args){
	
}
date('','','')
```

### 2.扩展运算符

`...`<u>能将数组转换为逗号分隔的参数序列</u>



### 3.数组的合并

<img src="C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801124318458.png" alt="image-20230801124318458" />

### 4.数组的克隆 

![image-20230801124411710](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801124411710.png)

![image-20230801124509545](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801124509545.png)

## 7.symbol

一种新的原始数据类型,表示独一无二的值

symbol值是唯一的,不能与其他值进行运算

symbol不能使用forin

```
let s = symbol();
let s2 = symbol(尚硅谷);
let s3 = symbol.for('尚硅谷')
let s4 = symbol.for('尚硅谷')
```



symbol给对象添加方法,





symbol内置属性





## 8.迭代器

一种接口,

for of遍历 

```
for(let v of xiyou) {}
for(let v in xiyou) {}

```





生成器

异步编程的解决方案

![image-20230801131635052](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801131635052.png)

![image-20230801131856258](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801131856258.png)

![image-20230801132202725](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801132202725.png)

promise 一个构造  

用来封装异步操作

![image-20230801141333069](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801141333069.png)

成功调用第一个  失败调用第二个

promise

![image-20230801141803937](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801141803937.png)

![image-20230801141956896](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801141956896.png)

封装ajax

把xhr装进 promise 在函数外 the

![image-20230801142743997](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801142743997.png)

![image-20230801142824500](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801142824500.png)

![image-20230801143048093](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801143048093.png)

链式调用

catch

![image-20230801143616231](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801143616231.png)

set

![image-20230801143712901](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801143712901.png)

Map

![image-20230801144228574](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801144228574.png)

![image-20230801144724115](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801144724115.png)

static

继承

getter setter

![image-20230801145620868](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801145620868.png)

![image-20230801145804964](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801145804964.png)

模块化

![image-20230801145910476](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801145910476.png)

![image-20230801150056138](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801150056138.png)

![image-20230801150219123](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801150219123.png)

统一暴露

![image-20230801150349542](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801150349542.png)

![image-20230801150426437](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801150426437.png)

引入

![image-20230801150637389](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801150637389.png)

![image-20230801150851608](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801150851608.png)

script 引入







![image-20230801151035163](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801151035163.png)

![image-20230801151200920](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801151200920.png)

打包

![image-20230801151241794](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801151241794.png)

引入npm包

?



es7

![image-20230801151528751](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801151528751.png)

**平方运算

es8

![image-20230801151713806](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801151713806.png)

![image-20230801151850164](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801151850164.png)

![image-20230801152053566](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801152053566.png)

![image-20230801152252736](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801152252736.png)

![image-20230801152834596](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801152834596.png)

![image-20230801152934715](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801152934715.png)

es9

rest对对象提供支持

对象合并

命名捕获分组

![image-20230801173406008](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801173406008.png)

![image-20230801173558929](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801173558929.png)

反向断言

![image-20230801173903149](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801173903149.png)

dot

es10

再见他妈了个头啊

es11

私有属性

![image-20230801174653678](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230801174653678.png)调用方法始终是成功的

可选链操作符

动态import

globalthis