# jScrollPane 使用介绍

一个模拟滚动条的插件

http://jscrollpane.kelvinluck.com/settings.html#animateScroll

## 如何使用

###第一种直接引用

	<link type="text/css" href="components/jScrollPane/jquery.jscrollpane.css" rel="stylesheet"/>
	<script type="text/javascript" src="lib/jq_ud_mod.js">
	</script>
	<script type="text/javascript" src="components/jquery-mousewheel/jquery.mousewheel.js"></script>
	<script type="text/javascript" src="components/jScrollPane/jquery.jscrollpane.js"></script>

###第二种，已fis的component的组件生态引用

	@import "components/jquery-jscrollpane/jquery.jscrollpane.css";

	require('jquery-mousewheel');
	require('jquery-jscrollpane');
        require('jquery-mousewheel');

	$('.scroll-pane').jScrollPane();


##参数选项

	showArrows - boolean (default false)//显示滑杆两边的箭头

	maintainPosition - boolean (default true) //保持原位置,内容增加了，还继续保持

	stickToBottom- boolean (default false) //滑到底部，内容增加了，一直保持在底部

	stickToRight- boolean (default false)//滑到最右边

	autoReinitialise - boolean (default false)  // 自动调节滚动条的高度

	autoReinitialiseDelay - int (default 500)//  自动调节滚动条的高度的时间

	verticalDragMinHeight - int (default 0)//垂直拖拽的最小高度
 
    verticalDragMaxHeight - int (default 99999)//处置拖拽的最大高度
 
    horizontalDragMinWidth - int (default 0)//水平拖拽的长度
 
    horizontalDragMaxWidth - int (default 99999)//水平拖拽的最大长度

	contentWidth - int (default undefined)//内幕内用的宽度

	animateScroll - boolean (default false)//滚动动画

	animateDuration - int (default 300)//动画延迟

	animateEase - string (default 'linear')//动画轨迹

	hijackInternalLinks - boolean (default false)//截获内部链接，锚点

	verticalGutter - int (default 4)// 内容与滚动条的水平距离
 
	horizontalGutter - int (default 4)//内容与滚动条的高度距离

	mouseWheelSpeed - int (default 10)//鼠标滚动的速度

	arrowButtonSpeed - int (default 10)//方向键按钮的速度 

	arrowRepeatFreq - int (default 100)//按钮事件重复频率

	arrowScrollOnHover - boolean (default false)//接手鼠标在方向键上滑过的动作

	 verticalArrowPositions - string [split|before|after|os] (default split)//垂直方向上按钮的位置
 
    horizontalArrowPositions - string [split|before|after|os] (default split)//水平方向上按钮的位置
 
    enableKeyboardNavigation - boolean (default true)//是否接受键盘操作
 
    hideFocus - boolean (default false)//隐藏焦点
 
    clickOnTrack - boolean (default true)//路径上点击操作
 
    trackClickSpeed - int (default 30)//互动轨迹上的点击速度
 
    trackClickRepeatFreq - int (default 100)//滑动轨迹上的重复频率


##api方法

	var element = $('#my-element').jScrollPane({/* ...settings... */});

	var api = element.data('jsp');

	reinitialise(s) 重新初始化
	
	scrollToElement(ele, stickToTop, animate)  滚动到元素的节点

	scrollTo(destX, destY, animate)

	scrollToX(destX, animate)

	scrollToY(destY, animate)	

	scrollToPercentX(destPercentX, animate)  设置滚动内容水平的百分比

	scrollToPercentY(destPercentY, animate)  设置滚动内容垂直的百分比

	
	scrollBy(deltaX, deltaY, animate)

	scrollByX(deltaX, animate)	设置滚动内容的left值

	scrollByY(deltaY, animate)  设置滚动内容的top值

	positionDragX(x, animate)	设置滚动条的水平位置

	positionDragY(y, animate)  设置滚动条的垂直位置

	animate(ele, prop, value, stepCallback)

	getContentPositionX() 获取滚动的left值，相对于内容

	getContentPositionY() 获取滚动的top值，相对于内容

	getContentWidth()  获取滚动条的宽度

	getContentHeight() 获取滚动条内的高度

	getIsScrollableH() 是否有水平滚动条

	getPercentScrolledX()  获取滚动条的水平百分比  

	getPercentScrolledY()  获取滚动条的垂直百分比  

	getIsScrollableV() 是否有垂直滚动条

	getContentPane() 获取滚动条内的内容

	scrollToBottom(animate) 滚动到底部

	hijackInternalLinks()  当新增内容的时候，充值锚点

	destroy()  销毁对象


##监听事件

 	http://jscrollpane.kelvinluck.com/events.html


