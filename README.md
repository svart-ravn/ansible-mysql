# ansible-mysql-repl

Used to setup mysql replication

Replication for two hosts can be setup in the following way:
```
> cat inventory/hosts
[master]
192.168.174.144 mysql_repl_type="full"

[slave]
192.168.174.146 mysql_repl_role="slave" mysql_repl_type="full" mysql_repl_master="192.168.174.144"

> cat playbook/setup_repl.yml
--- 
- hosts: all
  roles: ansible-mysql-repl

> ansible-playbook playbook/setup_repl.yml

```
