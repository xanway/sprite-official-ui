# checkbox组件

----------

<h2 id="cid_0">说明</h2>

checkbox组件主要用于多选场景，除了自身样式外，开发者还可以自己设置图片当做状态样式，该组件可作为表单控件使用。该组件封装了change事件，只要该控件内部定义的属性发生变化都会触发该事件（用户自己写的属性改变不会触发change事件）。  

用法：在js里面引入require("checkboxUI");  

示例：
  
```html
<checkbox id="checkbox1"   checked="true" caption="男" />
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
      <td>参考详细设计文档公共属性章节，包括：<br/>id<br/>style<br/>class</td>
      <td></td>
   </tr>
   <tr>
      <td>checked</td>
      <td>选择状态，true选中，false 未选中(通过js可以修改), 注意通过js设置checked如果存在同组的radio不具备排斥性，如需通过js控制可以调用click()方法，模拟radio点击；不写默认false</td>
      <td></td>
   </tr>

   <tr>
      <td>caption</td>
      <td>文字内容(通过js可以修改)；</td>
      <td></td>
   </tr>
   <tr>
      <td>checkedimage</td>
      <td>选中状态的图片路径；设置后默认选中样式失效</td>
      <td></td>
   </tr>
   <tr>
      <td>nocheckedimage</td>
      <td>未选中状态的图片路径；设置后默认未选择状态失效</td>
      <td></td>
   </tr>
   <tr>
      <td>readonly</td>
      <td>是否只读，取值true和false，不写默认false；(通过js可以修改)；</td>
      <td></td>
   </tr>
   <tr>
      <td>value</td>
      <td>提交值</td>
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
      <td>尺寸:默认height:30<br/>定位<br/>外边距<br/>内边距<br/>边框<br/>背景<br/>flexbox布局：align-self</td>
      <td></td>
   </tr>
   <tr>
      <td>color</td>
      <td>文字颜色(通过js可以修改); 默认#000000</td>
      <td></td>
   </tr>
   <tr>
      <td>height</td>
      <td>checkbox图标的高度(通过js可以修改); 设置后图标的高宽同时生效，一定保证是正方形或者圆形。默认30dp</td>
      <td></td>
   </tr>
   <tr>
      <td>font-size</td>
      <td>字体大小(通过js可以修改)；默认16dp</td>
      <td></td>
   </tr>
   <tr>
      <td>readonly-radius </td>
      <td>只读状态遮罩区域的弧度，一般用于有图片的时候设置，比如如果用的图片是圆形为了保证效果只读状态下遮罩区域也是圆形可以设置该值,默认0</td>
      <td></td>
   </tr>
   <tr>
      <td>checked-color</td>
      <td>checked时候的背景色; 默认#549FF7</td>
      <td></td>
   </tr>
   <tr>
      <td>nochecked-color</td>
      <td>为未选中状态下背景；默认#9B9C9C</td>
      <td></td>
   </tr>
 <tr>
      <td>checkbox-border-radius</td>
      <td>checkbox的边框弧度，默认0</td>
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
      <td>见详细设计文档box章节（不包括容器类Dom节点操作）</td>
      <td></td>
   </tr>
   <tr>
      <td>click()</td>
      <td>模拟点击checkbox组件，执行click()方法，相当于手动点击了一下checkbox</td>
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
      <td>监听checkbox属性改变</td>
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
        var console = require("Console");
        var ListAdapter = require("ListAdapter");
        require("titlebarUI");
        require("buttonUI");
        require("checkboxUI");

        var myappjs = require("myapp");
        var screenWidth = window.getScreenWidth();
        window.on("loaded", function () {
            var setcheckbox = document.getElement("setcheckbox");
            var getcheckbox = document.getElement("getcheckbox");
            var checkbox1 = document.getElement("checkbox1");
            var testclick = document.getElement("testclick");
            var testreadonly1 = document.getElement("testreadonly1");
            var testreadonly2 = document.getElement("testreadonly2");
            var testclickreadonly = document.getElement("testclickreadonly");
            var title = document.getElement("title");

            setcheckbox.on("click", function (e) {
                var checked = checkbox1.getAttr("checked");
                if (checked == "true") {
                    checkbox1.setAttr("checked", "false");
                }
                else {
                    checkbox1.setAttr("checked", "true");
                }

            });

            getcheckbox.on("click", function (e) {
                myappjs.alert(checkbox1.getAttr("checked"));
            });

            checkbox1.on("change", function (e) {
                //console.log("进入了change");
                myappjs.alert(checkbox1.getAttr("checked"));
            });

            /*checkbox1.on("click",function(e){
                    console.log("进入了click");
            	
                    myappjs.alert(checkbox1.getAttr("checked"));	
            });*/
            testclick.on("click", function () {
                checkbox1.click();
            });

            testclickreadonly.on("click", function () {

                if (testreadonly1.getAttr("readonly") == "true") {
                    console.log("进来了");
                    testreadonly1.setAttr("readonly", "false");
                    testreadonly2.setAttr("readonly", "false");
                }
                else {

                    testreadonly1.setAttr("readonly", "true");
                    testreadonly2.setAttr("readonly", "true");
                }
            });
            //titlebar关闭页面  
            title.on("liconClick", function (e) {
                var json = {};
                window.close(json);
            });
        });
    ]]>
    </script>
    <style>
        @import url(res:sprite_component/css/sprite.layout.css);
        @import url(res:sprite_component/css/sprite.color.css);
        checkbox {
            margin: 5;
            checkbox-border-radius: 4;
        }
        
        button {
            margin: 5;
        }
    </style>
    <ui>
        <box class="bg-white full" id="box">
            <titlebar title="checkbox控件" class="titlebar-hasstatus" licon="res:yuanhongqian/image/icon.png" style="licon-width:24;licon-height:24"
                id="title" />

            <scroll style="flex:1;width:fill_screen;font-size:12;">
                <box style="flex-direction:row;flex-wrap:wrap;align-items:flex-start;width:fill_screen;">
                    <checkbox id="checkbox1" checked="true" caption="男" />

                    <button value="设置checkbox" id="setcheckbox" />
                    <button value="得到checkbox" id="getcheckbox" />

                    <checkbox checkedimage="res:yuanhongqian/image/rad_pressed.png" nocheckedimage="res:yuanhongqian/image/rad_normal.png" checked="true"
                        caption="图片" style="checked-color:blue;height:30;font-size:18" />

                    <checkbox checkedimage="res:yuanhongqian/image/ump_checkbox_focus.png" nocheckedimage="res:yuanhongqian/image/ump_checkbox_normal.png"
                        checked="true" caption="图片2" style="checked-color:blue;height:30;font-size:18" />
                    <checkbox checked="true" caption="有弧度" style="checked-color:blue;color:red;checkbox-border-radius:15" />
                </box>
                <box style="flex-direction:row;flex-wrap:wrap;align-items:flex-start;width:fill_screen;">
                    <checkbox caption="三星" style="" />
                    <checkbox caption="iphone" style="checked-color:#F8BF53;" />
                    <checkbox caption="华为" style="checked-color:#F8BF53;" />
                    <checkbox caption="小米" style="checked-color:#F8BF53;" />
                    <checkbox caption="小米2" style="checked-color:#F8BF53;" />
                    <checkbox caption="小米3" style="checked-color:#F8BF53;" />
                    <checkbox caption="小米4" style="checked-color:#F8BF53;" />
                </box>
                <button id="testclick" value="模拟点击第一个checkbox"></button>
                <checkbox id="testreadonly1" checked="true" caption="iphone" style="checked-color:#F8BF53;" />
                <checkbox id="testreadonly2" checked="true" caption="华为" checkedimage="res:yuanhongqian/image/ump_checkbox_focus.png" nocheckedimage="res:yuanhongqian/image/ump_checkbox_normal.png"
                />
                <button id="testclickreadonly" value="设置readonly属性"></button>

            </scroll>

        </box>
    </ui>
</page>
```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_15.png" style="width:250;"/> 