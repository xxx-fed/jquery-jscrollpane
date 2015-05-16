# jScrollPane 使用介绍

一个模拟滚动条的插件


## 如何使用

###第一种直接引用

	<link type="text/css" href="components/jScrollPane/jquery.jscrollpane.css" rel="stylesheet"/>
	<script type="text/javascript" src="lib/jq_ud_mod.js">
	</script>
	<script type="text/javascript" src="components/jquery-mousewheel/jquery.mousewheel.js"></script>
	<script type="text/javascript" src="components/jScrollPane/jquery.jscrollpane.js"></script>

###第二种，已fis的component的组件生态引用

	@import "components/jScrollPane/jquery.jscrollpane.css";

	require('jquery-mousewheel');
	require('jScrollPane');

	$('.scroll-pane').jScrollPane();