# Angular

Angular (进阶demo)

ng-click等事件绑定，触发之后直接自动调用$apply方法进入angular context,然后使用$digest 来循环遍历$watch列表，更新相关的dom.

而自定义指令里面绑定的监听事件，触发之后不会进入angular context，所以不会触发脏检查，从而不会更新数据。



