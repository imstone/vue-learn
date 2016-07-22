

##VUE源码学习笔记
####入口从src文件夹开始看起


>/instance/

	/src/instance/vue.js
注释了一些备注，$开头的是公共API _开头的是私有API，没有前缀的是用户定义了Vue这个构造函数，并调用_init(),进行初始化。
然后依次执行各种初始化函数

>/instance/internal

	/src/instance/internal/init.js 
初始化模块，
初始化模块会被所有实例调用。

为实例添加各种属性，并合并options；



    /src/instance/vue.js
注释了一些备注，$开头的是公共API _开头的是私有API，没有前缀的是代理用户。
初始化参数，并调用初始化_init方法。

    /src/instance/internal/events.js



