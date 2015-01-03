pulp
====

Ansible role which installs Qpid CPP server.


Example
-------

```
---

# Example how to use the role
- hosts: myhost1
  roles:
    - qpid_cpp_server

# Example how to change the qpidd setting
- hosts: myhost2
  roles:
    - role: qpid_cpp_server
      qpid_cpp_server_config:
        auth: 'no'
```


Role variables
--------------

List of variables used by the role:

```
# Default qpidd config
qpid_cpp_server_qpidd_config: {}

# Default storage package
qpid_cpp_server_storage_pkg: qpid-cpp-server-store

# Default Qpid daemon config file
qpid_cpp_server_daemon_config_file: /etc/qpid/qpidd.conf

# Default YUM repository
qpid_cpp_server_yum_repo:
  pulp:
    name: Pulp Project repository
    baseurl: https://repos.fedorapeople.org/repos/pulp/pulp/stable/latest/$releasever/$basearch/
    gpgcheck: 0
```


Dependencies
------------

* [`yumrepo`](https://github.com/picotrading/ansible-yumrepo) role


License
-------

MIT


Author
------

Jiri Tyr
