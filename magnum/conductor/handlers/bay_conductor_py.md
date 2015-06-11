#### bay_conductor.py

处理对 bay 资源的操作。

* Handler：响应 bay 相关的 CRUD 操作。会调用 OpenStack 的客户端，传递相关的 heat 模板来实现对 bay 的操作。
* HeatPoller：实现对所创建 Stack 对象（bay）的状态查询。
