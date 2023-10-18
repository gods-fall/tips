# uniApp

## 一.文件目录结构说明

page-index.vue

```
<template>
<view class="box">

</view>
</template>
```

## 二.组件

pages.json--<u>全局文件配置</u>

1.注册页面

```

	"pages": [ //pages数组中第一项表示应用启动页，参考：https://uniapp.dcloud.io/collocation/pages
		{
			"path": "pages/index/index",
			"style": {
				"navigationBarTitleText": "uni-app"
			}
		}
	    ,{
            "path" : "pages/index/helloDemo1/helloDemo1",
            "style" :                                                                                    
            {
                "navigationBarTitleText": "",
                "enablePullDownRefresh": false
            }
            
        }
```

2.组件容器

4.`view` div



`rpx`响应式单位

`750x1334`

`icon :type="success" size="26"`

`text` span



1.`scroll-view` 内联滚动



2.`swiper`

```
<swiper>
<swiper-item> </swiper-item>
</swiper>
```

3.媒体组件

`image`

```
<image></image>
```

`video`

4.表单组件

5.tabar