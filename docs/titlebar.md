# titlebar组件 

[说明](#header1)  
 
[属性](#header2) 

[样式](#header3) 
 
[js方法](#header4) 

[事件](#header5) 

[示例](#header6) 

<br/>
<h2 id="header1">说明</h2>
titlebar主要用于页面的标题栏展示，为方便开发者布局，封装titlebar-hasstatus 含有系统状态栏高度样式可以直接使用，普通样式是不含状态栏高度的。在使用建议放在垂直布局容器中，宽度会自动填满父容器，如果放在水平布局容器中一定要给出width。

用法：在js里面引入require("titlebarUI");

示例，含有titlebar-hasstatus
 
 
```html
	<titlebar  id="title7" licon="res:yuanhongqian/image/touxiang.png" ricon="res:yuanhongqian/image/gou.png" style="background-color:#549FF7;" class="titlebar-hasstatus"  />
``` 

<br/>
<h2 id="header2">属性</h2>
<table><tr><td>属性</td><td>描述说明</td><td>示例</td></tr><tr><td>公共属性</td><td>参见公共属性章节，包括：<br/>id；<br/> style；<br/>class；</td><td></td></tr><tr><td>title</td><td>title：标题 (通过js可以修改)；</td><td>var title = document.getElement(“titleid”);<br/>title.setAttr(“title”,”标题”);</td></tr><tr><td>licon</td><td>licon：左边图片地址(通过js可以修改)；支持res:</td><td>同上</td></tr><tr><td>ltext</td><td>ltext: 左边文字(通过js可以修改)；</td><td>同上</td></tr><tr><td>rtext</td><td>rtext: 右边文字(通过js可以修改)；</td><td>同上</td></tr><tr><td>ricon</td><td>ricon：右边图片地址(通过js可以修改)；支持res:</td><td>同上</td></tr><tr><td>riconsnd</td><td>riconsnd：右边第二张图片地址(通过js可以修改)；支持res:</td><td>同上</td></tr></table>

<br/>
<h2 id="header3">样式</h2>

<table>
   <tr><td>样式</td><td>描述说明</td><td>示例</td></tr>
   <tr><td>box公共样式</td><td>尺寸:height默认44;<br/>定位;外边距;<br/>边框;<br/>背景:默认#f9f9f9;<br/>flexbox布局：align-self，flex</td><td></td></tr>
   <tr><td>title-color</td><td>title-color:标题颜色(通过js可以修改), 默认色值#000000；</td><td>var title = document.getElement(“titleid”);<br/>title.setStyle(“title-color”,”red”);</td></tr>
   <tr><td>left-color</td><td>left-color:左边为文字颜色(通过js可以修改)；默认色值#549FF7</td><td>同title-color</td></tr>
   <tr><td>right-color</td><td>right-color:右边文字颜色(通过js可以修改)；默认色值#549FF7</td><td>同title-color</td></tr>
   <tr><td>licon-width</td><td>licon-width:左边图片宽度(通过js可以修改)；默认宽度30dp</td><td>同title-color</td></tr>
   <tr><td>licon-height</td><td>licon-height:左边图片高度(通过js可以修改)；默认高度30dp</td><td>同title-color</td></tr>
   <tr><td>ricon-width</td><td>ricon-width:右边图片宽度(通过js可以修改)；默认宽度30dp</td><td>同title-color</td></tr>
   <tr><td>ricon-height</td><td>ricon-height:右边图片高度(通过js可以修改)；默认高度30</td><td>同title-color</td></tr>
   <tr><td>riconsnd-width</td><td>riconsnd-width:右边第二图片宽度(通过js可以修改)；默认高度30</td><td>同title-color</td></tr>
   <tr><td></td></tr>
</table>

<br/>
<h2 id="header4">js方法</h2>
<table>
   <tr><td>Js方法</td><td>描述说明</td><td>示例</td></tr>
   <tr><td>box公共方法</td><td>见设计文档box章节（不包括容器类Dom节点操作）</td><td></td></tr>
   <tr><td>setTitleContent('自定义内容xml') </td><td>根据xml字符串自定义内容；把内容放入titlebar的title中间区域。<br/>注：标签要注入到组件内部，这里注入的标签里面如果有图片，路径不能是相对路径，否则组件内部会认为是基于组件目录的相对路径，所以只能写res:绝对路径</td><td>var xmlstr2 = '<button licon=”res:yuanhongqian/image/1.png” id="btn1" class="margin4 radius8 submit"  value="123"/>';<br/>var title8= document.getElement("title8");  title8.setTitleContent(xmlstr2);</td></tr>
   <tr><td>getDomById("id")</td><td>根据id得到自定内容中控件的dom;</td><td>//btn1是自定义内容中按钮组件的id。<br/>var btn1 = title8.getDomById("btn1");</td></tr>
  
</table>

<br/>
<h2 id="header5">事件</h2>
<table>
   <tr>
      <td>事件</td>
      <td>描述说明</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>ltextClick</td>
      <td>监听左侧文字点击事件；</td>
      <td>var titlebarid = document.getElement("titlebarid");<br/>titlebarid.on("ltextClick",function(e) {var tag = e.target;<br/>var json = {};<br/>window.close(json);  });</td>
   </tr>
   <tr>
      <td>rtextClick </td>
      <td>监听右侧文字点击事件；</td>
      <td>同上</td>
   </tr>
   <tr>
      <td>liconClick</td>
      <td>监听左侧图片点击事件；</td>
      <td>同上</td>
   </tr>
   <tr>
      <td>riconClick</td>
      <td>监听右侧图片点击事件；</td>
      <td>同上</td>
   </tr>
   <tr>
      <td>riconsndClick</td>
      <td>监听右侧第二张图片点击事件；</td>
      <td>同上</td>
   </tr>
</table>

<br/>
<h2 id="header6">示例</h2>
```html
	<page>
	<script><![CDATA[
    var window = require("Window");
    var document = require("Document");
    var ui = require("UI");     
    var console = require("Console");
    //引用自定义UI模板库
    //require("componentUI");
    require("titlebarUI");
    require("buttonUI"); 
    var myappjs = require("myapp");
    var screenWidth = window.getScreenWidth(); 
    window.on("loaded",function(){
        //关闭页面
	    var titlebarid = document.getElement("titlebarid");
	    titlebarid.on("ltextClick",function(e) {
	    	var tag = e.target;
	        var json = {};
	        window.close(json);      
	    });

	    titlebarid.on("liconClick",function(e) {
	    	var tag = e.target;
	        var json = {};
	        window.close(json);      
	    });
    	
        var titlebartest = document.getElement("titlebartest");
	    titlebartest.on("ltextClick",function(e){ 
	        console.log(titlebartest);
	    	myappjs.alert("点击了左侧文字"+ this.getAttr("title"));
	    	this.setAttr("title","22222");    	
	    });

	    titlebartest.on("rtextClick",function(e){ 
	    	this.setAttr("title","22222");
	    	myappjs.alert("点击了右侧文字");
	    });

	     titlebartest.on("liconClick",function(e){
	    	myappjs.alert("点击了左侧图片");
	    });

	     titlebartest.on("riconClick",function(e){
	    	myappjs.alert("点击了右侧图片");
	    });

	     titlebartest.on("riconsndClick",function(e){
	    	myappjs.alert("点击了右侧第二张图片");
	    });

       //定义自定义内容
    var xmlstr = '<box  class="radius8 row-flex-center align-items-stretch" style="height:30dp;width:120dp;border-color:#ffffff;border-width:1dp" >'
		+'<box id="xiaoxi" class="bg-white flex1 row-flex-center" ><text  class="peter-river">消息</text></box>'
		+'<box id="dianhua" class="bg-transparent flex1 row-flex-center"><text  class="white">电话</text></box>'
		+'</box>';
	  var title6 = document.getElement("title6");					 
      //这个一定要先执行
	  title6.setTitleContent(xmlstr);
	 
	  title6.getDomById("xiaoxi").on("click",function(e){
	  	// myappjs.alert("点击了xiaoxi");
         var classes = this.getClassStyle();         
         	this.setClassStyle("bg-white flex1 row-flex-center");
         	this.getFirstChild().setClassStyle("peter-river");
         	title6.getDomById("dianhua").setClassStyle("bg-transparent flex1 row-flex-center");
            title6.getDomById("dianhua").getFirstChild().setClassStyle("white"); 
	  });

	  title6.getDomById("dianhua").on("click",function(e){
	  	 //myappjs.alert("点击了dianhua");	  
         	this.setClassStyle("bg-white  flex1 row-flex-center");
         	this.getFirstChild().setClassStyle("peter-river");
         	title6.getDomById("xiaoxi").setClassStyle("bg-transparent flex1 row-flex-center");
            title6.getDomById("xiaoxi").getFirstChild().setClassStyle("white");
         
	  });

	  var title7 = document.getElement("title7");
	  var xmlstr = '<box id="search"   class="row-flex-center align-items-center flex1" style="height:30dp;border-radius:15;background-color:#f9f9f9;margin:0 70 0 70" >'
			+'<image style="width:16;height:16"  src="res:yuanhongqian/image/icon_search.png" />'
			+'<text class="margin4" style="font-size:14dp;color:#999999">搜索</text>'
			+'</box>';

	  //这个一定要先执行
	  title7.setTitleContent(xmlstr);
	  title7.getDomById("search").on('click',function(e){
	  	 myappjs.alert("点击了搜索");
	  });

      var xmlstr2 = '<button id="btn1" class="margin4 radius8 submit"  value="123"/>';
	  var title8 = document.getElement("title8");
	  title8.setTitleContent(xmlstr2);
	  title8.getDomById("btn1").on('click',function(e){
	  	 myappjs.alert("测试放入自定义控件");
	  });

    });
    ]]>
	</script>
	<style>
       @import url(res:sprite_component/css/sprite.layout.css);
	   @import url(res:sprite_component/css/sprite.color.css);  	   
    </style>
	<ui>
		<box  class="bg-white full" id="box">
		  <titlebar id="titlebarid" ltext="返回" title="titlebar"   licon="res:yuanhongqian/image/back1.png"   class="titlebar-hasstatus bg-peter-river" style="title-color:#ffffff;left-color:#ffffff"/>
		  <line />			
		 <scroll class="flex1">        			
			<box id="boxid" class="row-flex-start flex-wrap full-width">
                <titlebar id="titlebartest" title="测试控件事件" ltext="返回" rtext="菜单"   licon="res:yuanhongqian/image/bx.png"  ricon="res:yuanhongqian/image/lxr.png" riconsnd="res:yuanhongqian/image/cjr.png"/>

                <box style="height:10;" class="full-width"></box>
				<titlebar  title="标题1"/>
				<box style="height:10;" class="full-width"></box>
				<titlebar title="首页" ltext="返回" rtext="菜单" />
				<box style="height:10;" class="full-width"></box>
				<titlebar title="首页2"  rtext="菜单" licon="res:yuanhongqian/image/bx.png" />
				 <box style="height:10;" class="full-width"></box>
				 <titlebar title="首页3"   licon="res:yuanhongqian/image/bx.png"  ricon="res:yuanhongqian/image/ss.png"/>

				 <box style="height:10;" class="full-width"></box>
				 <titlebar ltext="返回" title="首页4"   licon="res:yuanhongqian/image/back1.png"  ricon="res:yuanhongqian/image/gou.png" class="bg-peter-river" style="title-color:#ffffff;left-color:#ffffff"/>
				 
				 <box style="height:10;" class="full-width"></box>
				 <titlebar id="title5"  title="首页5"   licon="res:yuanhongqian/image/bx.png"  ricon="res:yuanhongqian/image/lxr.png" riconsnd="res:yuanhongqian/image/cjr.png"/>

				 <box style="height:10;" class="full-width"></box>
				 <titlebar id="title6"  title="首页6"   licon="res:yuanhongqian/image/touxiang.png"  ricon="res:yuanhongqian/image/gou.png" class="bg-peter-river" style="title-color:#ffffff;left-color:#ffffff"/>				 
				 <box style="height:10;" class="full-width"></box>				 
				 <box style="height:10;" class="full-width"></box>
				 <titlebar  id="title7" licon="res:yuanhongqian/image/touxiang.png" ricon="res:yuanhongqian/image/gou.png" style="background-color:#549FF7;" class="titlebar-hasstatus"  />

				  <box style="height:10;" class="full-width"></box>
				 <titlebar  id="title8" licon="res:yuanhongqian/image/touxiang.png" ricon="res:yuanhongqian/image/gou.png" style="background-color:#549FF7;" class="titlebar-hasstatus"  />			
			</box>
			</scroll>
		</box>
	</ui>
</page>
```
