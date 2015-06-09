### app.py

主要的 PeCan APP 配置，包括注册 API 的选项，提供初始化参数等。
```python
API_SERVICE_OPTS = [
    cfg.IntOpt('port',
               default=9511,
               help='The port for the magnum API server'),
    cfg.StrOpt('host',
               default='127.0.0.1',
               help='The listen IP for the magnum API server'),
    cfg.IntOpt('max_limit',
               default=1000,
               help='The maximum number of items returned in a single '
                    'response from a collection resource.')
]
```

setup_app 方法返回一个 WSGi 应用对象，是响应 API 请求的入口。
```python
def setup_app(config=None):
    if not config:
        config = get_pecan_config()

    app_conf = dict(config.app)

    app = pecan.make_app(
        app_conf.pop('root'),
        logging=getattr(config, 'logging', {}),
        wrap_app=middleware.ParsableErrorMiddleware,
        **app_conf
    )

    return auth.install(app, CONF, config.app.acl_public_routes)
```

从 config.py 中读取配置信息，然后直接启动添加 ACL 规则后的应用。
