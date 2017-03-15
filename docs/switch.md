# switch组件

----------

<h2 id="cid_0">说明</h2>

switch控件主要用于开关效果，可作为表单控件使用。该组件封装了change事件，只要该控件内部定义的属性发生变化都会触发该事件（用户自己写的属性改变不会触发change事件）。  

用法：在js里面引入require("switchUI");  

示例：
  
```html
<switch id="switch1" onText="是" offText="否"  checked="false" style="on-background-color:red;margin:8"/>
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
      <td> 参考详细设计文档公共属性章节，包括：<br/>id<br/>style<br/>class</td>
      <td></td>
   </tr>
   <tr>
      <td>onText</td>
      <td>on时的文字;</td>
      <td></td>
   </tr>
   <tr>
      <td>offText</td>
      <td>off时的文字</td>
      <td></td>
   </tr>
   <tr>
      <td>checked</td>
      <td>选择状态true,false (支持js动态修改)，不写默认false</td>
      <td></td>
   </tr>
   <tr>
      <td>readonly</td>
      <td>只读true,false (支持js动态修改)</td>
      <td></td>
   </tr>
   <tr>
      <td>value</td>
      <td>提交的值</td>
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
      <td>尺寸:默认height:36，width:72<br/>定位<br/>外边距<br/>内边距<br/>边框<br/>背景<br/>flexbox布局：align-self</td>
      <td></td>
   </tr>
   <tr>
      <td>on-background-color </td>
      <td>on时候的背景色</td>
      <td></td>
   </tr>
</table>

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
      <td>click()</td>
      <td>模拟点击switch组件，执行click()方法，相当于手动点击了一下switch</td>
      <td></td>
   </tr>
</table>

<h2 id="cid_4">事件</h2>


<table>
   <tr>
      <td>事件</td>
      <td>描述说明</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>box公共事件</td>
      <td>见详细设计文档box章节</td>
      <td></td>
   </tr>
   <tr>
      <td>change</td>
      <td>监听switch属性改变</td>
      <td></td>
   </tr>
</table>  

<h2 id="cid_5">示例</h2>

```html
<page>
    <script>
        <![CDATA[
        var window = require("Window");
        var document = require("Document");
        var ui = require("UI");
        var ListAdapter = require("ListAdapter");
        require("titlebarUI");
        require("buttonUI");
        require("switchUI");
        var console = require("Console");
        var myappjs = require("myapp");
        var screenWidth = window.getScreenWidth();
        var adapter = null;
        window.on("animator", function () {
            var setswitch = document.getElement("setswitch");
            var switch1 = document.getElement("switch1");
            var switch2 = document.getElement("switch2");
            setswitch.on("click", function (e) {
                if (switch1.getAttr("checked") == "true")
                    switch1.setAttr("checked", "false");
                else
                    switch1.setAttr("checked", "true");
            });
            var getswitch = document.getElement("getswitch");
            getswitch.on("click", function (e) {
                myappjs.alert(switch1.getAttr("checked"));
            });

            switch1.on("change", function (e) {
                myappjs.alert("监听change:" + this.getAttr("checked"));
            });

            var setreadonly = document.getElement("setreadonly");
            setreadonly.on("click", function (e) {
                if (switch2.getAttr("readonly") == "true")
                    switch2.setAttr("readonly", "false");
                else
                    switch2.setAttr("readonly", "true");
                document.refresh();

            });
            //titlebar关闭页面
            var title = document.getElement("title");
            title.on("liconClick", function (e) {
                var json = {};
                window.close(json);
            });
            var clickbtn = document.getElement("clickbtn");
            clickbtn.on("click", function (e) {
                switch1.click();
            });
        });
    ]]>
    </script>
    <style>
        @import url(res:sprite_component/css/sprite.layout.css);
        @import url(res:sprite_component/css/sprite.color.css);
        button {
            margin: 5 5 5 5;
        }
        
        text {
            font-size: 15dp;
        }
    </style>
    <ui>
        <box class="white full" id="box">
            <titlebar title="switch控件" class="titlebar-hasstatus" licon="res:yuanhongqian/image/icon.png" style="licon-width:24;licon-height:24"
                id="title" />
            <scroll style="flex:1;width:fill_screen;font-size:12;align-items:start;">
                <box style="flex-direction:row;flex-wrap:wrap;align-items:center;">
                    <switch id="switch1" onText="是" offText="否" checked="false" style="on-background-color:red;margin:8" />
                    <button value="设置switchy" id="setswitch" />
                    <button value="得到switch" id="getswitch" />
                </box>
                <switch onText="yes" offText="no" checked="true" style="on-background-color:green" />
                <switch onText="on" offText="off" checked="true" style="on-background-color:blue;width:100" />
                <switch onText="yes" offText="no" checked="true" style="on-background-color:#000000;height:50;width:100;font-size:20" />
                <box style="flex-direction:row;flex-wrap:wrap;align-items:start;">
                    <switch onText="是" offText="否" id="switch2" checked="true" style="margin:8" />
                    <switch onText="是" offText="否" checked="true" readonly="true" style="margin:8" />
                    <button value="设置readonly" id="setreadonly" />
                    <button value="模拟点击第一个switch" id="clickbtn" />
                </box>
            </scroll>
        </box>
    </ui>
</page>
```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_13.png" style="width:250;"/> 