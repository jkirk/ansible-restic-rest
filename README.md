 Restic rest-server
=========

Deploy rest-server for restic.
The intended usage pattern is that rest-server instances are behind an edge proxy,
which would handle authorization and SSL itself, if necessary.


All servers can be started via `systemctl start rest-server.target`

 Requirements
------------

None

 Role Variables
--------------

```yaml
restic_rest_v: '0.10.0'
restic_rest_repos:
  - path: '/user/home/backup'
    listen: ':8000'
    restic_htaccess_user: admin
    restic_htaccess_password: Chang3Me
  - path: '/user/home/backup_something_else'
    listen: ':8001'
    # custom arguments
    args: '--no-auth --append-only --prometheus'
restic_rest_service_enable: true
```


 License
-------

BSD [![License](https://raw.githubusercontent.com/donat-b/ansible-restic-rest/master/.github/license.svg?sanitize=true)](https://github.com/donat-b/ansible-restic-rest/blob/master/LICENSE)
