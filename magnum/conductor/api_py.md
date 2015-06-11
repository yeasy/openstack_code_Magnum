### api.py

#### API 类
作为 AMQP 客户端，接收指定 topic 的消息，执行相关操作，主要是对资源的 CRUD。

* bay_create
* bay_delete
* bay_list
* bay_show
* bay_update
* baymodel_create
* baymodel_delete
* baymodel_list
* baymodel_show
* container_create
* container_delete
* container_execute
* container_list
* container_logs
* container_pause
* container_reboot
* container_show
* container_start
* container_stop
* container_unpause
* pod_create
* pod_delete
* pod_list
* pod_show
* pod_update
* rc_create
* rc_delete
* rc_list
* rc_show
* rc_update
* service_create
* service_delete
* service_list
* service_show
* service_update


#### ListenerAPI 类
发送 ping_conductor 消息。
