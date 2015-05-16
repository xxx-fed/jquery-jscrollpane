# jScrollPane 使用介绍

一个模拟滚动条的插件


##参数说明

	embedSWF: function(swfUrlStr, replaceElemIdStr, widthStr, heightStr, swfVersionStr, xiSwfUrlStr, flashvarsObj, parObj, attObj, callbackFn) {
	}

	参数依次为

    swfUrlStr ： swf位置，
	replaceElemIdStr ： html要替换成flash的元素的id，
	widthStr ： 宽，
	heightStr ： 高，
	swfVersionStr ： flash版本，
	swfVersionStr ： 如果没有flash那就使用这个自动安装flash的文件 expressInstall.swf
	flashvarsObj ： 这里是flashvars的值。这个常用来作为html与flash之间传递参数，本来是在params对象中的属性，由于考虑到常用和方便，所以单独取了出来。可以设置为null。
	parObj ： 详细的介绍http://kb2.adobe.com/cps/127/tn_12701.html
	play，loop，menu，quality，scale，salign，bgcolor，base，swliveconnect，flahvars，devicefont ，allowscriptaccess ，seamlesstabbing ，allowfullscreen ，allownetworking

	wmode   这个很重要，window，opaque，transparent（一般设为transparent透明或者opaque不透明）。
	当不设置时默认为window，这时已窗口方式呈现。这时object元素将始终显示在最上面，同时点击事件等也监听不到。

	attObj： attributes对象的属性--id，name，styleclass（不使用class，因为class也是ECMA4的保留关键字），align
	callbackFn：回调函数


##怎样使用SWFObject的JavaScript类库获得Flash Player的相关信息

	SWFObject包含了一个公共API，通过它你可以用JavaScript获得Flash Player的相关信息。
	
	swfobject.getFlashPlayerVersion()返回一个包含了已安装Flash Player主要版本（major:Number）、次要版本（minor:Number）、发行版本（release:Number）的JavaScript对象：
	
	var playerVersion = swfobject.getFlashPlayerVersion(); // returns a JavaScript object
	var majorVersion = playerVersion.major; // access the major, minor and release version numbers via their respective properties
	 
	
	swfobject.hasFlashPlayerVersion(versionNumbersString)返回一个Boolean值，表明特定版本的Flash插件是否已被安装：
	
	if (swfobject.hasFlashPlayerVersion("9.0.18")) {
	  // has Flash
	}
	else {
	  // no Flash
	}
	 
	
	需要注意的是，表示Flash版本的数字通常由四部分组成：major.minor.release.build，但是SWFObject只识别前3个数字，所以“WIN 9,0,18,0”（IE）或者“Shockwave Flash 9 r18”（其他浏览器）都会被翻译为“9.0.18”。


##使用演示

	
	swfobject.embedSWF("test6_flashvars.swf", "content5", "300", "120", "10.0.0", "expressInstall.swf", {name1:"hello",name2:"world",name3:"foobar"}, {menu:"false"}, {id:"dynamicContent5",name:"dynamicContent5"});


	
	swfobject.embedSWF("gen_shu.swf", "gen_swf1", "180", "105", "10.0.0",null,null,{wmode:"transparent"},null,function(){alert("已加载成功flash")});