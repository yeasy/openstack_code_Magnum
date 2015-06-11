### rpc.py
基于 oslo_messaging 类的一些封装。

oslo_messaging 对消息中间件进行封装，用户无需关心后端是否是 AMQP 还是 zeromq 等实现。

只需要指定传输层信息、主体信息，然后客户端就可以调用服务端的方法了。
