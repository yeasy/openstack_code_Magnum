## cloud
定义在云环境中的一些支持。


### nova_driver.py
定义了三个使用 Nova 作为 Bay 类型的相关类。
* NovaBayBase：继承自 base.BayBase，基础类。
* NovaBay：继承自 NovaBayBase，声明了 destroy 和 stop 两个方法。
* NovaBayFactory：继承自 NovaBayBase，声明了 list、create 和 get_pod 方法。
