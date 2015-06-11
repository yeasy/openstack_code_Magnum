### __init__.py
暴露在外面的是各个模类的别名。

```python
Container = container.Container
Bay = bay.Bay
BayLock = baylock.BayLock
BayModel = baymodel.BayModel
Node = node.Node
Pod = pod.Pod
ReplicationController = rc.ReplicationController
Service = service.Service

__all__ = (Bay,
           BayLock,
           BayModel,
           Container,
           Node,
           Pod,
           ReplicationController,
           Service)
```
