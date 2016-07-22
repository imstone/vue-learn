

##VUE源码学习笔记
####入口从src文件夹开始看起


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


#### /src/instance/internal/state.js 

定义vue的$data使其可以使用新的属性`set`和`get`，相关`Object.defineProperty`方法可以百度一下
	
	Vue.prototype._initState 


##### /src/instance/vue.js
注释了一些备注，$开头的是公共API _开头的是私有API，没有前缀的是代理用户。
初始化参数，并调用初始化_init方法。
包括`$el` 等参数，仔细看这里你能知道基本所有的vue配置属性。

#### /src/instance/internal/events.js
定义正则，以`v-on`和`@`开头的为vue事件

	Vue.prototype._initEvents
调用下面一些初始化函数。

	Vue.prototype._initProps

初始化props
 



