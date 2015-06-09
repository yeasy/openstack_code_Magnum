### config.py
Pecan 框架的配置信息。
```python
app = {
    'root': 'magnum.api.controllers.root.RootController',
    'modules': ['magnum.api'],
    'debug': False,
    'hooks': [
        hooks.ContextHook(),
        hooks.RPCHook(),
        hooks.NoExceptionTracebackHook(),
    ],
    'acl_public_routes': [
        '/'
    ],
}
```
