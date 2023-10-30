Role Name
=========


Role for install lighthouse


Requirements
------------


Role Variables
--------------

Переменные для установки кредов
default/main.yml:
```yaml
clickhouse_user: netology
clickhouse_password: netology
```

Переменные для скачивания lighthouse из git и конфигурационных файлов lighthouse/nginx
vars/main.yml
```yaml
lighthouse_vcs: https://github.com/VKCOM/lighthouse.git
lighthouse_dir: /var/lib/lighthouse
lighthouse_access_log_name: lighthouse_access
```

Dependencies
------------

Требуется роль [clickhouse-role](https://github.com/zatulik2606/clickhouse-role.git)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
hosts: lighthouse
roles:
  - role: lighthouse-role
```

Для вывода строки подключения можно использовать post_tasks

```yaml
post_tasks:
  - name: Show connect URL lighthouse
    debug:
      msg: "http://{{ ansible_host }}/#http://{{ hostvars['clickhouse-01'].ansible_host }}:8123/?user={{ clickhouse_user }}"
```

License
-------

MIT

Author Information
------------------
