

##VUE源码学习笔记
入口从src文件夹开始看起

###instance文件夹下是最基本的类方法

>/instance/

#### /src/instance/vue.js
注释了一些备注，$开头的是公共API _开头的是私有API，没有前缀的是用户定义了Vue这个构造函数，并调用`_init()`,进行初始化。
然后依次执行各种初始化函数
我们看到如下初始化函数，我们依次看下面的文件

	initMixin(Vue)
	stateMixin(Vue)
	eventsMixin(Vue)
	lifecycleMixin(Vue)
	miscMixin(Vue)

公共接口文件

	dataAPI(Vue)
	domAPI(Vue)
	eventsAPI(Vue)
	lifecycleAPI(Vue)



>/instance/internal

#### /src/instance/internal/init.js 
**初始化模块**
初始化模块会被所有实例调用。

为实例添加各种属性，并合并`options`；

合并了包括`this.constructor.options`,`options`,`this`的options

并调用了一些函数进行初始化。


##### /src/instance/vue.js
注释了一些备注，$开头的是公共API _开头的是私有API，没有前缀的是代理用户。
<<<<<<< HEAD
初始化参数，并调用初始化_init方法。
包括`$el` 等参数，仔细看这里你能知道基本所有的vue配置属性。

#### /src/instance/internal/state.js 

定义vue的$data使其可以使用新的属性`set`和`get`，相关`Object.defineProperty`方法可以百度一下
	
	Vue.prototype._initState 
初始化合并好的参数，并进行一些参数的判断。


	Vue.prototype._initData 
初始化data参数，	并执行data函数得到初始值。所以这里也显示了data必须是一个可以返回对象的函数。
并检查props里和data定义对象是不是有 重复的。


	Vue.prototype._setData

原生setter的封装。


#### /src/instance/internal/events.js
定义正则，以`v-on`和`@`开头的为vue事件

	Vue.prototype._initEvents
调用下面一些初始化函数。

	Vue.prototype._initProps

初始化props 
 
=======
初始化参数，并调用初始化_init方法。
包括`$el` 等参数，仔细看这里你能知道基本所有的vue配置属性。

#### /src/instance/internal/state.js 

定义vue的$data使其可以使用新的属性`set`和`get`，相关`Object.defineProperty`方法可以百度一下
	
	Vue.prototype._initState 
初始化合并好的参数，并进行一些参数的判断。


	Vue.prototype._initData 
初始化data参数，	并执行data函数得到初始值。所以这里也显示了data必须是一个可以返回对象的函数。
并检查props里和data定义对象是不是有 重复的。


	Vue.prototype._setData

原生setter的封装。


#### /src/instance/internal/events.js
定义正则，以`v-on`和`@`开头的为vue事件

	Vue.prototype._initEvents
调用下面一些初始化函数。

	Vue.prototype._initProps

初始化props 
 

###util文件夹是一些常用工具函数


> /src/util

####/src/util/index.js

调用了所有工具函数。

####/src/util/lang.js

	function set

设置函数的属性，并监听属性变化

	function del

删除属性，并触发改变
	
	function hasOwn

Object 对象自有hasOwnProperty的封装。检查对象是不是存在属性。

	funciton isLiteral 
检查正则是不是字符串。

	function isReserved
	
检查是不是保留值，是不是以$和_开头

	function toString
保证输出

	function toNumber
检查数字类字符串输出数字

	export function def 
定义一个对象的属性并赋值一些基本属性，比如是否可枚举。

	export function debounce
延迟函数 


##### /src/instance/vue.js


	export function 
	
	
	export function debounce
延迟函数 

#### src/directives/public/if.js
v-if 内置指令
进入函数首先执行bind函数。
第一步确认v-else是否存在，如果存在就移除else元素。
并创建v-if的注释块，作为将来插入v-if里元素的参考点。

先执行bind
>>>>>>> 2f2416aa4d9b2414d86ad135f16bbe33642e6ecf

###util文件夹是一些常用工具函数


> /src/util

####/src/util/index.js

调用了所有工具函数。

####/src/util/lang.js

	function set

设置函数的属性，并监听属性变化

	function del

删除属性，并触发改变
	
	function hasOwn

Object 对象自有hasOwnProperty的封装。检查对象是不是存在属性。

	funciton isLiteral 
检查正则是不是字符串。

	function isReserved
	
检查是不是保留值，是不是以$和_开头

	function toString
保证输出

	function toNumber
检查数字类字符串输出数字

	export function def 
定义一个对象的属性并赋值一些基本属性，比如是否可枚举。

	export function debounce
延迟函数 



