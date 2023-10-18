.net core

.net 

.net standard 标准

.net core

.net framework

ilspy反编译工具

只有定义 没有实现

dotnet.Microsoft.com





nuget

![image-20230726215054882](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230726215054882.png)

异步编程

不能让单个请求变快

async异步方法 

task<T>t是真正的返回值类型 

![image-20230726221600818](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230726221600818.png)

![image-20230726222516114](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230726222516114.png)

 await

并发

编写异步方法

![image-20230726223617240](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230726223617240.png)

![image-20230726224607314](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230726224607314.png)

![image-20230726224822978](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230726224822978.png)

原理

![image-20230726225148705](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230726225148705.png)

语法糖![image-20230726230214253](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230726230214253.png)

获得线程id

![image-20230727110338648](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727110338648.png)

异步调用之前和调用之后代码可能运行在不同线程之中

避免线程切换

丢进run才会在新的线程中执行

![image-20230727113010404](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727113010404.png)



不写async![image-20230727114159593](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727114159593.png)

async方法的缺点![image-20230727114241824](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727114241824.png)

什么情况可以去掉async ![image-20230727114535524](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727114535524.png)

不使用sleep

![image-20230727115042186](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727115042186.png)

await Task.delay

![image-20230727115924955](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727115924955.png)

cancellationtoken

用于提前终止执行的信号

none 空

![image-20230727120251582](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727120251582.png)

![image-20230727120512382](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727120512382.png)

whenall

whenany

![image-20230727122642465](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727122642465.png)

![image-20230727122810442](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727122810442.png)

接口和抽象类 不能写async 实现可以写

yield 

![image-20230727123854296](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727123854296.png)

![image-20230727124406169](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727124406169.png)

linq

让数据傻瓜化

![image-20230727125558109](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727125558109.png)

lambda

()=>{

}

![image-20230727131240450](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727131240450.png)

where 会遍历

![image-20230727132004022](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727132004022.png)

![image-20230727133228777](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727133228777.png)

常用的拓展

list.where (传入过滤的lambda表达式)

​		count传入数据的条数

​		any()是否有一条

​	single() 有且只有一个 

![image-20230727134854421](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727134854421.png)

singleordefault最多有一套

first 返回一条,至少有一条

firstordefault 返回一条或者默认值



排序 

orderby

orderbydescending倒叙

thenby

限制结果集

![image-20230727140433790](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727140433790.png)

聚合函数

![image-20230727140853868](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727140853868.png)

分组

groupby ()

![image-20230727141726938](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727141726938.png)

投影

select

只是取

映射

![image-20230727143314362](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727143314362.png)

复合![image-20230727143658714](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727143658714.png)

集合转换

![image-20230727143857030](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727143857030.png)

链式调用

<>

面试题

![image-20230727145756893](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727145756893.png)

*

依赖注入

di是ioc的实现方式  控制反转

![image-20230727151145779](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727151145779.png)

![image-20230727151450556](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727151450556.png)

概念

![image-20230727151709145](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727151709145.png)

![image-20230727152413517](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727152413517.png)

前提 一个接口俩实现类



使用di

![image-20230727152702642](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230727152702642.png)



服务的生命周期

![image-20230728095529817](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230728095529817.png)

di

构造函数注入再看

![image-20230728102418878](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230728102418878.png)

配置系统

![image-20230728105004671](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230728105004671.png)

读取本地的json文件

![image-20230729102138928](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729102138928.png)



![image-20230728105503013](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230728105503013.png)

属性 较新复制

![image-20230728105614946](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230728105614946.png)

读取



![image-20230728110303830](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230728110303830.png)

![image-20230728110523455](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230728110523455.png)

![image-20230728110703971](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230728110703971.png)

ioptionsnapshot

![image-20230729103656334](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729103656334.png)

其他的项目配置

![image-20230729104500218](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729104500218.png)

项目属性调试

扁平化配置

![image-20230729105658555](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729105658555.png)

![image-20230729105824190](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729105824190.png)

开发自己的配置

![image-20230729111833112](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729111833112.png)

//



集群![image-20230729111932533](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729111932533.png)

多配置源的优先级

![image-20230729114953811](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729114953811.png)

logging日志系统

![image-20230729120149747](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729120149747.png)

![image-20230729120625054](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729120625054.png)

![image-20230729122708970](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729122708970.png)



![image-20230729123655273](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729123655273.png)

结构化日志

集中化日志

![image-20230729124225149](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729124225149.png)

ef core

![image-20230729124907082](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729124907082.png)

![image-20230729124949869](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729124949869.png)

![image-20230729131511801](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729131511801.png)

efcore 搭建

![image-20230729140808152](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729140808152.png)

![image-20230729141052310](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729141052310.png)

![image-20230729141427251](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729141427251.png)

![image-20230729142010570](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729142010570.png)

![image-20230729142300832](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729142300832.png)

![image-20230729142418633](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729142418633.png)

![image-20230729142944276](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729142944276.png)

增删改查

![image-20230729144052345](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729144052345.png)

![image-20230729144148268](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729144148268.png)

![image-20230729144755106](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729144755106.png)

![image-20230729145335658](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729145335658.png)

![image-20230729145558657](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729145558657.png)

![image-20230729145919347](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729145919347.png)

executeupdateasync批量更新 删除

约定规则

![image-20230729150624003](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729150624003.png)

![image-20230729151128373](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729151128373.png)



![image-20230729151505450](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230729151505450.png)

主键

![image-20230730113431383](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230730113431383.png)

![image-20230730113849933](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230730113849933.png)

![image-20230730121756563](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230730121756563.png)

![image-20230730122305625](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230730122305625.png)

![image-20230730122552127](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230730122552127.png)

![image-20230730123158734](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230730123158734.png)



![image-20230730124528958](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230730124528958.png)

![image-20230730124757454](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230730124757454.png)

![image-20230730151359444](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230730151359444.png)

一对多

![image-20230731101019662](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230731101019662.png)

![image-20230731101924103](C:\Users\link\AppData\Roaming\Typora\typora-user-images\image-20230731101924103.png)
