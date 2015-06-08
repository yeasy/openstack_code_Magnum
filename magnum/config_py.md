## config.py
配置相关的变量和方法。

包括 Pecan 框架的应用配置信息。
```python
app = {
    'root': 'magnum.api.controllers.root.RootController',
    'modules': ['magnum.api'],
    'static_root': '%(confdir)s/public',
    'template_path': '%(confdir)s/api/templates',
    'debug': True,
    'errors': {
        404: '/error/404',
        '__force_dict__': True
    }
}
```

定义 parse_args 方法，来从配置文件中获取相关的配置信息。
```python
def parse_args(argv, default_config_files=None):
    cfg.CONF(argv[1:],
             project='magnum',
             version=version.version_string,
             default_config_files=default_config_files)
```
