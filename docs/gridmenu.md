# gridmenu组件  

----------

<h2 id="cid_0">说明</h2>

gridmenu组件主要用于网格布局的暂时，该组件是基于基础组件grid进行封装，基本上具备grid所有属性和样式，除了具备grid本身属性和样式外，该组件还扩展了一些自己的属性和样式，方便开发者布局使用。  

在使用建议放在垂直布局容器中，宽度会自动填满父容器，如果放在水平布局容器中一定要给出width。
用法：在js里面引入require("gridmenuUI");  

示例：  
 
```html
<gridmenu  id="gridmenu1" style="cell-scale:1.2"  col="5" landcol="8"/>
```   
 
gridmenu内容只能通过loadData(json)方法动态加载。     

```javascript
var gridmenu1 = document.getElement("gridmenu1");
var json = {};
var arr = new Array();
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/20160126194705meishi.png";
itemJson.text = "美食";   
arr.push(itemJson);
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/20160126202805dianying.png";
itemJson.iconClick = "res:yuanhongqian/image/napp-active.png";
itemJson.text = "电影";  
arr.push(itemJson);
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/20160126203337jiudian.png";
itemJson.iconClick = "res:yuanhongqian/image/nme-active.png";
itemJson.isSmallTip = true;
itemJson.text = "酒店";   
arr.push(itemJson);
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/20160126202841xiuxianyule.png";
itemJson.text = "休闲娱乐";
itemJson.tip = "4";
arr.push(itemJson);
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/20160126203251waimai.png";
itemJson.text = "外卖";
           
itemJson.tip = "1";//如果是0或者空不显示
arr.push(itemJson);
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/2016101111034420161011huochejipiao.png";
itemJson.text = "机票/火车票";
arr.push(itemJson);
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/20160126202946liren.png";
itemJson.text = "丽人";
arr.push(itemJson);
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/20160126203440zhoubianyou.png";
itemJson.text = "周边游";
arr.push(itemJson);
json.datas = arr;
gridmenu1.loadData(json);
``` 
  
<h2 id="cid_1">属性</h2>

<span id="sx_0">**公共属性**</span>  

[参见公共属性章节](https://gitdocument.exmobi.cn/sprite-begin/ggsx.html)，包括：id、style、class；


**col**

<code>竖屏状态下一行现实的网格个数</code>

竖屏状态下一行现实的网格个数（可通过js修改）


**landcol**

<code>横屏切换时候的col</code>

横屏切换时候的col，横屏状态下一行显示网格个数（可通过js修改）


<h2 id="cid_2">样式</h2>

本节目录：

> [公共样式 ](#ys_0)
> 
> [grid原本样式](#ys_1) 
> 
> [color  文字颜色](#ys_2)
> 
> [color-click   文字点击颜色](#ys_3)
> 
> [background-color-click 	背景点击颜色](#ys_4)
> 
>[ icon-width	图片宽度](#ys_5)
> 
> [icon-height  图片高度](#ys_6)
> 
>[ font-size   字体大小](#ys_7)
> 
>[ tip-color  气泡字体颜色](#ys_8)
> 
>[ tip-background-color	 气泡背景色](#ys_9)


<span id="ys_0">**公共样式**</td>

> 尺寸;
> 
> 定位;
> 
>外边距;
>
>内边距;
>
>边框;
>
>背景:默认#ffffff;


<span id="ys_1">**grid原本样式**</span>

>col-spacing: cell列间距，单位dp，默认为0;
>
>row-spacing:cell行间距，单位dp，默认为0;
>
>cell-scale: cell单元格，高度与宽度比例，数字，默认为1


<span id="ys_2">**color** </span>

<code>文字颜色</code>

文字颜色，默认色值#000000


<span id="ys_3">**color-click**</span>

<code>文字点击颜色</code>

文字点击颜色，默认色值#549FF7


<span id="ys_4">**background-color-click**</span>

<code>背景点击颜色</code>

背景点击颜色，默认色值#f5f5f5


<span id="ys_5" >**icon-width**</span>

<code>图片宽度</code>

图片宽度，默认45dp

<span id="ys_6">**icon-height**</span>

<code>图片高度</code>

图片高度，默认45dp

<span  id="ys_7">**font-size** </span>

<code>字体大小</code>

字体大小，默认13dp

<span  id="ys_8">**tip-color**</span>

<code>气泡字体颜色</code>

气泡字体颜色，默认#ffffff

<span  id="ys_9">**tip-background-color**</span>

<code>气泡背景色</code>

气泡背景色，默认red


**注：**除了公共样式以外，其他菜单样式通过js修改后，需重新执行loadData()才生效。  

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


**loadData(jsonData:Object):void**

<code>注入网格数据</code>

参数：

jsonData，json格式如下：

> datas：为json数组：
> 
> - icon：网格图片，支持res:，相对路径和网络图
> 
> - text：网格文字
> 
> -  tip：网格气泡
> 
> -  isSmallTip：是否显示圆点气泡

返回值： 无

   
**gridmenuRefresh():void**

<code>刷新网格菜单数据</code>

修改菜单json数据属性后，执行gridmenuRefresh()，才可生效

参数：无

返回值：无


<h2 id="cid_4">事件</h2>

**grid本身事件**

[参见grid章节](https://gitdocument.exmobi.cn/sprite-advanced/grid.html)

**gridMenuClick**

<code>监听gridmenu点击事件</code>

event对象包括：  
 
> type：事件类型，字符串类型，固定值：gridMenuClick； 
>  
>target：触发事件的目标组件，dom对象； 
> 
>timestamp：事件触发的时间戳,单位毫秒，数字类型；

index：

监听gridmenu点击事件，返回点击标识

示例：

```javascript
gridmenu3.on("gridMenuClick ",function(e,index){});
```



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
        //引用自定义UI模板库
        //require("componentUI");
        require("titlebarUI");
        require("buttonUI");
        require("gridmenuUI");

        var myappjs = require("myapp");
        var screenWidth = window.getScreenWidth();

        window.on("loaded", function () {
            var gridmenu1 = document.getElement("gridmenu1");

            var gridmenu2 = document.getElement("gridmenu2");
            var gridmenu3 = document.getElement("gridmenu3");
            //关闭页面
            var titlebarid = document.getElement("titlebarid");
            titlebarid.on("liconClick", function (e) {
                var json = {};
                window.close(json);
            });

            titlebarid.on("ltextClick", function (e) {
                var json = {};
                window.close(json);
            });
            titlebarid.on("rtextClick", function (e) {
                var itemJson = json.datas[4];

                itemJson.icon = "res:yuanhongqian/image/20160126203251waimai.png";
                itemJson.text = "外卖123";
                itemJson.isSmallTip = true;

                var itemJson = json.datas[3];

                itemJson.icon = "res:yuanhongqian/image/20160126194705meishi.png";
                itemJson.text = "休闲123";
                itemJson.tip = "10";
                var itemJson = json.datas[2];

                itemJson.icon = "res:yuanhongqian/image/20160126203337jiudian.png";
                itemJson.iconClick = "res:yuanhongqian/image/nme-active.png";
                itemJson.isSmallTip = false;
                itemJson.text = "酒店123";
                var itemJson = json.datas[0];
                itemJson.icon = "res:yuanhongqian/image/20160126194705meishi.png";
                itemJson.text = "美食";
                itemJson.tip = "10";
                gridmenu1.refresh();
            });

            var json = {};
            var arr = new Array();
            var itemJson = {};
            itemJson.icon = "res:yuanhongqian/image/20160126194705meishi.png";
            itemJson.text = "美食";
            arr.push(itemJson);
            var itemJson = {};
            itemJson.icon = "res:yuanhongqian/image/20160126202805dianying.png";
            itemJson.iconClick = "res:yuanhongqian/image/napp-active.png";
            itemJson.text = "电影";
            arr.push(itemJson);
            var itemJson = {};
            itemJson.icon = "res:yuanhongqian/image/20160126203337jiudian.png";
            itemJson.iconClick = "res:yuanhongqian/image/nme-active.png";
            itemJson.isSmallTip = true;
            itemJson.text = "酒店";
            arr.push(itemJson);

            var itemJson = {};
            itemJson.icon = "res:yuanhongqian/image/20160126202841xiuxianyule.png";
            itemJson.text = "休闲娱乐";
            itemJson.tip = "4";
            arr.push(itemJson);
            var itemJson = {};
            itemJson.icon = "res:yuanhongqian/image/20160126203251waimai.png";
            itemJson.text = "外卖";

            itemJson.tip = "1";//如果是0或者空不显示
            arr.push(itemJson);

            var itemJson = {};
            itemJson.icon = "res:yuanhongqian/image/2016101111034420161011huochejipiao.png";
            itemJson.text = "机票/火车票";
            arr.push(itemJson);

            var itemJson = {};
            itemJson.icon = "res:yuanhongqian/image/20160126202946liren.png";
            itemJson.text = "丽人";
            arr.push(itemJson);

            var itemJson = {};
            itemJson.icon = "res:yuanhongqian/image/20160126203440zhoubianyou.png";
            itemJson.text = "周边游";
            arr.push(itemJson);

            var itemJson = {};
            itemJson.icon = "res:yuanhongqian/image/20160126205426shenghuofuwu.png";
            itemJson.text = "生活服务";
            arr.push(itemJson);

            var itemJson = {};
            itemJson.icon = "res:yuanhongqian/image/20160126203542ktv.png";
            itemJson.text = "KTV";
            arr.push(itemJson);
            json.datas = arr;
            gridmenu1.loadData(json);
            gridmenu2.loadData(json);
            gridmenu3.loadData(json);
            gridmenu1.on("gridMenuClick", function (e, tag) {
                myappjs.alert(tag);
            });

        });

        app.on("orientation", function (e, orientation) {
            var screenWidth = window.getScreenWidth();

        });
	
    ]]>
    </script>
    <style>
        @import url(res:sprite_component/css/sprite.layout.css);
        @import url(res:sprite_component/css/sprite.color.css);
    </style>
    <ui>
        <box class="bg-white full" id="box">
            <titlebar id="titlebarid" class="titlebar-hasstatus" title="gridmenu控件" licon="res:yuanhongqian/image/icon.png" style="licon-width:24;licon-height:24"
                ltext="返回" rtext="刷新" />
            <line />
            <scroll class="flex1" style="background-color:#ececec">

                <gridmenu id="gridmenu1" style="cell-scale:1.2" col="5" landcol="8" />

                <box style="height:10;" />
                <line style="line-size:0.5" />
                <gridmenu id="gridmenu2" style="icon-width:50;icon-height:50;color:red;tip-color:#000000;cell-scale:1.2;" col="4" landcol="6"
                />
                <box style="height:10;" />
                <line style="line-size:0.5" />

                <gridmenu id="gridmenu3" style="icon-width:50;icon-height:50;color:red;tip-color:#000000;font-size: 16;col-spacing:1;row-spacing:1;;cell-scale:1;background-color: #e0e0e0"
                    col="3" landcol="6" />
            </scroll>
        </box>
    </ui>
</page>

```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_6.png" style="width:250;"/>  <img width="250" src="image/fengzhuangzhujian_7.png" style="width:250;"/> 