# menubar组件  

----------

<h2 id="cid_0">说明</h2>

menubar组件主要用于页面底部菜单展示，一般建议菜单个数不要超过5个，menubar封装了两种菜单类型normal和middleMain，其中middleMain菜单可以在中间定义一个圆形的大菜单，在点击的时候，组件内部会旋转135度，类似QQ空间的底部菜单效果。  

在使用建议放在垂直布局容器中，宽度会自动填满父容器，如果放在水平布局容器中一定要给出width。  

用法：在js里面引入require("menubarUI");  

示例，normal类型：  
  
```html
<menubar type="normal" id="menubar1" />
```   

示例，middleMain类型：  

```html
<menubar id="menubar4" type="middleMain" mainicon="res:yuanhongqian/image/feedback_plus.png" style="main-transfer-y:-8" index = "0"/>
```    

menubar菜单内容只能通过loadData(json)方法动态加载。   

```javascript
var menubar1 = document.getElement("menubar1");
var json = {};
var arr = new Array();
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/nxinxi.png";
itemJson.iconCurrent = "res:yuanhongqian/image/nxinxi-active.png";
itemJson.text = "消息";
itemJson.tip = "4";
arr.push(itemJson);
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/ncontact.png";
itemJson.iconCurrent = "res:yuanhongqian/image/ncontact-active.png";
itemJson.text = "通讯录";	 
arr.push(itemJson);
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/napp.png";
itemJson.iconCurrent = "res:yuanhongqian/image/napp-active.png";
itemJson.text = "应用";	 
arr.push(itemJson);
var itemJson = {};
itemJson.icon = "res:yuanhongqian/image/nme.png";
itemJson.iconCurrent = "res:yuanhongqian/image/nme-active.png";
itemJson.isSmallTip = true;
itemJson.text = "我";	 
arr.push(itemJson);
json.datas = arr;
menubar1.loadData(json);
``` 
  
<h2 id="cid_1">属性</h2>

<span id="sx_0">**公共属性**</span>  

[参见公共属性章节](https://gitdocument.exmobi.cn/sprite-api/ggsx.html)，包括：id、style、class；


**index**

<code>设置选中菜单项</code>

值从0开始，如果不设置默认为0对应第一个菜单(通过js可以动态修改)

示例：
```javascript
document.getElement("menubar1");
menubar1.setAttr("index","2");
```

**mainicon**

<code>主菜单图片路径</code>

主菜单图片路径，支持res:和相对路径

**type**

<code>menubar样式</code>

取值[normal, middleMain]

> normal：普通形式的菜单，建议最多放5个
> 
>middleMain：在菜单中间有个原型的突出按钮，可以旋转，建议做多放4个菜单


 
<h2 id="cid_2">样式</h2>

>[公共样式](#ys_0)
>
>[color	菜单文字颜色](#ys_1)
>
>[current-color	菜单文字选择颜色](#ys_2)
>
>[tip-color	气泡数字颜色](#ys_3)
>
>[tip-background-color	气泡背景颜色](#ys_4)
>
>[icon-width	菜单图标宽度](#ys_5)
>
>[icon-height	菜单图标高度](#ys_6)
>
>[font-size	菜单字体大小](#ys_7)
>
>[main-background-color	middleMain样式下主菜单背景颜色	](#ys_8)
>
>[main-transfer-y	主菜单基于当前坐标y偏移距离,默认0](#ys_9)
>
>[main-transfer-x	主菜单基于基于当前坐标x偏移距离; 默认0 ](#ys_10)	
>
>[text-margin	菜单文字外边距](#ys_11)
>
>[icon-margin	图片外边距,默认](#ys_12)

<span id="ys_0">**公共样式**</span>

> 尺寸:height默认50dp;
> 
>定位;
>
>外边距;
>
>边框;
>
>背景:默认#f9f9f9;
>
>flexbox布局:align-self，flex;

<span id="ys_0">**color**</span>

<code>菜单文字颜色</code>

默认色值#565656；	

<span id="ys_1">**current-color**</span>	

<code>菜单文字选择颜色</code>

默认色值#549FF7	

<span id="ys_2">**tip-color**</span>
	
<code>气泡数字颜色</code>

默认色值#ffffff	


<span id="ys_3">**tip-background-color**</span>

<code>气泡背景颜色</code>

默认色值red	

<span id="ys_4">**icon-width**</span>

<code>菜单图标宽度</code>

默认25dp	


<span id="ys_5">**icon-height**</span>

<code>菜单图标高度</code>

默认25dp	

<span id="ys_6">**font-size**</span>	

<code>菜单字体大小</code>

默认14dp	


<span id="ys_7">**main-background-color**</span>

<code>主菜单背景颜色</code>

middleMain样式下，主菜单背景颜色，默认#549FF7	

<span id="ys_8">**main-transfer-y**</span>

<code>主菜单基于当前坐标y偏移距离</code>

默认0 (赋值的时候这里不要带dp单位)	

<span id="ys_9">**main-transfer-x**</span>	

<code>主菜单基于基于当前坐标x偏移距离</code>

 默认0 (赋值的时候这里不要带dp单位)	

<span id="ys_10">**text-margin**</span>	

<code>菜单文字外边距</code>

默认margin:0 0 0 0	

<span id="ys_11">**icon-margin**</span>

<code>图片外边距</code>

默认icon-margin:0 25 0 25



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

在模板里面使用时，该方法不能放在created里面执行，因为loadData时组件内部需要布局刷新，created时候是不允许执行刷新操作的。

参数：

jsonData，json格式如下：

> datas：为json数组：
>
> - text：文字
> 
> - icon：菜单图标
> 
> - isSmallTip：是否显示圆点气泡
> 
> - tip：气泡的值

返回值：无


**menubarRefresh():void**

<code>刷新menubar数据</code>

修改菜单json数据属性后，执行menubarRefresh()，才可生效。</td>
    
参数：无

返回值：无



**clickMiddle():void**

<code>模拟点击中间按钮</code>

参数：无

返回值：无


**mainImageInsertBeforeDom(IElement:dom):void**

<code>中间菜单图片显示在某个dom之前</code>

由于中间菜单在布局中采用绝对定位，默认层在最上层，有时候需要其他层进行遮罩，可以设置在某一层之前显示。
 

<h2 id="cid_4">事件</h2>

**selectedItem**

<code>监听选中菜单标识</code>

event对象包括：  
 
> type：事件类型，字符串类型，固定值：selectedItem； 
>  
>target：触发事件的目标组件，dom对象； 
> 
>timestamp：事件触发的时间戳,单位毫秒，数字类型；

index：

监听选中菜单标识

      
**middleMainClick**

<code>监听点击中间按钮</code>

event对象包括：  
 
> type：事件类型，字符串类型，固定值：middleMainClick； 
>  
>target：触发事件的目标组件，dom对象； 
> 
>timestamp：事件触发的时间戳,单位毫秒，数字类型；

tag：

监听主菜单点击事件，取值[0,1]

> 1:标示已旋转
>
>0:标示还原

示例：

```javascript
menubar3.on("middleMainClick",function(e,tag){
	//1标示已旋转，0标示回归原位
	myappjs.alert("按钮状态:"+tag);
});
```

<h2 id="cid_5">示例</h2>

```html
<page>
	<script><![CDATA[
    var window = require("Window");
    var document = require("Document");
    var ui = require("UI");
	var console = require("Console");
	var app = require("App");
	var time = require("Time");
	//引用自定义UI模板库
     //require("componentUI");
     require("titlebarUI");
     require("buttonUI");
     require("menubarUI");
    var myappjs = require("myapp");
 
	window.on("loaded",function(){
	  var screenWidth = window.getScreenWidth();
	  var titlebarid = document.getElement("titlebarid");
	    //关闭页面
	    titlebarid.on("ltextClick",function(e)
	    {
	        var json = {};
	        window.close(json);      
	    });
	    titlebarid.on("liconCurrent",function(e)
	    {
	        var json = {};
	        window.close(json);      
	    });
	    titlebarid.on("rtextClick",function(e)
	    {
	    	 var itemJson = json.datas[0];
			  itemJson.icon = "res:yuanhongqian/image/ncontact.png";
			  itemJson.iconCurrent = "res:yuanhongqian/image/ncontact-active.png";
			  itemJson.text = "消息123";
			  itemJson.tip = "1";
			  menubar1.refresh();
	    });
	  var json = {};
	  var arr = new Array();
	  var itemJson = {};
	  itemJson.icon = "res:yuanhongqian/image/nxinxi.png";
	  itemJson.iconCurrent = "res:yuanhongqian/image/nxinxi-active.png";
	  itemJson.text = "消息";
	  itemJson.tip = "4";
	 
	  arr.push(itemJson);
	  var itemJson = {};
	  itemJson.icon = "res:yuanhongqian/image/ncontact.png";
	  itemJson.iconCurrent = "res:yuanhongqian/image/ncontact-active.png";
	  itemJson.text = "通讯录";	 
	  arr.push(itemJson);

	  var itemJson = {};
	  itemJson.icon = "res:yuanhongqian/image/napp.png";
	  itemJson.iconCurrent = "res:yuanhongqian/image/napp-active.png";
	  itemJson.text = "应用";	 
	  arr.push(itemJson);

	  var itemJson = {};
	  itemJson.icon = "res:yuanhongqian/image/nme.png";
	  itemJson.iconCurrent = "res:yuanhongqian/image/nme-active.png";
	  itemJson.isSmallTip = true;
	  itemJson.text = "我";	 
	  arr.push(itemJson);

	  json.datas = arr;

	  var menubar1 = document.getElement("menubar1");
	  var menubar2 = document.getElement("menubar2");
	  var menubar3 = document.getElement("menubar3");
	  var menubar4 = document.getElement("menubar4");
	  var btn1 = document.getElement("btn1");
	  var pop =  document.getElement("pop");	 
	  var caidan = document.getElement("caidan");

	  menubar1.loadData(json);
      menubar2.loadData(json);
      menubar4.loadData(json);
	  menubar3.loadData(json);
	  menubar3.on("middleMainClick",function(e,tag){
	  		//1标示已旋转，0标示回归原位
	  	   // myappjs.alert("按钮状态:"+tag);
	  	    var m = tag;
            //console.log("tag:"+tag+"pop.getStyle:"+pop.getStyle("display"));
			if(m==1){
				pop.setStyle("display","block");
				document.refresh();					
			}          
	  	    var jsonData0 = {};
			var animationSet = new Array();
			var transferAni = {};
			transferAni.type = "transfer";
			
			transferAni.duration = 200;
			transferAni.curve = "linear";
           if(m == 0){	    
		    transferAni.delay = 0;
			transferAni.fromY = 0;
			transferAni.toY = 250;
			}
			else{		 
			   transferAni.delay = 0;
			   transferAni.fromY = 250;
			   transferAni.toY = 0;
			}
			
			animationSet.push(transferAni);
			jsonData0.animationSet = animationSet;
				//启动动画	
			caidan.startAnimation(jsonData0,function(){
                  //console.log(caidan); 
                   
					if(m==0){				
						pop.setStyle("display","none");		
					}
					document.refresh();
			});	  
	  });

	  menubar1.on("selectedItem",function(e,index){
          console.log("selectedItem:"+ index);
	  	  myappjs.alert("选择的item的坐标："+index);
	  });

	  btn1.on("click",function(e){
	  	 menubar1.setAttr("index","2");
	  });
	
	});
	
	app.on("orientation",function(e,orientation){	
	});
    ]]>
	</script>
	<style>
       @import url(res:sprite_component/css/sprite.layout.css);
	   @import url(res:sprite_component/css/sprite.color.css); 
	   text{
	   	 text-align: center;
	   } 
    </style>
	<ui>
		<box  class="bg-white full" id="box">		
			<titlebar id="titlebarid" ltext="返回" rtext="刷新" title="menubar"   licon="res:yuanhongqian/image/back1.png"   class="titlebar-hasstatus bg-peter-river" style="title-color:#ffffff;left-color:#ffffff;right-color:#ffffff"/>
			<line />
			<scroll class="flex1">
			    <box style="height:10;" class="full-width"></box>
				<box  class="column-flex-start flex-wrap full-width">
					<button value="测试changeIndex" id="btn1"></button>
					<menubar type="normal" id="menubar1" />
					<box style="height:10;" class="full-width"></box>
					<menubar type="normal" id="menubar2" style="current-color:red;background-color:yellow;tip-color:red;tip-background-color:#324254;icon-margin:4 25 0 25;text-margin:0 0 8 0" index = "1"/>
					<box style="height:10;" class="full-width"></box>
					
					<box class="menubar-out" id="menubaroutid">
					    <line />
						<box class="menubar-out-z" >
							<box class="menubar-item-main-out"  style="background-color:#f9f9f9">						
							</box>
						</box>
						 <menubar id="menubar4" type="middleMain" mainicon="res:yuanhongqian/image/feedback_plus.png" style="main-transfer-y:-8" index = "0"/>
					</box>	
					<box style="height:10;" class="full-width"></box>		
				</box>
				
			</scroll>
			
            <menubar id="menubar3" type="middleMain" mainicon="res:yuanhongqian/image/feedback_plus.png" style="" index = "0"/>
			<box id="pop" class="full absolute" style="background-color:rgba(255, 255, 255, 0.9);display:none">
				 
				<box class="flex1"/>	
				<box id="caidan"  style="margin:0 0 70 0;width:fill_screen"  >
				   <box  class="flex1 row-flex-start" style="height:100;padding:0 10 0 10;margin:10 0 5 0">
					  <box class="flex1 " style="align-items:center;justify-content:center;height:100">	     					 
							 <image src="res:yuanhongqian/image/shuoshuo.png" style="width:70;height:70"/>
							 <text style="margin:10 0 4 0;color:#000000;font-size:14;font-weight:bold;">说说</text>				 				 
					  </box>
					  <box class="flex1 " style="align-items:center;justify-content:center;height:100">	     
							 <image src="res:yuanhongqian/image/zhaopian.png" style="width:70;height:70"/>
							 <text style="margin:10 0 4 0;color:#000000;font-size:14;font-weight:bold;">照片</text>				 				 
					  </box>
					  <box class="flex1 " style="align-items:center;justify-content:center;height:100">	     
							 <image src="res:yuanhongqian/image/shipin.png" style="width:70;height:70"/>
							 <text style="margin:10 0 4 0;color:#000000;font-size:14;font-weight:bold;">视频</text>				 				 
					  </box>
					  <box class="flex1 " style="align-items:center;justify-content:center;height:100">			     
							 <image src="res:yuanhongqian/image/shuiyinxiangji.png" style="width:70;height:70"/>
							 <text style="margin:10 0 4 0;color:#000000;font-size:14;font-weight:bold;">动效相机</text> 
					  </box>
				   </box>
				   <box  class="flex1 row-flex-start" style="height:100;padding:0 10 0 10;;margin:5 0 10 0">
					   <box class="flex1 " style="align-items:center;justify-content:center;height:100">	     
							 <image src="res:yuanhongqian/image/rizhi.png" style="width:70;height:70"/>
							 <text style="margin:10 0 4 0;color:#000000;font-size:14;font-weight:bold;">日志</text>				 				 
					  </box>
					  <box class="flex1 " style="align-items:center;justify-content:center;height:100">			     
							 <image src="res:yuanhongqian/image/qiandao.png" style="width:70;height:70"/>
							 <text style="margin:10 0 4 0;color:#000000;font-size:14;font-weight:bold;">签到</text> 
					  </box>
					  <box class="flex1 " style="align-items:center;justify-content:center;height:100">	     
					  </box>
					  <box class="flex1 " style="align-items:center;justify-content:center;height:100">	     
					  </box>
				   </box>
				   
				</box>
				
			</box>
		</box>
	</ui>
</page>

```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_4.png" style="width:250;"/> 
<img width="250" src="image/fengzhuangzhujian_5.png" style="width:250;"/> 