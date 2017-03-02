# button组件 

----------

[说明](#header1)  
 
[属性](#header2) 

[样式](#header3) 
 
[js方法](#header4) 

[事件](#header5) 

[示例](#header6) 

<br/>
<h2 id="header1">说明</h2>
button组件主要用于按钮形式布局，为方便开发者使用，其封装一些常用样式

包括：sumbit cancel outline 注意：混合使用时outline必需在最后。  

用法：在使用button组件的时候需要在js里面引入 require("buttonUI");   
示例代码：  
 
```html
	<button class="margin4 radius8 submit outline"  value="提交"></button>
``` 

<br/>
<h2 id="header2">属性</h2>
<table><tr><td>属性</td><td>描述说明</td><td>示例</td></tr><tr><td>公共属性</td><td>参见公共属性章节，包括：id，style，class</td><td></td></tr><tr><td>value</td><td>按钮文字（可以通过js修改）</td><td>var btn = document. getElement(“buttonid”);<br/>btn.setAttr(“value”,”按钮”);</td></tr><tr><td>tip</td><td>小气泡数字（可以通过js修改）</td><td>同上</td></tr><tr><td>licon</td><td>按钮上左侧的图片（可以通过js修改）</td><td>同上</td></tr><tr><td>ricon</td><td>按钮上右侧的图片（可以通过js修改）</td><td>同上</td></tr><tr><td>readonly</td><td>只读（可以通过js修改）</td><td>同上</td></tr><tr><td>loading</td><td>加载等待，取值true和false （可以通过js修改）</td><td>一般用于点击按钮时候的等待效果，btn.setAttr(“loading”,”true”);显示等待图标，过程执行结束后再调用btn.setAttr(“loading”,”false”);隐藏等待图标</td></tr></table>

<br/>
<h2 id="header3">样式</h2>

<table><tr><td>样式</td><td>描述说明</td><td>示例</td></tr><tr><td>box公共样式</td><td>尺寸:height默认40;<br/>定位<br/>内边距，默认padding:0 8 0 8;<br/>外边距<br/>边框:默认#549FF7;<br/>背景:默认#549FF7;<br/>flexbox布局：align-self，flex</td><td></td></tr><tr><td>color</td><td>按钮文字颜色，默认#ffffff （可以通过js修改）</td><td>var btn = document. getElement(“buttonid”);<br/>btn.setStyle(“color”,”red”);</td></tr><tr><td>color-click</td><td>按钮文字点击颜色 默认#ffffff</td><td></td></tr><tr><td>border-color-click</td><td>边框点击颜色，默认#295b9d</td><td></td></tr><tr><td>background-color-click</td><td>按钮背景点击色，点击按钮会渐变到该色值，默认#295b9d。</td><td></td></tr><tr><td>tip-color</td><td>小气泡字体颜色（可以通过js修改），默认#ffffff</td><td>同color</td></tr><tr><td>tip-background-color</td><td>小气泡背景颜色（可以通过js修改），当按钮样式有outline是背景色是red
