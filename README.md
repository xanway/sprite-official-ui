# 官方封装组件API及使用

官方组件基于sprite平台提供的基础组件进行封装，首先获取封装组件 sprite_component 把该组件目录放入自己应用某个目录下面，另外还需要在应用程序的入口home.js里面进行路径配置，配置信息如下，示例中配置是直接把sprite_component放在apps更目录下，开发者根据实际目录修改路径配置信息。

![](image/fengzhuangzhujian_1.png)

>配置信息如下：  

```
require.config({
jsPaths:{
},
componentPaths:{
//官方封装组件引用
"componentUI":"res:sprite_component/tmpl/component.component",
"buttonUI":"res:sprite_component/button/button.component",
"titlebarUI":"res:sprite_component/titlebar/titlebar.component",
"menubarUI":"res:sprite_component/menubar/menubar.component",
"gridmenuUI":"res:sprite_component/gridmenu/gridmenu.component",
"newsliderUI":"res:sprite_component/newslider/newslider.component",
"checkboxUI":"res:sprite_component/checkbox/checkbox.component",
"radioUI":"res:sprite_component/radio/radio.component",
"switchUI":"res:sprite_component/switch/switch.component",
"selectUI":"res:sprite_component/select/select.component",
"tabbarUI":"res:sprite_component/tabbar/tabbar.component",
"indexbarUI":"res:sprite_component/indexbar/indexbar.component",
"popmenuUI":"res:sprite_component/popmenu/popmenu.component","popbottommenuUI":"res:sprite_component/popbottommenu/popbottommenu.component",
"sliderbarUI":"res:sprite_component/sliderbar/sliderbar.component",
"audioplayUI":"res:sprite_component/audioplay/audioplay.component","superhandsignUI":"res:sprite_component/superhandsign/superhandsign.component",
"organizationUI":"res:sprite_component/organization/organization.component",
"memoryfieldUI":"res:sprite_component/memoryfield/memoryfield.component",
"audiorecordUI":"res:sprite_component/audiorecord/audiorecord.component"
},
cssPaths:{

}
});
```

    require.config({
	jsPaths:{
	},
	componentPaths:{
	//官方封装组件引用
	"componentUI":"res:sprite_component/tmpl/component.component",
	"buttonUI":"res:sprite_component/button/button.component",
	"titlebarUI":"res:sprite_component/titlebar/titlebar.component",
	"menubarUI":"res:sprite_component/menubar/menubar.component",
	"gridmenuUI":"res:sprite_component/gridmenu/gridmenu.component",
	"newsliderUI":"res:sprite_component/newslider/newslider.component",
	"checkboxUI":"res:sprite_component/checkbox/checkbox.component",
	"radioUI":"res:sprite_component/radio/radio.component",
	"switchUI":"res:sprite_component/switch/switch.component",
	"selectUI":"res:sprite_component/select/select.component",
	"tabbarUI":"res:sprite_component/tabbar/tabbar.component",
	"indexbarUI":"res:sprite_component/indexbar/indexbar.component",
	"popmenuUI":"res:sprite_component/popmenu/popmenu.component","popbottommenuUI":"res:sprite_component/popbottommenu/popbottommenu.component",
	"sliderbarUI":"res:sprite_component/sliderbar/sliderbar.component",
	"audioplayUI":"res:sprite_component/audioplay/audioplay.component","superhandsignUI":"res:sprite_component/superhandsign/superhandsign.component",
	"organizationUI":"res:sprite_component/organization/organization.component",
	"memoryfieldUI":"res:sprite_component/memoryfield/memoryfield.component",
	"audiorecordUI":"res:sprite_component/audiorecord/audiorecord.component"
	},
	cssPaths:{
	
	}
	});

