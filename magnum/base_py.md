## base.py
定义了若干抽象基础元类。

这里面大部分类目前都没有被使用，只有 BayBase 被 magnum.cloud 中的 NovaBayBase 使用了。

### Bay 相关
* BayBase：基础抽象元类。
* Bay：继承自 BayBase，声明了 destroy、stop 两个方法。
* BayFactory：继承自 BayBase，声明了 list、create 和 get_pod 三个方法。

### Container 相关
* ContainerBase：基础抽象元类。
* Container：继承自 ContainerBase，声明了 destroy、execute、info、kill、logs、pause、reboot、unpause 等容器相关方法。
* ContainerFactory：继承自 ContainerBase，声明了 create、list 方法。

### Pod 相关
* Pod：继承自 ContainerBase。
* PodFactory：继承自 ContainerBase，声明 create、list 方法。
