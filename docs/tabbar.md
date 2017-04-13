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

<table>
   <tr>
      <td>属性</td>
      <td>描述说明</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>公共属性</td>
      <td>参见公共属性章节，包括：<br/>id;<br/>style;<br/>class;</td>
      <td></td>
   </tr>
   <tr>
      <td>bindid</td>
      <td>绑定slider控件的id，注意只能是slider控件,绑定后通过设置slider的index可以切换tabbar</td>
      <td></td>
   </tr>
</table>

 
<h2 id="cid_2">样式</h2>

<table>
   <tr>
      <td>样式</td>
      <td>描述说明</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>box公共样式</td>
      <td>尺寸:默认height:44;<br/>定位;<br/>外边距;<br/>内边距;<br/>边框;<br/>背景;<br/>flexbox布局:align-self，flex</td>
      <td></td>
   </tr>
   <tr>
      <td>color</td>
      <td>文字颜色</td>
      <td></td>
   </tr>
   <tr>
      <td>current-color</td>
      <td>选中的颜色（包含文字和滑动条颜色）</td>
      <td></td>
   </tr>
</table>

注：除了box公共样式以外，其他菜单样式通过js修改后，需重新执行loadData()才生效。  

<h2 id="cid_3">js方法</h2>

<table>
   <tr>
      <td>Js方法</td>
      <td>描述说明</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>box公共方法</td>
      <td>见设计文档box章节（不包括容器类Dom节点操作）</td>
      <td></td>
   </tr>
   <tr>
      <td>loadData(json)</td>
      <td>格式json.datas数组，属性如下:var itemJson = {}; itemJson.text = "头条";  </td>
   </tr>
</table>


<h2 id="cid_4">事件</h2>

无


<h2 id="cid_5">示例</h2>

```html
<page>
    <script><![CDATA[
    var index = 1;
    var window = require("Window");
    var document = require("Document");
    var ui = require("UI");           
    var console = require("Console");
     var app = require("App");

    require("titlebarUI");
    require("tabbarUI");
    var myappjs = require("myapp");
   
   
    window.on("loaded",function(){
          //关闭页面
        var titlebarid = document.getElement("titlebarid");
        var  tabbarid1 = document.getElement("tabbarid1");
        
        var  sliderid = document.getElement("sliderid");
        titlebarid.on("liconClick",function(e)
        {
            var json = {};
            window.close(json);      
        });
        titlebarid.on("ltextClick",function(e)
        {
            var json = {};
            window.close(json);      
        });

        titlebarid.on("rtextClick",function(e)
        {
            sliderid.setAttr("index",3);
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
        tabbarid1.loadData(json);
        sliderid.on("pageSelected",function(e,position){
              
            var jsondata = {"content":position,"duration":"1"};
            ui.toast(jsondata);
       
      });
    
 });
    
    ]]>
    </script>
    <style>
       @import url("spriteLayout");
       @import url("spriteColor");  
      .full
        {
            width:fill_screen;
            height:fill_screen;
        }
   
    </style>
    <ui>
        <box  class="full" style="background-color:#ececec" id="box">           
            <titlebar id="titlebarid" ltext="返回" rtext="设置索引" title="tabbar"   licon="res:yuanhongqian/image/back1.png"   class="titlebar-hasstatus bg-peter-river" style="title-color:#ffffff;left-color:#ffffff;right-color:#ffffff"/>
            <line />
                    
            <tabbar id="tabbarid1" bindid="sliderid" style="color:#909090;background-color: #ffffff;current-color:rgb(255, 0, 0)"/>
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
                  
        </box>
    </ui>
</page>

```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_9.gif" style="width:250;"/> 
