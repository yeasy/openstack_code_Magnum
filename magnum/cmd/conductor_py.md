### conductor.py
提供一个 main 方法，可以命令行手动启动 conductor 服务（作为消息 RPC 服务）。
```python
def main():
    logging.register_options(cfg.CONF)
    cfg.CONF(sys.argv[1:], project='magnum')
    logging.setup(cfg.CONF, 'magnum')

    LOG.info(_LI('Starting server in PID %s') % os.getpid())
    LOG.debug("Configuration:")
    cfg.CONF.log_opt_values(LOG, std_logging.DEBUG)

    cfg.CONF.import_opt('topic', 'magnum.conductor.config', group='conductor')

    conductor_id = short_id.generate_id()
    endpoints = [
        docker_conductor.Handler(),
        k8s_conductor.Handler(),
        bay_conductor.Handler(),
        conductor_listener.Handler(),
    ]

    if (not os.path.isfile(cfg.CONF.bay.k8s_atomic_template_path)
            and not os.path.isfile(cfg.CONF.bay.k8s_coreos_template_path)):
        LOG.error(_LE("The Heat template can not be found for either k8s "
                      "atomic %(atomic_template)s or coreos "
                      "(coreos_template)%s. Install template first if you "
                      "want to create bay.") %
                  {'atomic_template': cfg.CONF.bay.k8s_atomic_template_path,
                   'coreos_template': cfg.CONF.bay.k8s_coreos_template_path})

    server = service.Service(cfg.CONF.conductor.topic,
                             conductor_id, endpoints)
    server.serve()
```
