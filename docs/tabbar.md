# tabbar组件  

----------

<h2 id="cid_0">说明</h2>

tabbar组件主要用于页签切换，类似于网易新闻等应用的页签，该组件需要和基础组件slider绑定使用，绑定后通过设置slider的index可以切换tabbar，或者滑动slider来切换tabbar。同时点击tabbar某一个页签也可以切换slider滑动。  

在使用建议放在垂直布局容器中，宽度会自动填满父容器，如果放在水平布局容器中一定要给出width。  

注：因为该控件页签切换时颜色会渐变，样式色值只能用#xxxxxx方式，不能用red,blue这样的英文单词。  

用法：在js里面引入require("tabbarUI");  

示例：
```html
<tabbar id="tabbarid1" bindid="sliderid" style="color:#909090"/>
<slider class="flex1"   id="sliderid" >
  <box><text>第1页</text></box>
  <box><text>第2页</text></box> 
  <box><text>第3页</text></box>     
  <box><text>第4页</text></box>   
  <box><text>第5页</text></box>  
  <box><text>第6页</text></box>
  <box><text>第7页</text></box> 
  <box><text>第8页</text></box>     
  <box><text>第9页</text></box>   
  <box><text>第10页</text></box>                                  
</slider>
```   
 
tabbar内容只能通过loadData(json)方法动态加载。  
     
```javascript
var  tabbarid1 = document.getElement("tabbarid1");
var json = {};
var datas = new Array();
var itemJson = {};
itemJson.text = "头条";
datas.push(itemJson);
var itemJson = {};
itemJson.text = "精选";
datas.push(itemJson);
var itemJson = {};
itemJson.text = "娱乐";
datas.push(itemJson);
var itemJson = {};
itemJson.text = "热点";
datas.push(itemJson);
var itemJson = {};
itemJson.text = "新闻";
datas.push(itemJson);
var itemJson = {};
itemJson.text = "视频";
datas.push(itemJson);
var itemJson = {};
itemJson.text = "军事";
datas.push(itemJson);
var itemJson = {};
itemJson.text = "南京";
datas.push(itemJson);
var itemJson = {};
itemJson.text = "网易号";
datas.push(itemJson);
var itemJson = {};
itemJson.text = "房产";
datas.push(itemJson);
json.datas = datas;
tabbarid1.loadData(json);
``` 
  
<h2 id="cid_1">属性</h2>

<span id="sx_0">**公共属性**</span>  

[参见公共属性章节](https://gitdocument.exmobi.cn/sprite-begin/ggsx.html)，包括：id、style、class；


**bindid**

<code>绑定slider控件的id</code>

注意只能是slider控件，绑定后通过设置slider的index可以切换tabbar

 
<h2 id="cid_2">样式</h2>

**公共样式**  

> 尺寸:默认height:44;
> 
>定位;
>
>外边距;
>
>内边距;
>
>边框;
>
>背景;
>
>flexbox布局:align-self，flex

**color**

<code>文字颜色</code>

文字颜色，默认#000000;
    
**current-color**

<code>选中的颜色</code>

包含文字和滑动条颜色，默认#549FF7;

**注：** 除了公共样式以外，其他菜单样式通过js修改后，需重新执行loadData()才生效。  

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

**loadData(jsonData:Object):void**</td>

<code>注入数据</code>

参数：

jsonData，json格式如下：

> datas：为json数组：
>
> - text：文字


<h2 id="cid_4">事件</h2>

无


<h2 id="cid_5">示例</h2>

```html
<page>
    <script>
        <![CDATA[
        var index = 1;
        var window = require("Window");
        var document = require("Document");
        var ui = require("UI");
        var console = require("Console");
        var app = require("App");

        require("titlebarUI");
        require("tabbarUI");
        var myappjs = require("myapp");

        window.on("loaded", function () {
            //关闭页面
            var titlebarid = document.getElement("titlebarid");
            var tabbarid1 = document.getElement("tabbarid1");
            var sliderid = document.getElement("sliderid");
            titlebarid.on("liconClick", function (e) {
                var json = {};
                window.close(json);
            });
            titlebarid.on("ltextClick", function (e) {
                var json = {};
                window.close(json);
            });

            titlebarid.on("rtextClick", function (e) {
                sliderid.setAttr("index", 3);
            });

            var json = {};
            var datas = new Array();
            var itemJson = {};
            itemJson.text = "头条";
            datas.push(itemJson);
            var itemJson = {};
            itemJson.text = "精选";
            datas.push(itemJson);
            var itemJson = {};
            itemJson.text = "娱乐";
            datas.push(itemJson);
            var itemJson = {};
            itemJson.text = "热点";
            datas.push(itemJson);
            var itemJson = {};
            itemJson.text = "新闻";
            datas.push(itemJson);
            var itemJson = {};
            itemJson.text = "视频";
            datas.push(itemJson);
            var itemJson = {};
            itemJson.text = "军事";
            datas.push(itemJson);
            var itemJson = {};
            itemJson.text = "南京";
            datas.push(itemJson);
            var itemJson = {};
            itemJson.text = "网易号";
            datas.push(itemJson);
            var itemJson = {};
            itemJson.text = "房产";
            datas.push(itemJson);
            json.datas = datas;
            sliderid.on("pageSelected", function (e, position) {
                //该监听事件需要放在document.refresh()方法之前， tabbarid1.loadData里面有刷新，故要放在前面
                var jsondata = { "content": position, "duration": "1" };
                ui.toast(jsondata);

            });
            tabbarid1.loadData(json);
        });
        app.on("orientation", function (e, orientation) {
            var screenWidth = window.getScreenWidth();

        });
    ]]>
    </script>
    <style>
        @import url("spriteLayout");
        @import url("spriteColor");
        .full {
            width: fill_screen;
            height: fill_screen;
        }
    </style>
    <ui>
        <box class="full" style="background-color:#ececec" id="box">
            <titlebar id="titlebarid" ltext="返回" rtext="设置索引" title="tabbar" licon="res:yuanhongqian/image/back1.png" class="titlebar-hasstatus bg-peter-river"
                style="title-color:#ffffff;left-color:#ffffff;right-color:#ffffff" />
            <line />

            <tabbar id="tabbarid1" bindid="sliderid" style="color:#909090;background-color: #ffffff;current-color:rgb(255, 0, 0)" />
            <slider class="flex1" id="sliderid">
                <box>
                    <text>第1页</text>
                </box>
                <box>
                    <text>第2页</text>
                </box>
                <box>
                    <text>第3页</text>
                </box>
                <box>
                    <text>第4页</text>
                </box>
                <box>
                    <text>第5页</text>
                </box>
                <box>
                    <text>第6页</text>
                </box>
                <box>
                    <text>第7页</text>
                </box>
                <box>
                    <text>第8页</text>
                </box>
                <box>
                    <text>第9页</text>
                </box>
                <box>
                    <text>第10页</text>
                </box>
            </slider>
        </box>
    </ui>
</page>
```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_9.gif" style="width:250;"/> 
