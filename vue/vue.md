
![image icon](http://vuejs.org.cn/images/logo.png =30*30)
##VUE源码学习笔记
####入口
> 从src文件夹下开始看起

    /src/instance/vue.js
注释了一些备注，$开头的是公共API _开头的是私有API，没有前缀的是代理用户。
初始化参数，并调用初始化_init方法。

    /src/instance/internal/events.js


####
