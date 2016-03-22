pulp
====

Ansible role which installs Qpid CPP server.


Examples
--------

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
      qpid_cpp_server_qpidd_config:
        auth: 'no'
```

This role requires [Config
Encoders](https://github.com/jtyr/ansible/blob/jtyr-config_encoders/lib/ansible/plugins/filter/config_encoders.py)
which must be configured in the `ansible.cfg` file like this:

```
[defaults]

filter_plugins = ./plugins/filter/
```

Where the `./plugins/filter/` containes the `config_encoders.py` file.


Role variables
--------------

List of variables used by the role:

```
# Whether to install EPEL YUM repo
qpid_cpp_server_epel_install: yes

# EPEL YUM repo URL for RHEL/CentOS 7
qpid_cpp_server_epel_yumrepo_url: "{{ yumrepo_epel_url | default('https://dl.fedoraproject.org/pub/epel/' + ansible_distribution_major_version + '/' + ansible_userspace_architecture + '/') }}"

# Additional EPEL YUM repo params
qpid_cpp_server_epel_yumrepo_params: {}

# YUM repo for RHEL/CentOS 6 only
qpid_cpp_server_qpid_yumrepo_url: https://copr-be.cloud.fedoraproject.org/results/@qpid/qpid/epel-6-$basearch/

# Additional Qpid YUM repo params
qpid_cpp_server_qpid_yumrepo_params: {}

# Package to be installed (version can be specified here)
qpid_cpp_server_pkg: qpid-cpp-server

# Default storage package (version can be specified here)
qpid_cpp_server_storage_pkg: qpid-cpp-server-linearstore

# Default Qpid daemon config file
qpid_cpp_server_daemon_config_file: /etc/qpid/qpidd.conf

# Default qpidd config
qpid_cpp_server_qpidd_config: {}
```


Dependencies
------------

- [Config Encoders](https://github.com/jtyr/ansible/blob/jtyr-config_encoders/lib/ansible/plugins/filter/config_encoders.py)


License
-------

MIT


Author
------

Jiri Tyr
