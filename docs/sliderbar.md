<h1>sliderbar组件</h1>

----------

## 说明  

sliderbar是滑动条组件，类似控制播放的进度条，一般用于拖动滑动条来设置一个区间范围值。  

用法：在js里面引入require("sliderbarUI");  

示例：

  
```html
<sliderbar id="slidebar_id"  style="sliderbar-color:red;height:36;width:fill_screen" x_progress="30"  />
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
      <td>x_progress</td>
      <td>当前进度和总进度的百分比数值0-100 (可通过js动态修改)</td>
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
      <td>尺寸:默认height:30;<br/>定位<br/>外边距<br/>内边距<br/>边框<br/>背景<br/>flexbox布局:align-self<br/></td>
      <td></td>
   </tr>
   <tr>
      <td>sliderbar-color</td>
      <td>前面线条颜色;默认#549FF7</td>
      <td></td>
   </tr>
   <tr>
      <td>sliderbar-after-color</td>
      <td>后部分线条颜色；默认#f5f5f5</td>
      <td></td>
   </tr>
   <tr>
      <td>button-background-color</td>
      <td>触摸按钮背景颜色；默认#fcfcfc</td>
      <td></td>
   </tr>
   <tr>
      <td>button-border-color</td>
      <td>触摸按钮边框颜色；默认#d9d9d9</td>
      <td></td>
   </tr>
   <tr>
      <td>button-height</td>
      <td>触摸按钮高度（设置后宽度同时生效），默认30，如果同时设置height和button-height的时候，需要保证height比button-height的值大</td>
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
</table>

## 事件  

<table>
   <tr>
      <td>事件</td>
      <td>描述说明</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>change</td>
      <td>监听触摸时的实时进度值,参数(e , param1) param1返回进度值</td>
	<td></td>
   </tr>
</table>  

## 示例  

该示例和list组件混合使用，list需要用到section。

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
        require("sliderbarUI");
        require("buttonUI");
        var myappjs = require("myapp");

        var screenWidth = window.getScreenWidth();
        window.on("animator", function () {

            //titlebar关闭页面
            var titlebarid = document.getElement("titlebarid");
            titlebarid.on("liconClick", function (e) {
                var json = {};
                window.close(json);

            });

            titlebarid.on("ltextClick", function (e) {
                var json = {};
                window.close(json);

            });

            var slidebar_id = document.getElement("slidebar_id");
            var slider_n = document.getElement("slider_n");

            slider_n.setText(slidebar_id.getAttr("x_progress") + "%");

            slidebar_id.on("change", function (e, param1) {
                //console.log(param1);
                slider_n.setText(param1 + "%");
            });

            var setProgress_btn = document.getElement("setProgress_btn");
            setProgress_btn.on("click", function (e) {
                slidebar_id.setAttr("x_progress", "50");
                //console.log(slidebar_id.getAttr("x_progress"));

            });

            var timeprogeress = document.getElement("timeprogeress");
            var time1 = document.getElement("time1");
            var time2 = document.getElement("time2");
            var x = 0;
            var t = 0;
            timeid = time.setInterval(function () {
                x = x + 100 / 120;
                t = t + 1;

                timeprogeress.setAttr("x_progress", x);
                var s = Number(t % 60) >= 10 ? Number(t % 60) : "0" + Number(t % 60);
                var time1str = Math.floor(t / 60) >= 10 ? Math.floor(t / 60) : "0" + Math.floor(t / 60) + ":" + s;

                time1.setText(time1str);
                if (t == 120) {
                    time.clearInterval(timeid);
                }
            }, 1000);
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
    </style>
    <ui>
        <box class="bg-white full" id="box">
            <titlebar id="titlebarid" ltext="返回" title="sliderbar的控件" licon="res:yuanhongqian/image/icon.png" class="titlebar-hasstatus"
                style="licon-width:24;licon-height:24" />
            <scroll style="flex:1;width:fill_screen;align-items:center;">
                <box style="flex-direction:row;width:fill_screen;align-items:start;justify-content:center;flex-wrap:wrap">
                    <sliderbar id="slidebar_id" style="sliderbar-color:red;height:36;width:fill_screen" x_progress="30" />
                    <text id="slider_n" style="width:70;height:36">0</text>
                </box>
                <button value="设置进度" style="width:fill_screen" id="setProgress_btn" />
                <sliderbar style="sliderbar-color:blue;height:30;width:200" x_progress="10" />
                <sliderbar style="sliderbar-color:blue;height:50;width:300" x_progress="30" />
                <box style="flex-direction:row;align-items:center;">
                    <text id="time1" style="width:50;">00:00</text>
                    <sliderbar id="timeprogeress" style="height:30;flex:1;margin:0 10 0 10;button-background-color:#549FF7;button-border-color:#549FF7"
                        x_progress="0" />
                    <text id="time2" style="width:50">02:00</text>
                </box>
            </scroll>
        </box>
    </ui>
</page>
```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_17.png" style="width:250;"/> 