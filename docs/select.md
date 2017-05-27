# select组件

----------

<h2 id="cid_0">说明</h2>

select组件主要用于弹出框选项效果，该组件可作为表单控件使用。该组件封装了change事件，只要该控件内部定义的属性发生变化都会触发该事件（用户自己写的属性改变不会触发change事件）。  

用法：在js里面引入require("selectUI");  

示例：
 
```html
<select readonly="true" id="select1" style="margin:8" value="100"  title="请选择"/>
``` 

select选项内容必须通过loadData()方法动态加载  

```javascript
var select1 = document.getElement("select1");
var datas = new Array();
json = {};
json.type   = "cell";
json.text   = "flexbox测试";
json.selected = "false";
json.value   = "100";
datas.push(json); 
json = {};
json.type   = "cell";			
json.text   = "移动按钮";
json.selected = "false";
json.value   = "101";			
datas.push(json);  
json = {};
json.type   = "cell";			
json.text   = "switch控件";	
json.selected = "false";
json.value   = "102";			
datas.push(json);
select1.loadData(datas);

``` 

<h2 id="cid_1">属性</h2>

<span id="sx_0">**公共属性**</span>  

[参见公共属性章节](https://gitdocument.exmobi.cn/sprite-api/ggsx.html)，包括：id、style、class；

<span id="sx_1">**readonly**</span>

<code>是否只读</code>

是否只读，取值true和false，不写默认false (通过js可以修改)



<span id="sx_2">**value**</span>

<code>提交值</code>

如果该值和注入的数据内容的value一致，那么注入数据对应的选项就是选中状态。(通过js可以修改)



<span id="sx_3">**title**</span>

<code>设置弹出框的title文字内容</code>

设置弹出框的title文字内容。


<span id="sx_4">**prompt**</span>

<code>设置提示文字</code>

在没有value的选中的情况下，给出的提示文字。



<h2 id="cid_2">样式</h2>

[参见公共样式章节](https://gitdocument.exmobi.cn/sprite-api/ggys.html)，包括：  

> 尺寸：height默认40;
> 
> 定位
> 
> 内边距
> 
> 外边距
> 
> 边框
> 
> 背景
> 
> flexbox布局：align-self，flex


**selected-color**	

<code>选中状态下文字颜色</code>

选中状态下文字颜色; 默认#549FF7；


**text-align**	

<code>select内部文字布局位置</code>

默认left;


**color**	

<code>select内部文字颜色</code>

默认#000000;

**font-size**	

<code>select内部字体大小</code>

默认16dp;

**title-background-color**	

<code>pop弹出框的title背景颜色</code>

默认#ffffff;


**title-color**	

<code>pop弹出框的title文字颜色</code>

默认#000000;


**prompt-color**	

<code>提示文字颜色</code>

默认#D2D3D7;




<h2 id="cid_3">js方法</h2>



**公共方法**  


[事件相关](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_0)，包括：

> [on(messageName:string,callback:Function): void   组件注册事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_1)   
> 
> [fire(messageName:string,params:Array&lt;any&gt;): void  组件事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_2)   
> 
> [off(messageName:string,callback:Function): void  组件移除事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_3)  
>  
> [getOn(messageName:string): Array&lt;Function&gt;  获取已绑定的事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_4)   

[动画相关](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_1)，包括： 
 
> [startAnimation(jsonData:Object,callback:Function): void  启动UI组件动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_1)   
> 
> [startAnimator(jsonData:Object,callback:Function): void  启动UI组件属性动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_2)   
> 
> [startKeyFrameAnimator(jsonData:Object,callback:Function): void  启动UI组件关键帧动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_3)  
>  
> [ releaseAnimator(): void  结束控件动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_4)   

[尺寸和位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_2)，包括：  

> [getFrame(): Object  获取组件在父容器中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_1)   
> 
> [setFrame(frame:Object): void  设置组件在父容器中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_2)   
> 
> [getCenter(): Object  获取组件中心点在父容器中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_3)  
>
> [getAbsoluteFrame(): Object  获取组件在绘制窗口中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_4)   


[普通Dom节点操作](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_3)，包括：  

> [getParent(): IElement  获取父节点](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_1)   
> 
> [getNext(): IElement  获取同级下一个节点](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_2)   
> 
> [getPrevious(): IElement  获取同级前一个节点](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_3)  
> 
> [remove(): void  从父容器中移除自身](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_4)  
> 
> [clone(isDeep:boolean):IElement  对当前Dom节点进行克隆](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_5)  
>
> [setAttr(attrName:string,attrValue:string): void  设置节点属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_6)   
>
> [getAttr(attrName:string):string  获取节点属性值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_7) 
>
> [getAttrs(): Object  获取节点所有属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_8) 
>
> [removeAttr(attrName:string): void  移除节点属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_9) 
>
> [hasAttr(attrName:string): boolean  节点是否具有该属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_10) 
> 
> [setStyle(styleName:string,styleValue:string): void  设置节点样式值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_13)  
>
> [getStyle(styleName:string):string  获取节点样式值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_14)   
>
> [clearStyle(styleName:string): void  移除节点样式值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_15)    
>
> [setClassStyle(className:string,domobj:IElement): void   设置节点对应Class样式](https://gitdocument.exmobi.cn/sprite-api/ggff.htm#ptdom_16) 
>  
> [getClassStyle(): string  获取节点已设置Class样式](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_17)  
>  
> [getTag(): string  获取UI组件类型](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_18)  
>  
> [getId(): string  获取UI组件Id标识](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_19) 


** click():void**

<code>模拟点击一次select</code>

模拟点击checkbox组件，执行click()方法，相当于手动点击了一下select

参数：无

返回值：无

**getSelectedIndex():void**

<code>得到当前索引从0开始</code>

参数：无

返回值：无


**loadData(jsonDatas:Array):void**

在模板里面使用时，该方法不能放在created里面执行，因为loadData时组件内部需要布局刷新，created时候是不允许执行刷新操作的。

<code>注入数据</code>

参数：

jsonDatas：json数组，json格式

> text: 文字
> 
> selected: 是否选择，取值true，false;
> 
> value: 提交值;



<h2 id="cid_4">事件</h2>


**change**  

<code>监听select属性改变</code>

event对象包括：  
 
type：事件类型，字符串类型，固定值：change；  

target：触发事件的目标组件，dom对象；  

timestamp：事件触发的时间戳,单位毫秒，数字类型；

<h2 id="cid_5">示例</h2>

```html
<page>
    <script>
        <![CDATA[
        var index = 1;
        var window = require("Window");
        var document = require("Document");
        var console = require("Console");
        var ui = require("UI");
        var ListAdapter = require("ListAdapter");
        var console = require("Console");

        require("titlebarUI");
        require("buttonUI");
        require("selectUI");


        var myappjs = require("myapp");
        var screenWidth = window.getScreenWidth();
        var datas = new Array();
        var datas2 = new Array();
        window.on("animator", function () {
            var testbtn = document.getElement("testbtn");
            var select1 = document.getElement("select1");
            var testbtn2 = document.getElement("testbtn2");
            var testbtn3 = document.getElement("testbtn3");
            var testbtn4 = document.getElement("testbtn4");
            testbtn.on("click", function (e) {
                //myappjs.alert(datas[0].selected);
                select1.setAttr("value", "1000");

            })

            testbtn2.on("click", function (e) {
                //myappjs.alert(datas[0].selected);
                myappjs.alert(select1.getAttr("value"));
            })
            testbtn3.on("click", function (e) {

                var index = select1.getSelectedIndex();
                myappjs.alert(index);

            })
            testbtn4.on("click", function (e) {
                if (select1.getAttr("readonly") == "false") {

                    select1.setAttr("readonly", "true");
                }
                else {
                    select1.setAttr("readonly", "false");
                }
            });
            //titlebar关闭页面
            var title = document.getElement("title");
            title.on("liconClick", function (e) {
                var json = {};
                window.close(json);

            });
            //多个true 只是显示第一个，select控件如果有value值并且value值能对应上data里面的value，以value值对应的数据为选择项

            for (i = 0; i < 5; i++) {
                json = {};
                json.text = "flexbox测试";
                json.selected = "false";
                json.value = "100" + i;
                datas.push(json);

                json = {};
                json.text = "移动按钮";
                json.selected = "false";
                json.value = "101" + i;
                datas.push(json);

                json = {};
                json.text = "switch控件";
                json.selected = "false";
                json.value = "102" + i;
                datas.push(json);

            }

            var select1 = document.getElement("select1");
            var select2 = document.getElement("select2");

            select1.loadData(datas);

            select1.on("change", function (e) {

                myappjs.alert("监听change事件");
            })
            json = {};
            json.text = "flexbox测试";
            json.selected = "false";
            json.value = "100";
            datas2.push(json);

            json = {};
            json.text = "switch控件";
            json.selected = "true";
            json.value = "102";
            datas2.push(json);
            select2.loadData(datas2);

        });
	
    ]]>
    </script>
    <style>
        @import url(res:sprite_component/css/sprite.layout.css);
        @import url(res:sprite_component/css/sprite.color.css);
        button {
            margin: 5 5 5 5;
        }
    </style>
    <ui>
        <box class="white full" id="box">
            <titlebar title="select控件" class="titlebar-hasstatus" licon="res:yuanhongqian/image/icon.png" style="licon-width:24;licon-height:24"
                id="title" />

            <scroll style="flex:1;width:fill_screen;">
                <select readonly="true" id="select1" style="margin:8" value="1001" title="请选择" />
                <button value="设置值" id="testbtn" class="submit" />
                <button value="得到当前select的value" id="testbtn2" />
                <button value="得到当前selected的索引" id="testbtn3" />
                <button value="设置readonly" id="testbtn4" />

                <select id="select2" style="margin:8;select-color:red;border-radius:20" />
            </scroll>
        </box>
    </ui>
</page>
```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_16.png" style="width:250;"/>  