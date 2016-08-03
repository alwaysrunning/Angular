# Angular

1.浏览器先将html转化为dom, 然后交给compile服务;

2.compile服务找到指令以及所对应的dom结构，进行绑定;

3.每个指令会执行compile函数，执行完之后会返回link函数，再执行link函数;
(自定义指令里面，如果需要操作dom，改变数据模型时用link函数而不是compile函数)

4.在执行compile，link函数的过程中，插入指令所绑定的变量，会生产一个watch（监测绑定的变量值），由于会产生很多watch,这样就
形成一个$watch列表。

5.ng-click等事件触发之后直接调用$apply方法进入angular context,然后使用$digest 来循环遍历$watch列表，更新相关的dom.

而自定义指令里面绑定的监听事件，触发之后不会进入angular context，所以不会触发脏检查，从而不会更新数据。



