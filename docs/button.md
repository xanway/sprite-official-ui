# button组件

----------

<h2 id="cid_0">说明</h2>

button组件主要用于按钮形式布局，为方便开发者使用，其封装一些常用样式包括：submit cancel outline 注意：混合使用时outline必需在最后。

内置样式需要用builtInClass属性    

用法：在使用button组件的时候需要在js里面引入 require("buttonUI");    
 
示例代码：  

```html
<button class="margin4 radius8"  builtInClass="submit outline"  value="提交"></button>
``` 


<h2 id="cid_1">属性</h2>

本节目录：


> [公共属性](#sx_0)	
> 
> [builtInClass	使用内置样式](#sx_1)
>
>[value	按钮文字（可以通过js修改）](#sx_2)
>
>[tip  小气泡数字（可以通过js修改）	](#sx_3)
>
>[licon	按钮上左侧的图片（可以通过js修改）](#sx_4)
>
>[ricon	按钮上右侧的图片（可以通过js修改）](#sx_5)
>
>[readonly	只读（可以通过js修改）](#sx_6)
>
>[loading  加载等待](#sx_7)


<span id="sx_0">**公共属性**</span>  

[参见公共属性章节](https://gitdocument.exmobi.cn/sprite-begin/ggsx.html)，包括：id、style、class；

<span id="sx_1">**builtInClass**</span>

<code>使用内置样式</code>

submit cancel outline 注意：混合使用时outline必需在最后


<span id="sx_2">**value**</span>

<code>按钮文字</code> 

按钮文字（可以通过js修改）

示例：

```javascirpt
var btn = document. getElement(“buttonid”);
btn.setAttr(“value”,”按钮”);
```

<span id="sx_3">**tip**</span>

<code>小气泡数字</code> 

小气泡数字（可以通过js修改）


<span id="sx_4">**licon**</span>

<code>按钮上左侧的图片</code>  

按钮上左侧的图片（可以通过js修改）


<span id="sx_5">**ricon**</span>

<code>按钮上右侧的图片</code>  

按钮上右侧的图片（可以通过js修改）


<span id="sx_6">**readonly**</span>

<code>只读属性</code> 

只读（可以通过js修改）


<span id="sx_7">**loading**</span>

<code>加载等待</code> 

加载等待，取值true和false （可以通过js修改）

一般用于点击按钮时候的等待效果，btn.setAttr("loading”,"true");显示等待图标，过程执行结束后再调用btn.setAttr("loading",”false");隐藏等待图标


<h2 id="cid_2">样式</h2>

**公共样式**  

[参见公共样式章节](https://gitdocument.exmobi.cn/sprite-begin/ggys.html)，包括：  

> 尺寸：height默认40;
> 
> 定位
> 
> 内边距：默认padding:0 8 0 8;
> 
> 外边距
> 
> 边框：边框颜色默认#549FF7;
> 
> 背景：默认#549FF7;
> 
> flexbox布局：align-self，flex


**color**	

<code>按钮文字颜色</code>

按钮文字颜色，默认#ffffff （可以通过js修改）	

```javascirpt
var btn = document. getElement("buttonid");
btn.setStyle("color","red");
```

**color-click**	

<code>按钮文字点击颜色</code>

按钮文字点击颜色 默认#ffffff	


**border-color-click**	

<code>边框点击颜色</code>

边框点击颜色，默认#295b9d	


**background-color-click**	

<code>按钮背景点击色</code>

按钮背景点击色，点击按钮会渐变到该色值，默认#295b9d。

	
**tip-color**	

<code>小气泡字体颜色</code>

小气泡字体颜色（可以通过js修改），默认#ffffff	同color


**tip-background-color**	

<code>小气泡背景颜色</code>

小气泡背景颜色（可以通过js修改），当按钮样式有outline是背景色是red，其他样式基于按钮本身背景色半透明	


**font-size**	

<code>按钮文字字体大小</code>

按钮文字字体大小 （可以通过js修改），默认大小16dp


**licon-width**

<code>按钮左侧图片宽度</code>

按钮左侧图片宽度（可以通过js修改），默认24	 


**licon-height**  

<code>按钮左侧图片高度</code>

按钮左侧图片高度（可以通过js修改）,默认24	


**ricon-width**

<code>按钮右侧图片宽度</code>

按钮右侧图片宽度（可以通过js修改）,默认24
	
**ricon-height** 

<code>按钮右侧图片高度</code>

按钮右侧图片高度（可以通过js修改）,默认24




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


**click():void**

<code>模拟点击一次按钮</code>

可以通过js方式，模拟点击一次按钮

参数：无

返回值：无

示例：

```javascript
var btn = document. getElement("buttonid");
btn.click();
```

<h2 id="cid_4">事件</h2>

**box所有事件**

由box封装而成，具有box所有事件，[具体见box组件章节](https://gitdocument.exmobi.cn/sprite_advanced/box.html#cid_2)。

**change**  

<code>当按钮属性通过js修改发生变化时会触发</code>

event对象包括：  
 
type：事件类型，字符串类型，固定值：change；  

target：触发事件的目标组件，dom对象；  

timestamp：事件触发的时间戳,单位毫秒，数字类型；

示例：

```javascript
var btn = document.getElement("buttonid");
btn.on("change",function(e){
//to do
});
```

<h2 id="cid_5">示例</h2>

```html
<page>
	<script>
		<![CDATA[ 
    	var window = require("Window");
		var document = require("Document");
		var ui = require("UI");
		var console = require("Console");
		//引用自定义UI模板库
		//require("componentUI"); 
		require("buttonUI");
		require("titlebarUI");
		var myappjs = require("myapp");
		var screenWidth = window.getScreenWidth();
		window.on("loaded", function () {
			var titlebarid = document.getElement("titlebarid");
			var btn0 = document.getElement("btn0");
			var btn1 = document.getElement("btn1");
			var btn2 = document.getElement("btn2");
			var btn3 = document.getElement("btn3");
			var btn4 = document.getElement("btn4");
			var btn5 = document.getElement("btn5");
			var btn6 = document.getElement("btn6");
			var btn7 = document.getElement("btn7");
			var btn8 = document.getElement("btn8");
			titlebarid.on("ltextClick", function (e) {
				var tag = e.target;
				var json = {};
				window.close(json);
			});
			titlebarid.on("liconClick", function (e) {
				var tag = e.target;
				var json = {};
				window.close(json);
			});
			btn1.on("click", function (e) {
				// myappjs.alert("触发点击事件");
				btn1.setAttr("value", "11111111");
			});
			btn1.on("touchDown", function (e) {
				// myappjs.alert("触发点击事件");
				var jsondata = { "content": "触发touchDown事件", "duration": "1" };
				ui.toast(jsondata);
			});
			btn1.on("touchUp", function (e) {
				// myappjs.alert("触发点击事件");
				var jsondata = { "content": "触发touchUp事件", "duration": "1" };
				ui.toast(jsondata);
			});
			btn2.on("click", function (e) {

				btn2.setStyle("font-size", "16");
				btn2.setStyle("color", "#000000");
				btn2.setStyle("background-color", "red");
			});
			btn3.on("click", function (e) {
				btn3.setAttr("tip", 10);
			});

			btn4.on("click", function (e) {
				btn4.setStyle("tip-color", "red");
				btn4.setStyle("tip-background-color", "blue");

			});

			btn5.on("click", function (e) {
				console.log("2224442");
				btn5.setAttr("licon", "../image/touxiang4.png");
			});
			btn6.on("click", function (e) {
				if (btn6.getAttr("readonly") != "true") {
					btn6.setAttr("readonly", "true");
				}
			});

			btn7.on("click", function (e) {
				btn0.click();
			});

			btn0.on("click", function (e) {
				// myappjs.alert("监听到了按钮1的点击事件");
				var jsondata = { "content": "监听到了按钮1的点击事件", "duration": "1" };
				ui.toast(jsondata);

			});
			btn1.on("change", function (e) {
				// myappjs.alert("触发change事件"+e.type);
				var jsondata = { "content": "触发change事件", "duration": "1" };
				ui.toast(jsondata);
			});
			btn8.on("click", function (e) {
				btn8.setAttr("loading", "true");
			});
			var bkbtn = document.getElement("bkbtn");
			console.log(bkbtn);
		});	
    ]]>
	</script>
	<style>
		@import url("spriteColor");
		@import url("spriteLayout");
	</style>
	<ui>
		<box class="bg-white full" id="box">

			<titlebar id="titlebarid" ltext="返回" title="按钮组件" licon="../image/back1.png" class="titlebar-hasstatus bg-peter-river" style="title-color:#ffffff;left-color:#ffffff"
			/>
			<line />
			<scroll class="flex1">


				<box class="title">
					<text class="title-text">普通按钮</text>
				</box>
				<box id="boxid" class="row-flex-start flex-wrap full-width">
					<button id="btn0" class="margin4" value="默认样式按钮"></button>
					<button id="btn1" class="margin4 radius8" value="点击修改按钮文字"></button>
					<button id="btn2" class="margin4 radius8" style="font-size:24" value="修改文字大小和颜色"></button>
					<button class="margin4 radius8" builtInClass="submit" value="提交"></button>
					<button class="margin4 radius8" builtInClass="cancel" value="取消"></button>
					<button class="margin4 radius8" readonly="true" value="禁用普通按钮"></button>
					<button class="margin4 radius8" id="btn6" value="点击设置只读"></button>
					<button value="自定义样式" style="color:red;background-color:green;background-color-click:blue;color-click:yellow"></button>
				<button id="btn7" value="模拟点击第一个按钮"></button>
				</box>
				<box class="title">
					<text class="title-text">边框按钮</text>
				</box>
				<box id="boxid" class="row-flex-start flex-wrap full-width">
					<button id="bkbtn" class="margin4" builtInClass="outline" value="按钮"></button>
					<button class="margin4 radius8" builtInClass="outline" value="按钮"></button>
					<button class="margin4 radius8" builtInClass="submit outline" value="提交"></button>
					<button class="margin4 radius8" builtInClass="cancel outline" value="取消"></button>
					<button class="margin4 radius8" builtInClass="outline" readonly="true" value="禁用普通按钮"></button>
					<button value="自定义样式" class="margin4 radius8 " style="color:red;border-color:red;background-color-click:blue;border-color-click:blue;color-click:yellow"
						builtInClass="outline"></button>
				</box>
				<box class="title">
					<text class="title-text">按钮气泡</text>
				</box>
				<box id="boxid" class="row-flex-start flex-wrap full-width">

					<button id="btn3" class="flex1 margin4 radius8" value="点击修改气泡数字" tip="190"></button>
					<button id="btn4" class="flex1 margin4 radius8" builtInClass="outline" value="点击修改气泡颜色" tip="19"></button>
				</box>
				<box class="title">
					<text class="title-text">圆按钮</text>
				</box>
				<box id="boxid" class="row-flex-start flex-wrap full-width">
					<button class="margin4 radius8 round" value="1"></button>
					<button class="margin4 radius8 round" builtInClass="submit" value="2"></button>
				</box>
				<box class="title">
					<text class="title-text">图标按钮</text>
				</box>
				<box id="boxid" class="row-flex-start flex-wrap full-width">

					<button loading="true" id="btn5" licon="../image/new_select.png" ricon="../image/touxiang4.png" class="margin4 radius8 "
						style="licon-width:30" value="点击修改图标" tip="109"></button>
						<button licon="../image/new_select.png" class="margin4 radius8 outline" value="普通按钮" tip="109"></button>
				</box>
				<box class="title">
					<text class="title-text">Loading按钮</text>
				</box>
				<box id="boxid" class="row-flex-start flex-wrap full-width">
					<button class="margin4 radius8 " loading="true" value="普通按钮"></button>
					<button id="btn8" class="margin4 radius8 outline" loading="false" value="普通按钮"></button>
				</box>
			</scroll>
		</box>
	</ui>
</page>

```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_2.png" style="width:250;"/> 