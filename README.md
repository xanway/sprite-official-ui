# SpriteUI
官方组件封装  
<table><tr><td>属性</td><td>描述说明</td><td>示例</td></tr><tr><td>公共属性</td><td>参见公共属性章节，包括：<br/>id，<br/>
style， 
class</td><td></td></tr><tr><td>value</td><td>按钮文字（可以通过js修改）</td><td>var btn = document. getElement(“buttonid”);<br/>
btn.setAttr(“value”,”按钮”);</td></tr><tr><td>tip</td><td>小气泡数字（可以通过js修改）</td><td>同上</td></tr><tr><td>licon</td><td>按钮上左侧的图片（可以通过js修改）</td><td>同上</td></tr><tr><td>ricon</td><td>按钮上右侧的图片（可以通过js修改）</td><td>同上</td></tr><tr><td>readonly</td><td>只读（可以通过js修改）</td><td>同上</td></tr><tr><td>loading</td><td>加载等待，取值true和false （可以通过js修改）</td><td>一般用于点击按钮时候的等待效果，btn.setAttr(“loading”,”true”);显示等待图标，过程执行结束后再调用btn.setAttr(“loading”,”false”);隐藏等待图标</td></tr></table>
