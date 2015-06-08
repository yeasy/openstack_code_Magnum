# etc

## magnum.conf.sample
一个 Mangum 服务的配置样例。

包括制定 api 参数、conductor 参数、数据库，各种后端参数等。


## policy.json
制定访问的权限策略。
```json
{
    "context_is_admin":  "role:admin",
    "admin_or_owner":  "is_admin:True or project_id:%(project_id)s",
    "default": "rule:admin_or_owner",
    "admin_api": "is_admin:True",
}
```
