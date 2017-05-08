# newslider组件  

----------

<h2 id="cid_0">说明</h2>

newslider主要用于主页广告滑动栏效果布局，基于基础组件slider进行封装，具有slider组件全部属性，该控件建议放在垂直布局的容器中使用，如果放在水平布局的容器中，一定要给出width，否则组件可能不显示。组件内部已经给出了默认高度height值为180dp，使用是可以根据自己的实际情况通过样式进行调整。  

用法：在js里面引入require("newsliderUI");  

示例：  
 
 
```html
<newslider id="newslider2" index="1" loop="true" style="color:red;font-size:20;mark-point-color:red;bottom-mark-height:36;mark-point-width:10;mark-point-height:10"/>
```   
 
newslider内容只能通过loadData(json)方法动态加载，还需要注意的是只有内容大于两个的时候才能支持循环滑动。     

```javascript
var newslider1 = document.getElement("newslider1");	
var data = {};
data.text = "华中师大教授讽范冰冰 不欢迎这样戏子";
data.imageurl = "http://cms-bucket.nosdn.127.net/d325d6e7b40e45598aadb2fcc67249c220161028103329.png";
data.defaulturl = "res:spritetest/image/wangyi/default_null_big_src.png";
datas.push(data);

var data = {};
data.text = "成都S型急弯马路如赛道 多车辆压线";
data.imageurl = "http://cms-bucket.nosdn.127.net/a54d528ac2c04d7fb5cf544d82e3e0db20161029081754.jpeg";
data.defaulturl = "res:spritetest/image/wangyi/default_null_big_src.png";
datas.push(data);
var data = {};
data.text = "成都S型急弯马路如赛道 多车辆压线2";
data.imageurl = "http://cms-bucket.nosdn.127.net/a54d528ac2c04d7fb5cf544d82e3e0db20161029081754.jpeg";
data.defaulturl = "res:spritetest/image/wangyi/default_null_big_src.png";
datas.push(data);
json.datas = datas;
newslider1.loadData(json);
``` 
  
<h2 id="cid_1">属性</h2>

本节目录：

> [公共属性 ](#sx_0)
> 
>[type	展示类型](#sx_1)	
>
>[index	当前显示页索引](#sx_2)
>
>[direction	滚动方向](#sx_3)
>
>[drag	是否允许手动拖动切换](#sx_4)
>
>[loop	是否支持循环滑动](#sx_5)
>
>[autoPlay	是否自动切换](#sx_6)
>
>[interval	自动切换间隔时间](#sx_7)
>
>[bounces	是否支持弹动](#sx_8)


<span id="sx_0">**公共属性**</span>  

[参见公共属性章节](https://gitdocument.exmobi.cn/sprite-api/ggsx.html)，包括：id、style、class；


<span id="sx_1">**type**</span>

<code>展示类型</code>

支持normal和notext( 没有文字时标记点居中 ) 两种类型
    
<span id="sx_2">index</span>

<code>当前显示页索引</code>

默认为0，支持设置及获取（支持js动态修改）


<span id="sx_3">**direction**</span>

<code>滚动方向</code>

取值：[horizontal，vertical];

> horizontal：横向滚动；（默认）
> 
> vertical：纵向滚动； 

<span id="sx_4">**drag**</span>

<code>是否允许手动拖动切换</code>

取值[true，false]:

> true：允许手动拖动切换（默认）；
> 
>false：不允许手动拖动切换；
     

<span id="sx_5">**loop**</span>

<code>是否支持循环滑动</code>

取值[true，false]:

> true：支持循环；
> 
>false：不支持循环（默认）

**注：** 循环滑动子容器应不少于3个

<span id="sx_6">autoPlay</span>

<code>是否自动切换</code>

取值[true，false]

> true：自动切换；
> 
>false：不自动切换（默认）
    
<span id="sx_7">interval</span>

<code>自动切换间隔时间</code>

取值数字，单位s;默认3s

<span id="sx_8">bounces</span>

<code>是否支持弹动</code>

取值[true，false];

> true：支持弹动（默认）
> 
>false：不支持弹动;

**注：** 仅iOS支持
 
<h2 id="cid_2">样式</h2>

本节目录：


**公共样式**

> 尺寸:默认height:180;
> 
>定位;
>
>外边距;
>
>内边距;
>
>边框;
>
>背景:默认#ffffff;
>
>flexbox布局：align-self，flex

**bottom-mark-height**

<code>底部文字描述条高度</code>

底部文字描述条高度;默认30dp

**mark-point-width**

<code>标记点宽度</code>

标记点宽度;默认6dp

**mark-point-height**

<code>标记点高度</code>

标记点高度;默认6dp

    
**mark-point-color**

<code>标记点颜色</code>

标记点颜色;默认#ffffff

     
**color**
<code>底部描述文字颜色</code>

底部描述文字颜色;默认#ffffff

**font-size**

<code>底部描述文字大小</code>

底部描述文字大小;默认15dp

**注：** 除了公共样式以外，其他菜单样式通过js修改后，需重新执行loadData()才生效。  


<h2 id="cid_3">js方法</h2>



**公共方法**  

[事件相关](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_0)，包括：

> [on(messageName:string,callback:Function): void   组件注册事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_1)   
> 
> [fire(messageName:string,params:Array&lt;any&gt;): void  组件事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_2)   
> 
> [off(messageName:string,callback:Function): void  组件移除事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_3)  
>  
> [getOn(messageName:string): Array&lt;Function&gt;  获取已绑定的事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_4)   

[动画相关](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_1)，包括： 
 
> [startAnimation(jsonData:Object,callback:Function): void  启动UI组件动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_1)   
> 
> [startAnimator(jsonData:Object,callback:Function): void  启动UI组件属性动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_2)   
> 
> [startKeyFrameAnimator(jsonData:Object,callback:Function): void  启动UI组件关键帧动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_3)  
>  
> [ releaseAnimator(): void  结束控件动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_4)   

[尺寸和位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_2)，包括：  

> [getFrame(): Object  获取组件在父容器中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_1)   
> 
> [setFrame(frame:Object): void  设置组件在父容器中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_2)   
> 
> [getCenter(): Object  获取组件中心点在父容器中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_3)  
>
> [getAbsoluteFrame(): Object  获取组件在绘制窗口中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_4)   


[普通Dom节点操作](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_3)，包括：  

> [getParent(): IElement  获取父节点](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_1)   
> 
> [getNext(): IElement  获取同级下一个节点](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_2)   
> 
> [getPrevious(): IElement  获取同级前一个节点](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_3)  
> 
> [remove(): void  从父容器中移除自身](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_4)  
> 
> [clone(isDeep:boolean):IElement  对当前Dom节点进行克隆](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_5)  
>
> [setAttr(attrName:string,attrValue:string): void  设置节点属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_6)   
>
> [getAttr(attrName:string):string  获取节点属性值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_7) 
>
> [getAttrs(): Object  获取节点所有属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_8) 
>
> [removeAttr(attrName:string): void  移除节点属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_9) 
>
> [hasAttr(attrName:string): boolean  节点是否具有该属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_10) 
> 
> [setStyle(styleName:string,styleValue:string): void  设置节点样式值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_13)  
>
> [getStyle(styleName:string):string  获取节点样式值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_14)   
>
> [clearStyle(styleName:string): void  移除节点样式值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_15)    
>
> [setClassStyle(className:string,domobj:IElement): void   设置节点对应Class样式](https://gitdocument.exmobi.cn/sprite-api/ggff.htm#ptdom_16) 
>  
> [getClassStyle(): string  获取节点已设置Class样式](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_17)  
>  
> [getTag(): string  获取UI组件类型](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_18)  
>  
> [getId(): string  获取UI组件Id标识](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_19) 

**loadData(jsonData:Object):void**

<code>注入数据</code>

参数：

jsonData，json格式如下：

> datas：为json数组：
> 
> - imageurl：网格图片，支持res:，相对路径和网络图
> 
> - text：新闻内容文字
> 
> - defaulturl：默认图片地址

返回值： 无

<h2 id="cid_4">事件</h2>

**newsliderClick**

<code>点击新闻图片触发</code>

event对象包括：  
 
> type：事件类型，字符串类型，固定值：newsliderClick； 
>  
>target：触发事件的目标组件，dom对象； 
> 
>timestamp：事件触发的时间戳,单位毫秒，数字类型；

index：

返回点击标识

**pageSelected**

<code>监听newslider切换触发</code>

event对象包括：

> type：事件类型，字符串类型，固定值：pageSelected； 
>  
>target：触发事件的目标组件，dom对象； 
> 
>timestamp：事件触发的时间戳,单位毫秒，数字类型；


index：

监听newslider切换事件，返回切换后的标识



<h2 id="cid_5">示例</h2>

```html
<page>
    <script>
        <![CDATA[
        var index = 1;
        var window = require("Window");
        var document = require("Document");
        var console = require("Console");
        var ui = require("UI");
        var ListAdapter = require("ListAdapter");
        var console = require("Console");

        //引用自定义UI模板库
        require("titlebarUI");
        require("newsliderUI");

        var myappjs = require("myapp");
        var screenWidth = window.getScreenWidth();
        var json = {};
        var datas = new Array();

        window.on("animator", function () {
            //titlebar关闭页面
            var titlebarid = document.getElement("titlebarid");
            titlebarid.on("ltextClick", function (e) {
                var json = {};
                window.close(json);

            });

            titlebarid.on("liconClick", function (e) {
                var json = {};
                window.close(json);
            });

            var newslider1 = document.getElement("newslider1");
            var newslider2 = document.getElement("newslider2");
            var newslider3 = document.getElement("newslider3");
            var data = {};
            data.text = "华中师大教授讽范冰冰 不欢迎这样戏子";
            data.imageurl = "http://cms-bucket.nosdn.127.net/d325d6e7b40e45598aadb2fcc67249c220161028103329.png";
            data.defaulturl = "res:spritetest/image/wangyi/default_null_big_src.png";
            datas.push(data);
            var data = {};
            data.text = "成都S型急弯马路如赛道 多车辆压线";
            data.imageurl = "http://cms-bucket.nosdn.127.net/a54d528ac2c04d7fb5cf544d82e3e0db20161029081754.jpeg";
            data.defaulturl = "res:spritetest/image/wangyi/default_null_big_src.png";
            datas.push(data);
            var data = {};
            data.text = "成都S型急弯马路如赛道 多车辆压线2";
            data.imageurl = "http://cms-bucket.nosdn.127.net/a54d528ac2c04d7fb5cf544d82e3e0db20161029081754.jpeg";
            data.defaulturl = "res:spritetest/image/wangyi/default_null_big_src.png";
            datas.push(data);
            json.datas = datas;

            newslider1.loadData(json);
            newslider2.loadData(json);
            newslider3.loadData(json);

            newslider1.on("newsliderClick", function (e, param) {

                var message = {};
                message.content = JSON.stringify(param);
                ui.toast(message);
            });
            newslider1.on("pageSelected", function (e, param) {
                var message = {};
                message.content = JSON.stringify(param);
                ui.toast(message);
            });
        });
    ]]>

    </script>
    <style>
        @import url(res:sprite_component/css/sprite.layout.css);
        @import url(res:sprite_component/css/sprite.color.css);
    </style>
    <ui>
        <box class="bg-white full" id="box">
            <titlebar id="titlebarid" ltext="返回" title="select控件" licon="res:yuanhongqian/image/icon.png" class="titlebar-hasstatus"
                style="licon-width:24;licon-height:24" />
            <scroll style="flex:1;width:fill_screen;">
                <newslider id="newslider1" />
                <box style="height:10" />
                <newslider id="newslider2" index="1" loop="true" style="color:red;font-size:20;mark-point-color:red;bottom-mark-height:36;mark-point-width:10;mark-point-height:10"
                />
                <box style="height:10" />
                <newslider id="newslider3" type="notext" />
            </scroll>
        </box>
    </ui>
</page>

```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_8.png" style="width:250;"/> 
