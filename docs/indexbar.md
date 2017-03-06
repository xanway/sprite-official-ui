<h1>indexbar组件</h1>

----------

## 说明  

inderbar组件主要用于字母导航条，类似于手机通讯录字母条的效果，通过触摸滑动字母条可以快速检索到对应字母的内容，该组件一般和list组件一起使用，组件本身只提供字母条的样式效果。该控使用绝对定位布局，默认定位在页面右侧。由于是绝对定位，在使用的时候建议把该控件放在页面布局代码的最下面，否者会被其他控件遮罩。  

用法：在js里面引入require("inderbarUI");  

示例：  
  
```html
<indexbar id="indexbarid"  ispop="true"/>
``` 


## 属性  

<table>
   <tr>
      <td>属性</td>
      <td>描述说明</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>公共属性</td>
      <td>参见公共属性章节，包括：<br/>id<br/>style<br/>class<br/></td>
      <td></td>
   </tr>
   <tr>
      <td>ispop</td>
      <td>是否弹出pop，取值true,false，默认true</td>
      <td></td>
   </tr>
</table>


## 样式  

<table>
   <tr>
      <td>样式</td>
      <td>描述说明</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>box公共样式</td>
      <td>尺寸:默认width:30;<br/>定位:position:absolute;top:0;right: 0;<br/>bottom: 0;<br/>外边距<br/>内边距<br/>边框<br/>背景<br/>
</td>
      <td></td>
   </tr>
   <tr>
      <td>pop-background-color</td>
      <td>pop窗口背景色; 默认#549FF7</td>
      <td></td>
   </tr>
   <tr>
      <td>pop-text-color</td>
      <td>pop 窗口中文字颜色，默认#ffffff</td>
      <td></td>
   </tr>
   <tr>
      <td>indexbar-text-color</td>
      <td>字母条的文字颜色</td>
      <td></td>
   </tr>
</table>

## js方法 

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
      <td>loadData(arr)</td>
      <td>数组格式["a","b","c"];如果不传值默认[A-Z]</td>
      <td></td>
   </tr>
</table>

## 事件  

<table>
   <tr>
      <td>事件</td>
      <td>描述说明</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>changeIndex</td>
      <td>参数(e ,text) text返回对应字母</td>
	<td></td>
   </tr>
</table>  

## 示例  

该示例和list组件混合使用，list需要用到section。

```html
	<page>
    <script><![CDATA[
    var index = 1;
    var window = require("Window");
    var document = require("Document");
    var ui = require("UI");           
    var console = require("Console");
    var app = require("App");
    var ListAdapter = require("ListAdapter");

    require("titlebarUI");
    require("indexbarUI");
    var myappjs = require("myapp");
    var screenWidth = window.getScreenWidth();
    
   var datas = new Array();
   var adapter = null;
   var list = null;
   
    window.on("loaded",function(){
        var titlebarid = document.getElement("titlebarid");
        //关闭页面
        titlebarid.on("liconClick",function(e)
        {
            var json = {};
            window.close(json);
        });
        titlebarid.on("rtextClick",function(e){

             var zmarr = ["热门","A","B","C","D","E"];
            indexbarid.loadData(zmarr);
        });

        var indexbarid = document.getElement("indexbarid"); 
        list = document.getElement("list");

        indexbarid.on("changeIndex",function(e,zm){

          for(var i=0;i<datas.length;i++){
                 if(zm == datas[i].title){
                    
                   var json = {};
                   json.sectionIndex = i;
                   json.index = 0;
                   json.animated = false;
                   list.scrollToPosition(json);

                    break;
                 }
          }
        });
        indexbarid.loadData();
        initAdapter();
        loadData();
        adapter.refresh();      
        
    });
 
    app.on("orientation",function(e,orientation){
        var screenWidth = window.getScreenWidth();
        
    });

    function initAdapter()
    {
        if(adapter == null)
        {
            adapter = new ListAdapter();
            adapter.on("getCellId",function(e,position,sectionindex)
            {
                var sectionJson = datas[sectionindex];
                var data = sectionJson.cells[position];
                return data.type;
            });
            adapter.on("getView",function(e,position,sectionindex)
            {
               var sectionJson = datas[sectionindex];
                var data = sectionJson.cells[position];
                var text = e.target.getElement("text");
                text.setText(data.text);
              //设置列表点击背景色
                var boxObj = e.target;
                var event = boxObj.getOn("touchUp");
                if(event.length == 0){
                    boxObj.on("touchDown",function(e)
                    {
                        e.target.setStyle("background-color","#dddddd");
                    });
                    boxObj.on("touchUp",function(e)
                    {
                        e.target.setStyle("background-color","transparent");
                    });
                }
            });
            adapter.on("getCount",function(e,sectionindex)
            {
                   var sectionJson = datas[sectionindex];
                    return sectionJson.cells.length;
            });
            adapter.on("getItem",function(e,position,sectionindex)
            {
                var sectionJson = datas[sectionindex];
                    return sectionJson.cells[position];
            });
            adapter.on("getSectionCount", function(e) {
                    return datas.length;
              });
            adapter.on("getSectionText", function(e, sectionindex) {
                    var text = "";
                    var sectionJson = datas[sectionindex];
                    text = sectionJson.title+" "+sectionindex;
                    return text;
              });
            list.setAdapter(adapter);
         }
    }
    function loadData()
    {
        var sectionJson = {};
        sectionJson.title = "A";
        sectionJson.cells = new Array();
        for(var i=0;i<20;i++){
          json = {};
          json.type   = "cell";      
          json.text   = "按钮"; 
          sectionJson.cells.push(json);     
      }
        datas.push(sectionJson); 
       var sectionJson = {};
        sectionJson.title = "B";
        sectionJson.cells = new Array();
        for(var i=0;i<30;i++){
          json = {};
          json.type   = "cell";
          json.text   = "titlebar导航";
          sectionJson.cells.push(json);
       }
         datas.push(sectionJson); 
        var sectionJson = {};
        sectionJson.title = "C";
        sectionJson.cells = new Array();
        for(var i=0;i<30;i++){
           json = {};
            json.type   = "cell";       
            json.text   = "tabbar样式";       
            sectionJson.cells.push(json);
       }  
       datas.push(sectionJson);  
        var sectionJson = {};
        sectionJson.title = "D";
        sectionJson.cells = new Array();
        for(var i=0;i<30;i++){
           json = {};
            json.type   = "cell";       
            json.text   = "menubar样式";       
            sectionJson.cells.push(json);
       }          
datas.push(sectionJson); 
        var sectionJson = {};
        sectionJson.title = "E";
        sectionJson.cells = new Array();
        for(var i=0;i<30;i++){
           json = {};
            json.type   = "cell";       
            json.text   = "menubar23234样式";       
            sectionJson.cells.push(json);
       }  

        datas.push(sectionJson); 
    }
    ]]>
    </script>
    <style>
       @import url(res:sprite_component/css/sprite.layout.css);
       @import url(res:sprite_component/css/sprite.color.css);  
        .listcell
       {
            flex-direction:row;
            justify-content:flex-start;
            flex-wrap:nowrap;
            height:60;
            align-items:center;
            background-color:transparent;
       }
    </style>
    <ui>
        <box  class="full" style="" id="box">  
           <titlebar id="titlebarid" licon="res:yuanhongqian/image/icon.png" title="indexbar滑动条索引" style="licon-width:24;licon-height:24"   class="titlebar-hasstatus" rtext="修改字母条"/> 
            <line />
          <box class="flex1" id="bodyid">
              <list id="list" style="flex:1" >
                <cell id="cell" >
                   <box class="listcell">         
                    <text id="text" style="flex:1;color:#333333;text-align:left;margin:8;font-size:17"></text>
                   </box>      
                   <line style="line-size:1;" /> 
               </cell>
               <cell id="cell_section" >
                   <box class="listcell" style="background-color:#dddddd;height:30">         
                    <text id="text" style="flex:1;color:#333333;text-align:left;margin:8;font-size:17"></text>
                   </box>      
                   <line style="line-size:1;" /> 
               </cell>
            </list>
            <indexbar id="indexbarid"  ispop="true"/>          
         </box>
        </box>
    </ui>
</page>

```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_33.png" style="width:250;"/> 
<img width="250" src="image/fengzhuangzhujian_34.png" style="width:250;"/> 