# superhandsign组件

----------

<h2 id="cid_0">说明</h2>

superhandsign组件为增强型手写签名组件，此组件是在基础组件handsign组件之上封装，可以支持选择16种常用画笔颜色，支持拖动滑条改变画笔粗细，以及撤销功能。  

需要注意的是，该组件不支持在使用过程中进行横竖屏切换，如果需要横屏那么在打开页面的时候就横屏打开，另外这个组件是个全屏组件，一个页面只能放一个superhandsign组件。  

用法：在js里面引入require("superhandsignUI");  

示例：
  

```html
<superhandsign id="superhandsign" folderpah="res:page/handsign/"/>
``` 

<h2 id="cid_1">属性</h2>

<span id="sx_0">**公共属性**</span>  

[参见公共属性章节](https://gitdocument.exmobi.cn/sprite-begin/ggsx.html)，包括：id、style、class；


**folderpah**

<code>需要存放的文件夹目录</code>

需要存放的文件夹目录（不含文件名）

示例：

```
folderpah="res: handsign"
```



<h2 id="cid_2">样式</h2>

无

<h2 id="cid_3">js方法</h2>

**公共方法**

[事件相关](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#cid_0)，包括：

> [on(messageName:string,callback:Function): void   组件注册事件的触发函数](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#jjxg_1)   
> 
> [fire(messageName:string,params:Array&lt;any&gt;): void  组件事件的触发函数](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#jjxg_2)   
> 
> [off(messageName:string,callback:Function): void  组件移除事件的触发函数](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#jjxg_3)  
>  
> [getOn(messageName:string): Array&lt;Function&gt;  获取已绑定的事件的触发函数](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#jjxg_4)   

[动画相关](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#cid_1)，包括： 
 
> [startAnimation(jsonData:Object,callback:Function): void  启动UI组件动画](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#dhxg_1)   
> 
> [startAnimator(jsonData:Object,callback:Function): void  启动UI组件属性动画](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#dhxg_2)   
> 
> [startKeyFrameAnimator(jsonData:Object,callback:Function): void  启动UI组件关键帧动画](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#dhxg_3)  
>  
> [ releaseAnimator(): void  结束控件动画](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#dhxg_4)   

[尺寸和位置](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#cid_2)，包括：  

> [getFrame(): Object  获取组件在父容器中的位置](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#cchwz_1)   
> 
> [setFrame(frame:Object): void  设置组件在父容器中的位置](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#cchwz_2)   
> 
> [getCenter(): Object  获取组件中心点在父容器中的位置](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#cchwz_3)  
>
> [getAbsoluteFrame(): Object  获取组件在绘制窗口中的位置](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#cchwz_4)   


[普通Dom节点操作](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#cid_3)，包括：  

> [getParent(): IElement  获取父节点](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_1)   
> 
> [getNext(): IElement  获取同级下一个节点](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_2)   
> 
> [getPrevious(): IElement  获取同级前一个节点](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_3)  
> 
> [remove(): void  从父容器中移除自身](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_4)  
> 
> [clone(isDeep:boolean):IElement  对当前Dom节点进行克隆](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_5)  
>
> [setAttr(attrName:string,attrValue:string): void  设置节点属性](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_6)   
>
> [getAttr(attrName:string):string  获取节点属性值](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_7) 
>
> [getAttrs(): Object  获取节点所有属性](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_8) 
>
> [removeAttr(attrName:string): void  移除节点属性](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_9) 
>
> [hasAttr(attrName:string): boolean  节点是否具有该属性](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_10) 
> 
> [setStyle(styleName:string,styleValue:string): void  设置节点样式值](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_13)  
>
> [getStyle(styleName:string):string  获取节点样式值](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_14)   
>
> [clearStyle(styleName:string): void  移除节点样式值](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_15)    
>
> [setClassStyle(className:string,domobj:IElement): void   设置节点对应Class样式](https://gitdocument.exmobi.cn/sprite-begin/ggff.htm#ptdom_16) 
>  
> [getClassStyle(): string  获取节点已设置Class样式](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_17)  
>  
> [getTag(): string  获取UI组件类型](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_18)  
>  
> [getId(): string  获取UI组件Id标识](https://gitdocument.exmobi.cn/sprite-begin/ggff.html#ptdom_19) 

**loadData(json:Object):void**

<code>加载已有图片</code>

如果想在某一个图片之上作画，要导入一个图片路径，如果是新建一个白板这个方法可以不用执行。

参数：

json，json格式：

> path：图片路径



<h2 id="cid_4">事件</h2>

**backClick**

<code>监听返回点击事件</code>

监听返回点击事件，一般用于关闭页面

event对象包括：  
 
> type：事件类型，字符串类型，固定值：backClick；  
> 
>target：触发事件的目标组件，dom对象；  
>
>timestamp：事件触发的时间戳,单位毫秒，数字类型；


**okClick**

<code>监听确定点击事件</code>


event对象包括：  
 
> type：事件类型，字符串类型，固定值：okClick；  
> 
>target：触发事件的目标组件，dom对象；  
>
>timestamp：事件触发的时间戳,单位毫秒，数字类型；

path:

返回后保存签名的图片路径


<h2 id="cid_5">示例</h2>

首先创建一个测试用的uixml文件，用来调用签名控件

```html
<page>
    <script>
        <![CDATA[
        var window = require("Window");
        var document = require("Document");
        var ui = require("UI");
        var time = require("Time");
        var config = require("myconfig");
        var console = require("Console");
        require("titlebarUI");
        require("buttonUI");
        var myappjs = require("myapp");
        var screenWidth = window.getScreenWidth();
        window.on("animator", function () {
            //titlebar关闭页面
            var titlebarid = document.getElement("titlebarid");
            var image1 = document.getElement("image1");
            var image2 = document.getElement("image2");
            var image3 = document.getElement("image3");
            var jizhudom = null;
            titlebarid.on("ltextClick", function (e) {
                window.close({});
            });
            titlebarid.on("liconClick", function (e) {
                window.close({});
            });
            window.on("result", function (e, data) {
                console.log("sssss" + data.path);
                jizhudom.setStyle("display", "block");
                jizhudom.setAttr("src", data.path);
                document.refresh();
            });
            var btn1 = document.getElement("btn1");
            btn1.on("click", function (e) {
                jizhudom = image1;
                var openjson = {};
                openjson.url = "res:yuanhongqian/componentdemo/superhandsign.uixml";
                openjson.target = "_blank";
                openjson.statusBar = "transparent";
                openjson.statusBarColor = "transparent";
                openjson.statusBarMode = "default";
                openjson.orientation = "portrait";
                window.open(openjson);
            });
            image1.on("click", function (e) {
                var openjson = {};
                openjson.url = "res:yuanhongqian/componentdemo/superhandsign.uixml";
                openjson.target = "_blank";
                openjson.statusBar = "transparent";
                openjson.statusBarColor = "transparent";
                openjson.statusBarMode = "default";
                openjson.orientation = "portrait";
                openjson.data = {};
                openjson.data.imageurl = this.getAttr("src");
                window.open(openjson);
            });
            var btn2 = document.getElement("btn2");
            btn2.on("click", function (e) {
                jizhudom = image2;
                var openjson = {};
                openjson.url = "res:yuanhongqian/componentdemo/superhandsign.uixml";
                openjson.target = "_blank";
                openjson.statusBar = "transparent";
                openjson.statusBarColor = "transparent";
                openjson.statusBarMode = "default";
                openjson.orientation = "landscape";
                window.open(openjson);
            });
            image2.on("click", function (e) {
                var openjson = {};
                openjson.url = "res:yuanhongqian/componentdemo/superhandsign.uixml";
                openjson.target = "_blank";
                openjson.statusBar = "transparent";
                openjson.statusBarColor = "transparent";
                openjson.statusBarMode = "default";
                openjson.orientation = "landscape";
                openjson.data = {};
                openjson.data.imageurl = this.getAttr("src");
                window.open(openjson);
            });

            var btn3 = document.getElement("btn3");
            btn3.on("click", function (e) {
                jizhudom = image3;
                var openjson = {};
                openjson.url = "res:yuanhongqian/componentdemo/superhandsign.uixml";
                openjson.target = "_blank";
                openjson.statusBar = "transparent";
                openjson.statusBarColor = "transparent";
                openjson.statusBarMode = "default";
                openjson.orientation = "landscape";
                openjson.data = {};
                openjson.data.imageurl = "res:yuanhongqian/image/1.jpg";
                window.open(openjson);

            });

            image3.on("click", function (e) {
                var openjson = {};
                openjson.url = "res:yuanhongqian/componentdemo/superhandsign.uixml";
                openjson.target = "_blank";
                openjson.statusBar = "transparent";
                openjson.statusBarColor = "transparent";
                openjson.statusBarMode = "default";
                openjson.orientation = "landscape";
                openjson.data = {};
                openjson.data.imageurl = this.getAttr("src");
                window.open(openjson);
            });
        });
    ]]>
    </script>
    <style>
        @import url(res:sprite_component/css/sprite.layout.css);
        @import url(res:sprite_component/css/sprite.color.css);
        text {
            text-overflow: ellipsis;
            singleline: true;
            line-space: 0;
        }
        
        button {
            margin: 4;
        }
    </style>
    }
    <ui>
        <box class="bg-white full" id="box">
            <titlebar id="titlebarid" ltext="返回" title="手写涂鸦控件" licon="res:yuanhongqian/image/icon.png" class="titlebar-hasstatus" style="licon-width:24;licon-height:24"
            />
            <scroll class="flex1">
                <button id="btn1" value="启动涂鸦面板 竖屏显示" />
                <image id="image1" style="width: 200;height:300;display: none" />
                <button id="btn2" value="启动涂鸦面板  横屏显示" />
                <image id="image2" style="width: 300;height:200;display: none" />
                <button id="btn3" value="启动涂鸦面板 带图片 横屏显示" />
                <image id="image3" style="width: 300;height:200;display: none" />
            </scroll>
        </box>
    </ui>
</page>
```

然后在单独创建一个uixml页面来单独放手写签名控件，这个页面会根据前一个页面打开状态进行横屏打开或者竖屏打开。

```html
<page>
    <script>
        <![CDATA[
    var index = 1;
        var window = require("Window");
        var document = require("Document");
        var ui = require("UI");
        var time = require("Time");
        var config = require("myconfig");
        var console = require("Console");

        require("titlebarUI");
        require("superhandsignUI");
        require("buttonUI");

        var myappjs = require("myapp");
        var screenWidth = window.getScreenWidth();
        window.on("animator", function () {
            //titlebar关闭页面
            var superhandsign = document.getElement("superhandsign");
            superhandsign.on("backClick", function (e) {
                console.log("监听了");
                window.close({});
            });
            superhandsign.on("okClick", function (e, path) {
                //console.log("监听了OK"+path);
                var closejson = {};
                closejson.data = {};
                closejson.data.path = path;
                window.close(closejson);
            });
            if (window.getData() != null) {
                var json = {};
                json.path = window.getData().imageurl;
                superhandsign.loadData(json);
            }
        }); 
    ]]>
    </script>
    <style>
        @import url(res:sprite_component/css/sprite.layout.css);
        @import url(res:sprite_component/css/sprite.color.css);
        text {
            text-overflow: ellipsis;
            singleline: true;
            line-space: 0;
        }
        
        button {
            margin: 4;
        }
    </style>
    }
    <ui>
        <box class="bg-white full" id="box">
            <!-- 	<titlebar id="titlebarid" ltext="返回" title="手写涂鸦控件"   licon="res:yuanhongqian/image/icon.png" class="titlebar-hasstatus"  style="licon-width:24;licon-height:24" /> -->
            <superhandsign id="superhandsign" folderpah="res:handsign" />
        </box>
    </ui>
</page>


```
>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_23.gif" style="width:250;"/>  <img width="250" src="image/fengzhuangzhujian_25.png" style="width:250;"/> 


