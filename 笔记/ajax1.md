# ajax

## 一.简要介绍

最大优势无刷新获取数据

/xml可扩展标记语言

传输和存储数据/

现在用json

Ajax 最吸引人的特性是它的“异步”性质，这意味着它可以与服务器通信、交换数据并更新页面，而无需刷新页面。

![image-20230721200549878](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230721200549878.png)

## 二.请求头与请求体

/请求报文/

行 get /                /http/1.1

 头 host : xx.com 

cookie : name=longlong

content-type: application/xxx

user-agent: chrome 83

空行

体username=admin

/响应报文/

行 http/1.1  200 ok 

头  content-type:text/html;charset=utf-8

​		

空行

体  html   

​		head

​			body 

​		h1	



network

使用

## 三.express 框架

`npm init --yes`

`npm i express`

```
const express = require('express')
const app = express()
const port = 3000
app.get('/',(request,response)=>{
res.send('hello,ajax')
});
app.listen(port ,()=>{
    console.log('已经被访问啦')
})
```

引入 express 

const express = require('express')

创建应用对象 

const app = express()

创建路由规则

request是对请求报文  封装

app.get('/',(request,reponse)=>{

设置响应 

response.send('hell')

});

监听端口启动服务

app.listen(8000,()=>{

console.log(服务已经启动")})

## 四.ajax的准备

准备 

1.前端页面的准备

无

2.服务端的准备

```
const express = require('express')
const app = express()
const port = 3000
app.get('url',(rqu,res)=>{
res.send()
res.setHeader('Access-Control-Allow-Origin','*')
app.listen(port,()=>{
console.log()
})
})
```

设置允许跨域

` res.setHeader('Access-Control-Allow-Origin','*')`

node server.js

```
        btn.onclick = function(){
            const xhr = XMLHttpRequest();
            xhr.open('GET','http://127.0.0.1:3000/server');
            xhr.send();
            xhr.onreadystatechange =function(){
                if(xhr.readyState === 4){
                    if(xhr.status ===200) {
                        
                    }
                }
            }
        }
```

`xhr.status`获取状态码

`xhr.statusText`获取状态字符串

`xhr.getAllResponseHeader`获取所有请求头

`xhr.reponse`请求体

## 五.设置请求参数

`http://127.0.0.1:3000/server?a=100&b=200&c=300`



## 六.发送post请求

` xhr.open('POST','http://127.0.0.1:3000/server?a=100&b=200&c=300');`

`请求体 xhr.send('A=100&B=200&C=300');`

## 七.设置请求头

`xhr.setRequestHeader('Content-Type','application/x-www')`

## 八.json的请求与响应

`Json.Stringify()`对象转json格式的字符串

`json.parse()json`字符串转为对象

`xhr.responseType = 'json';`自动转换

## 九.nodemon安装

## 十.缓存

缓存可以通过在链接请求上加时间戳 `?t=' +Date.now()`

这样就被认为不是同一个链接

## 十一.请求超时与异常处理

`xhr.timeout=2000;`

`xhr.ontimeout = function(){}`

`xhr.onerror = function(){}`

## 十二.取消请求

`x.abort()`

注意:使用let声明`x=null`

## 十三.请求重复发送问题

取消发送的相同请求,

```
 	let x = null
       let isSending = false;
        btn.onclick = function(){
            if(isSending) x.abort();
            isSending =true;
             x = new XMLHttpRequest();
            x.open('POST','http://127.0.0.1:3000/server');
            x.send();
           
            x.onreadystatechange =function(){
               
                if(x.readyState === 4){
                    isSending=false
                    if(x.status >=200&&x.status<=300) {
                     input1.value = JSON.parse(x.response).d
                    }
                }
            }
        }
```

## 十四.jQuery发送ajax

`$('button').eq(0).click(function(){ $.get('',{},function(data) { }),'json'}`

```
$('button').eq(2).click(function(){
$.ajax({
url:''
data:{}
type:'GET'
timeout:2000,
success:function(data) {
dataType:'json'
}
})
})
```

## 十五.axios发送ajax

### 1.基本发送

```
btn.onclick=function(){
        axios.post('http://127.0.0.1:3000/server')
        .then(function(res){
           
            console.log(res.data.d)
        })
        .catch(function(error){
            console.log('出错啦')
        })
        .then(function(){
            
        })
      }
```

### 2对于传参的基本理解

params

params 的对象参数名和值， axios 源码会把参数和值，拼接在 url? 后面给后台（query 查询字符串）

data 

data 的对象参数名和值，axios 源码会把参数和值，拼接在[请求体](https://so.csdn.net/so/search?q=请求体&spm=1001.2101.3001.7020)里（body 参数）

headers

拼接在请求头里

params传参：后台通过 query 找到前台传过来的数据 

data传参：后台通过 body 找到前台传过来的数据  

 headers传参：后台通过 请求头 找到前台传过来的数据 

` axios.defaults.baseURL='https://api.btstu.cn';`

`axios.defaults.headers.common['Authorization'] = AUTH_TOKEN;`

```
axios({ url :'/',
methods:'post',
params:{

}
})
```

```
// 支持async/await用法
async function getUser() {
  try {
    const response = await axios.get('/user?ID=12345');
    console.log(response);
  } catch (error) {
    console.error(error);
  }
}
```

### 3.发起多个并发请求

```
function getUserAccount() {
  return axios.get('/user/12345');
}

function getUserPermissions() {
  return axios.get('/user/12345/permissions');
}

Promise.all([getUserAccount(), getUserPermissions()])
  .then(function (results) {
    const acct = results[0];
    const perm = results[1];
  });
```

` response.data.pipe(fs.createWriteStream('ada_lovelace.jpg'))`?

### 4.一段响应体的结构

```
{
  // `data` 由服务器提供的响应
  data: {},

  // `status` 来自服务器响应的 HTTP 状态码
  status: 200,

  // `statusText` 来自服务器响应的 HTTP 状态信息
  statusText: 'OK',

  // `headers` 是服务器响应头
  // 所有的 header 名称都是小写，而且可以使用方括号语法访问
  // 例如: `response.headers['content-type']`
  headers: {},

  // `config` 是 `axios` 请求的配置信息
  config: {},

  // `request` 是生成此响应的请求
  // 在node.js中它是最后一个ClientRequest实例 (in redirects)，
  // 在浏览器中则是 XMLHttpRequest 实例
  request: {}
}
```

### 5.拦截器

```
// 添加请求拦截器
axios.interceptors.request.use(function (config) {
    // 在发送请求之前做些什么
    return config;
  }, function (error) {
    // 对请求错误做些什么
    return Promise.reject(error);
  });

// 添加响应拦截器
axios.interceptors.response.use(function (response) {
    // 2xx 范围内的状态码都会触发该函数。
    // 对响应数据做点什么
    return response;
  }, function (error) {
    // 超出 2xx 范围的状态码都会触发该函数。
    // 对响应错误做点什么
    return Promise.reject(error);
  });
```

### 6.取消请求

AbortController

```
const controller = new AbortController();

axios.get('/foo/bar', {
   signal: controller.signal
}).then(function(response) {
   //...
});
// 取消请求
controller.abort()
```

CancelToken

## 十六.fetch方法发送请求

## 十七.跨域

### 1.同源策略

协议域名端口号

### 2.解决跨域

jsonp利用script标签实现跨域

?

cors解决跨域

`res.setHeader = Access-control-Alllow-origin,'*'`
