# Vue2

## 一.搭建Vue开发环境

-  开发版 vue.js
-  生产版 vue.min.js
- 引入vue2

`<script type="text/javascript" src="./vue.js">` 

- 取消警報

`Vue.config.productionTip = false`

## 二.Hello，World！

```
<body>
    <!-- /*准备好一个容器*/ -->
    <div id="root">
        <h1>Hello,{{name}}</h1>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false
        new Vue({
            el:'#root',//el用于指定当前vue实例为哪一个容器服务,值为css选择器字符串
            data:{//data中存储数据 供给el指定的容器使用
                name:'World'
            }
        }) //创建Vue实例

    </script>
</body>
```

​		<u>容器和组件一一对应</u>,

*{{这里面有什么?}}* --js表达式

1. **a**

2. **a+b**

3. **main()**

4. **x===y?x:y**

   

## 三.模板语法

### 1.插值语法

### 2.指令语法

**用于解析标签**

`<a v-bind:href="URL">点我去</a>`

  <u>被v-bind:修饰的属性为js表达式</u>  简写为 :

## 四.数据绑定

#### 1.v-bind

单向数据绑定

#### 2.v-model

双向数据绑定,<u>它只能应用在表单类元素上</u>,默认收集value

------

#### 2.1 el与data的两种写法

`v.$mount('#root')`

`data:function(){ return {name:'返回值冲' }}`

```
<body>
  <div id="hello">
    <h1 >hello,{{name}}</h1>
    <form action="">
        <input type="text" v-model:value="nihao">
        
    </form>
    <a v-bind:href="URL">点我去</a>

</div>
        
</body>
<script>
    new Vue({
        v.$mount('#root'),
        
        data:{
            
            name:'nima',
            nihao:'nihao',
            URL:'naidu.com'
        }
    })
```



## 五.MVVM



​     	 <img src="C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230808130400018.png" alt="image-20230808130400018" style="zoom: 67%; float:left;display:block;border:2px solid pink" /><span>*M:模型 对应data数据*</span>

​     	 *V:视图 模板*

​     	 <span>*VM:视图模型 ViewModel  Vue实例对象* </span>

​			<u>如果接收Vue实例请使用vm</u>







## 六.数据代理

### 1.Object.defineproperty

```
Object.defineProperty(person, ' age', (
        value: 18,
        enumerable: true，//控制属性是否可以枚举，默认值是false
        writable:true，//控制属性是否可以被修改，默认值是false
        configurable:true //控制属性是否可以被删除，默认值是false
        get:function(){   //当有人调用age属性 get函数会被调用 且返回值是age值
        return number
        }
        set(value){
        number = value
        }
```

### 2.何为数据代理

:通过一个对象代理对另一个对象中属性的操作

```
Object.defineProperty(obj2,'x' ,{
		get(){
		return obj.x
		},
		set(value){
		obj.x=value
		}
```

<u>vue对数据代理的应用</u>

`vm._data === options.data === data`

<a><u>详情参考 :尚硅谷vue全家桶 P13</u></a>

## 七.事件处理

`<button v-on:click="showInfo">点我起飞</button>`

`<button @click="showInfo">点我起飞</button>`

`<button @click="showInfo(66)">点我起飞</button>`

```
methods:{
            showInfo(event.target.innerText){
               alert("你好") 
               console.log(this)  //this指vm
            }
        }
```

### 1.*事件的修饰符*



`<a v-bind:href="URL" @click.prevent="showInfo">点我去</a>`

- prevent  阻止默认行为

- stop   阻止事件冒泡

- once 事件只触发一次

- capture 使用事件的捕获模式

- passive 立即执行 无需等待事件的回调执行完毕

  修饰符是可以连着写的

  滚动条事件

  *wheel 轮滚动*

  *scroll  条滚动*

### 2.键盘事件

- keyDown
- keyUp

`<input type="text" @keyDown.enter="demo">`

```
demo(e){
                console.log(event.target.value)
            }
```

​                 <!--别名--><img src="C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230808151359962.png" alt="image-20230808151359962" style="zoom: 80%;float:left" />











<u>tab配合keyDown使用</u>

## 八.计算属性与监视

### 1.计算属性

```
<body>
    <div id="qwer">
    姓:<input type="text" v-model="xing">
    <br>
    名:<input type="text" v-model="ming">
    <br>
    <span>全名:{{fullName}}</span>
</div>
</body>
<script>
    new Vue({
        el:'#qwer',
        data:{
            xing:'张',
            ming:'三'

        },
        computed:{
            fullName:{
                get(){
                    return this.xing+'-'+this.ming
                }
        }
        }
    })
    
</script>
```

<u>get什么时候调用</u> (缓存)

1.初次读取fullName 2.所依赖的数据发生改变

<u>set什么时候调用 ?</u>

**计算属性的简写**

当你只是考虑读取,不考虑修改

```
fullName(){
		return   
}
```

### 2.监视属性

```
 // watch:{
    //     isHot:{
    //         immediate:true,
    //         //什么时候被调用 当isHot发生改变时
    //         handler(newValue,oldValue){
    //             console.log('isHot被修改了')
    //         }
    //     }
    // }
     vm.$watch('isHot',{
            immediate:true,
            //什么时候被调用 当isHot发生改变时
            handler(newValue,oldValue){
                console.log('isHot被修改了')
           }
        })
```

#### 2.1深度监视

<u>**deep:true**</u>

```
watch:{
        //监视多级结构某个属性的变化
        isHot:{
            immediate:true,
            handler(newValue,oldValue){

            }
        },
        numbers:{
            deep:true,
            handler(){

            }
        }
    }
```

监视简写

不需要immediate,deep可以简写

`isHot(){}`

watch对比computed

- 计算属性不能开异步
- vue管理的函数最好写成普通函数,确保this指向vm或者组件对象
- 不被vue管理的函数 定时器 ajax 最好写成箭头函数 这样才可以指向vm

## 九.绑定样式

### 1.绑定class样式

```
    <div id="root">
        <div class="basc" :class="mood" @click="cmood">

        </div>
    </div>
</body>
<script>
  const vm= new Vue ({
    el:'#root',
    data:{
       mood:'normal' //字符串写法
       arr:['']  //数组写法
       classObj:{  //对象写法
       css1:true,
       css2:false,
       }
    },
    
    methods: {
        cmood(){
            this.mood='happy'
            Math.floor(Math.random()*3)
        }
    },
```

适用于样式的类名不确定,需要动态确定

适用于要绑定的个数不确定,名字不确定

适用于个数确定 名字确定 动态决定

### 2.绑定style样式

```
data:{
	fontSize:'40px'
}
```

## 十.条件渲染与列表渲染

### 1.条件渲染

`v-show="true"`

不清楚结构

`v-if="false"`

`v-if-else="n===1"`

`v-else`

清除结构,能被其他div打断

//template标签不影响结构,但是只能配合v-if

### 2.列表渲染

#### 2.1.v-for

```
遍历数组
<ul>
        <li v-for="p/(p,index) in/of persons" :key="p.id/index">
            {{p.name}}-{{p.age}}
        </li>
        
       </ul>
遍历对象
<ul>
        <li v-for="p/(value,key) in/of persons" :key="p.key/key">
            {{p.name}}-{{p.age}}
        </li>
        
       </ul>
```

key的作用与原理

虚拟dom的对比算法

<img src="C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230809142158970.png" alt="image-20230809142158970" style="zoom: 50%;" />

面试题

![image-20230809142744699](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230809142744699.png)

#### 2.2.列表过滤

```
<body>
    <div id="root">
        <input type="text" placeholder="请输入名字" v-model="keyWord">
        <ul>
            <li v-for="(p,index) of filePerson" :key="p.id">
                {{p.name}}-{{p.age}}-{{p.sex}}
            </li>
        
        </ul>

    </div>
</body>
<script>
    new Vue({
        el:'#root',
        data:{
            keyWord:'',
            persons:[
                {id:'001',name:'马冬梅',age:18,sex:'女'},
                {id:'002',name:'周冬雨',age:19,sex:'女'},
                {id:'003',name:'周杰伦',age:21,sex:'男'},
                {id:'004',name:'温兆伦',age:22,sex:'男'}
            ],
            filePerson:[]
            
        },
        watch:{
            keyWord:{
                immediate:true,
            handler(val){
            this.filePerson=    this.persons.filter((p)=>{
                    return p.name.indexOf(val)!==-1
                })
            }
            }
        }
    })
```

*监听and计算*

```
data:{
            keyWord:'',
            persons:[
                {id:'001',name:'马冬梅',age:18,sex:'女'},
                {id:'002',name:'周冬雨',age:19,sex:'女'},
                {id:'003',name:'周杰伦',age:21,sex:'男'},
                {id:'004',name:'温兆伦',age:22,sex:'男'}
            ],
            
            sortType:0,
        },
        computed:{
            filePerson(){
                return this.persons.filter((p)=>{
                    return p.name.indexOf(this.keyWord)!== -1
                })
            }
        }
```

#### 2.3列表排序

```
<body>
    <div id="root">
        <input type="text" placeholder="请输入名字" v-model="keyWord">
        <button  @click="sortType =2">升序</button></button>
        <button  @click="sortType =1">降序</button>
        <button  @click="sortType =0">原序</button>
        <ul>
            <li v-for="(p,index) of filePerson" :key="p.id">
                {{p.name}}-{{p.age}}-{{p.sex}}
            </li>
        
        </ul>


    </div>
</body>
<script>
    new Vue({
        el:'#root',
        data:{
            keyWord:'',
            persons:[
                {id:'001',name:'马冬梅',age:18,sex:'女'},
                {id:'002',name:'周冬雨',age:19,sex:'女'},
                {id:'003',name:'周杰伦',age:21,sex:'男'},
                {id:'004',name:'温兆伦',age:22,sex:'男'}
            ],
            
            sortType:0,
        },
        computed:{
            filePerson(){
               const arr= this.persons.filter((p)=>{
                    return p.name.indexOf(this.keyWord)!== -1
                })
                if(this.sortType){
                    arr.sort((a,b)=>{
                        return this.sortType ===1 ?a.age-b.age:b.age-a.age
                    })
                }
                return arr
            }
        }
```

#### 2.4监测数据原理

监测对象

```
//创建一个监视的实例对象,用于监视data中属性的变化
const obs = new Observer(data)
function Observer(obj){
?
}
```

Vue.set

`Vue.set(vm._data.student,'sex','男'`

vm.$set

只能给data里的对象加

?

监测数组

调用对数组操作的api就可以了

?

![image-20230809200227130](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230809200227130.png)

## 十一.过滤器

*时间戳*  Date.now() day.js()

Vue.prototype.dayjs = dayjs;

过滤器实现

```
<h3>现在是:{{time | timeFormater('')}}</h3>
```

```
filters:{
	timeFormater(value){
	return dayjs(value).format('YYYY年MM月DD日 HH:mm:ss')
	}
}
```

vue3已经取消了过滤器

## 十二.指令

`v-text="name"` 

`v-html="str"` <u>**解析结构**</u>

`v-cloak`

```
[v-cloak] {			//css
	display:none
}
<h2 v-cloak>{{name}}</h2>
```

`v-once` 初次动态渲染就视为静态内容了

`v-pre` 跳节点不编译

### 2.自定义指令

**函数式**

```
<body>
   <div id="root">
    <span v-text="n"></span><br>
    <span v-big="n" ></span><br>
    <button @click="n++">点我n+1</button>
   </div> 
</body>
<script type="text/javascript" >
    new Vue({
        el:'#root',
        data:{
            n:1
        },
        directives:{
            big(element,binding){  //指令与元素成功绑定时, 指令所在模板重新被解析时
                element.innerText =binding.value *10
            }
        }
    })
</script>
```

**对象式**

```
directives:{
         fbind:{
           bind(){},//指令与元素成功绑定时
           inserted(){}, //指令所在的元素被插入页面

           update(){} // 指令所在的模板被重新解析时
          } 
        }
```

全局 

```
Vue.directives('fbind',{
{
           bind(){},//指令与元素成功绑定时
           inserted(){}, //指令所在的元素被插入页面

           update(){} // 指令所在的模板被重新解析时
          } 
})
```

## 十三.生命周期

```
<body>
   <div id="root">
   <h2 :style="{opacity}">欢迎学习vue</h2>
</div> 
</body>
<script type="text/javascript" >
   new Vue({
        el:'#root',
        data:{
            opacity:1
        },
        mounted(){  //完成模板解析并把初始的真实的dom放入页面后
            setInterval(()=>{
                this.opacity -=0.01
                if(this.opacity <=0) this.opacity =1
            },16)
        }
        
    })
//     
</script>
```

<u>this指向vm或组件实例</u>

### 1.挂载流程

<img src="C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230810151141893.png" alt="image-20230810151141893" style="zoom:80%;" />

beforeCreate 

created

beforeMount

mounted

<img src="C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230810153205914.png" alt="image-20230810153205914" style="zoom: 80%;" />

### 2.更新流程

<img src="C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230810153326204.png" alt="image-20230810153326204" style="zoom:80%;" />

### 3.销毁流程

![image-20230810154139703](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230810154139703.png)

vm.$destroy()

beforedestroy 和destroyed 不能修改

