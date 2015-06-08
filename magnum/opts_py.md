## opts.py

主要定义 list_opts 方法，返回所有的选项。

```python
def list_opts():
    return [
        ('DEFAULT',
         itertools.chain(magnum.api.auth.AUTH_OPTS,
                         magnum.common.magnum_keystoneclient.trust_opts,
                         magnum.common.paths.PATH_OPTS,
                         magnum.common.utils.UTILS_OPTS,
                         (magnum.openstack.common.eventlet_backdoor
                          .eventlet_backdoor_opts),
                         log.generic_log_opts,
                         log.log_opts,
                         log.common_cli_opts,
                         log.logging_cli_opts,
                         magnum.openstack.common.periodic_task.periodic_opts,
                         )),
        ('api', magnum.api.app.API_SERVICE_OPTS),
        ('bay', magnum.conductor.template_definition.template_def_opts),
        ('conductor', magnum.conductor.config.SERVICE_OPTS),
        ('database', magnum.db.sqlalchemy.models.sql_opts),
        ('docker', magnum.conductor.handlers.docker_conductor.docker_opts),
        ('heat_client', magnum.common.clients.heat_client_opts),
        ('bay_heat', magnum.conductor.handlers.bay_conductor.bay_heat_opts),
    ]
```
