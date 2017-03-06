<h1>popbottommenu组件 </h1> 

----------

## 说明  

popbottommenu组件主要用于页面底部弹出菜单，效果类似微信钱包里面的弹出菜单。  

用法：在js里面引入require("popbottommenuUI");  

示例：需要在js里面创建组件对象。  
   
```javascript
var popbottommenu =  document.createElement("popbottommenu");
var popjson =  {
    datas:[
        {
            text:"交易记录",
            handler:function(e){
                console.log(e.target);
                myappjs.alert("你点击了 交易记录,隐藏pop");
                popbottommenu.hide(); 
            }
        },
        {
            text:"支付管理",
            handler:function(e){
                console.log(e.target);
                myappjs.alert("你点击了 支付管理");
                popbottommenu.hide();
            }
        },
        {
            text:"支付安全",
            handler:function(e){
                console.log(e.target);
                myappjs.alert("你点击了 支付安全");
                popbottommenu.hide();
            }
        },
        {
            "text":"帮助中心",
            handler:function(e){
                console.log(e.target);
                myappjs.alert("你点击了 帮助中心");
                popbottommenu.hide();
            }
        }
    ]
};
popbottommenu.popinit(popjson);
popbottommenu.show(); 

``` 
  
## 属性  

无

 
## 样式  

无  

## js方法  

<table>
   <tr>
      <td>Js方法</td>
      <td>描述说明</td>
      <td>示例</td>
   </tr>
   <tr>
     <td>popinit(popjson) </td>
	 <td>初始化pop数据，参数为json数据。<br/>
	var popjson = {};<br/>  
	popjson.datas; //菜单子项数据，格式数组。<br/>
	子项数据格式为json：<br/>
	Jsonitem.text; //菜单文字内容<br/>
	Jsonitem.handler:function(e){};点击菜单回调方法<br/>
	</td>
	 <td>var popjson = {};<br/>
//菜单子项数据<br/>
popjson.datas = [;<br/>
{<br/>
text:"菜单1", <br/>
handler:function(e){<br/>
myappjs.alert("你点击了 菜单1");<br/>
     &emsp;&emsp;&emsp;popbottommenu.hide();<br/>
   &emsp; &emsp;}<br/>
 &emsp;}<br/>
]<br/>
popbottommenu.popinit(popjson);
</td>
   </tr>
   <tr>
      <td>show()</td>
      <td>显示pop弹窗 </td>
      <td></td>
   </tr>
   <tr>
      <td>hide()</td>
      <td>隐藏pop窗口</td>
      <td></td>
   </tr>
 
</table>


## 事件  

无


## 示例  

```html
<page>
    <script>
        <![CDATA[
        var index = 1;
        var window = require("Window");
        var document = require("Document");
        var time = require("Time");
        var ui = require("UI");
        var console = require("Console");
        var myappjs = require("myapp");
        var app = require("App");
        require("titlebarUI");
        require("buttonUI");
        require("popbottommenuUI");
        var screenWidth = window.getScreenWidth();
        window.on("animator", function () {
            //关闭页面
            var titleid = document.getElement("titleid");
            var popbottommenu = document.createElement("popbottommenu");
            var popjson = {
                datas: [
                    {
                        text: "交易记录",
                        handler: function (e) {
                            console.log(e.target);
                            myappjs.alert("你点击了 交易记录,隐藏pop");

                            popbottommenu.hide();
                        }
                    },
                    {
                        text: "支付管理",
                        handler: function (e) {
                            console.log(e.target);
                            myappjs.alert("你点击了 支付管理");
                            popbottommenu.hide();
                        }
                    },
                    {
                        text: "支付安全",
                        handler: function (e) {
                            console.log(e.target);
                            myappjs.alert("你点击了 支付安全");
                            popbottommenu.hide();
                        }
                    },
                    {
                        "text": "帮助中心",
                        handler: function (e) {
                            console.log(e.target);
                            myappjs.alert("你点击了 帮助中心");
                            popbottommenu.hide();
                        }
                    }
                ]
            };

            popbottommenu.popinit(popjson);
            titleid.on("liconClick", function (e) {
                var json = {};
                window.close(json);
            });

            titleid.on("rtextClick", function (e) {
                popbottommenu.show();
            });
        });
 
    ]]>
    </script>
    <style>
        @import url(res:sprite_component/css/sprite.layout.css);
        @import url(res:sprite_component/css/sprite.color.css);
    </style>
    <ui>
        <box class="full" style="" id="box">
            <titlebar id="titleid" class="titlebar-hasstatus" style="background-color:#549FF7;title-color:#ffffff;right-color:#ffffff"
                title="popbottommenu" licon="res:yuanhongqian/image/back.png" rtext="菜单"></titlebar>
                <box class="flex1">
                </box>
        </box>
    </ui>
</page>
```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_12.png" style="width:250;"/> 

