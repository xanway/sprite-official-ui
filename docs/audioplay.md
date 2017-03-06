<h1>audioplay组件</h1>

----------

## 说明  

audioplay组件是一个播放器组件，可以支持本地音频播放和网络音频播放音频格式建议mp3,其余音频格式要看手机系统自身能否支持。  

用法：在js里面引入require("audioplayUI");  

示例

```html
<audioplay id="play1" style="button-border-color:#549FF7;button-background-color:#549FF7;button-height: 20;height: 50" />
``` 

音频播放需要通过js初始化后播放

```javascript
var json = {};
json.url = "res:yuanhongqian/mp3/mnmjd.mp3";
json.mediaInfo = {};
json.mediaInfo.title = "没那么简单";
json.mediaInfo.artist = "王小虎";
json.mediaInfo.albumTitle = "四叶草Joyce Chu";
json.mediaInfo.cover = "res:yuanhongqian/image/2.jpg";
play1.playinit(json);
play1.start();

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
      <td>尺寸，默认height:30;<br/>
定位<br/>
外边距<br/>
内边距<br/>
边框<br/>
背景<br/>
flexbox布局:align-self<br/>
</td>
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
   <tr>
      <td>playinit(jsondata)</td>
      <td>播放音频之前初始化,<br/>
Json数据格式<br/>
Json.url:音频文件路径支持res:和http<br/>
Json. mediaInfo={} 音频文件内容json格式，音频切换换掉后台播放时，可以在手机系统播放状态里面看到。<br/>
json.mediaInfo.title：标题<br/>
json.mediaInfo.artist：艺术家<br/>
json.mediaInfo.albumTitle：专辑<br/>
json.mediaInfo.cover：系统播放界面的状态图片。<br/>
</td>
	<td>var json = {};<br/>
json.url = "res:yuanhongqian/mp3/mnmjd.mp3";<br/>
json.mediaInfo = {};<br/>
json.mediaInfo.title = "没那么简单";  <br/>          
json.mediaInfo.artist = "王小虎"; <br/>         
 json.mediaInfo.albumTitle = "四叶草Joyce Chu";   <br/>
 json.mediaInfo.cover = "res:yuanhongqian/image/2.jpg";<br/>
play1.playinit(json);
</td>
   </tr>
   <tr>
      <td>start()</td>
      <td>开始播放，播放之前需要先执行playinit(json)方法</td>
      <td></td>
   </tr>
   <tr>
      <td>pause()</td>
      <td>暂停播放</td>
      <td></td>
   </tr>
   <tr>
      <td>stop()</td>
      <td>停止播放</td>
      <td></td>
   </tr>
   <tr>
      <td>getStatus()</td>
      <td>获得当前播放状态；0：未播放状态； 1：播放状态； 2：暂停状态；</td>
      <td></td>
   </tr>
  
</table>

## 事件  

无

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
        require("audioplayUI");
        require("buttonUI");
        var myappjs = require("myapp");
        var screenWidth = window.getScreenWidth();

        window.on("animator", function () {
            //titlebar关闭页面
            var titlebarid = document.getElement("titlebarid");
            var play1 = document.getElement("play1");
            var btn1 = document.getElement("btn1");
            var btn2 = document.getElement("btn2");

            titlebarid.on("liconClick", function (e) {
                var json = {};
                window.close(json);

            });

            titlebarid.on("ltextClick", function (e) {
                var json = {};
                window.close(json);
            });

            btn1.on("click", function (e) {

                if (btn1.getAttr("bofang") == "0") {

                    if (btn2.getAttr("bofang") == "1") {
                        play1.stop();
                    }

                    if (play1.getStatus() == 0) {
                        var json = {};
                        json.url = "res:yuanhongqian/mp3/mnmjd.mp3";
                        json.mediaInfo = {};
                        json.mediaInfo.title = "没那么简单";
                        json.mediaInfo.artist = "王小虎";
                        json.mediaInfo.albumTitle = "四叶草Joyce Chu";
                        json.mediaInfo.cover = "res:yuanhongqian/image/2.jpg";
                        play1.playinit(json);
                        play1.start();
                        btn1.setAttr("bofang", "1");
                        btn2.setAttr("bofang", "0");
                    }
                }
            });

            btn2.on("click", function (e) {
                if (btn2.getAttr("bofang") == "0") {
                    if (btn1.getAttr("bofang") == "1") {
                        play1.stop();
                    }

                    if (play1.getStatus() == 0) {
                        var json = {};
                        // json.url = "http://ar.h5.rh01.sycdn.kuwo.cn/resource/n3/69/69/1177285534.mp3";
                        json.url = "http://mpge.5nd.com/2017/2017-1-9/75862/1.mp3";
                        json.mediaInfo = {};
                        json.mediaInfo.title = "思念2017";
                        json.mediaInfo.artist = "乔冠林";
                        json.mediaInfo.albumTitle = "最新歌曲";
                        json.mediaInfo.cover = "res:yuanhongqian/image/2.jpg";
                        play1.playinit(json);
                        play1.start();
                        btn1.setAttr("bofang", "0");
                        btn2.setAttr("bofang", "1");
                    }
                }
            });
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
        
        button {
            margin: 4;
        }
    </style>
    }
    <ui>
        <box class="bg-white full" id="box">
            <titlebar id="titlebarid" ltext="返回" title="audioplay播放控件" licon="res:yuanhongqian/image/icon.png" class="titlebar-hasstatus"
                style="licon-width:24;licon-height:24" />
            <scroll style="flex:1;width:fill_screen;align-items:center;">
                <button bofang="0" id="btn1" value="播放本地音乐《没那么加简单》"></button>
                <button bofang="0" id="btn2" value="播放网络音乐《思念2017》"></button>
            </scroll>
            <audioplay id="play1" style="button-border-color:#549FF7;button-background-color:#549FF7;button-height: 20;height: 50" />
        </box>
    </ui>
</page>
```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_21.png" style="width:250;"/> 
<img width="250" src="image/fengzhuangzhujian_22.png" style="width:250;"/> 
