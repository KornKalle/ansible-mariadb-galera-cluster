<!-- START doctoc generated TOC please keep comment here to allow auto update -->

<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

-   [ansible-mariadb-galera-cluster](#ansible-mariadb-galera-cluster)
    -   [Requirements](#requirements)
    -   [Role Variables](#role-variables)
    -   [Example Playbook](#example-playbook)
    -   [License](#license)
    -   [Author Information](#author-information)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# ansible-mariadb-galera-cluster

An [Ansible](https://www.ansible.com) role to install/configure a [MariaDB-Galera Cluster](https://mariadb.com/kb/en/mariadb/what-is-mariadb-galera-cluster/).
Forked from https://github.com/mrlesmithjr/ansible-mariadb-galera-cluster.

This Role will install and configure a mariadb-cluster with all nodes in the group "galera-cluster" (The group name is overwritable).

## Requirements

- Ansible >= 2.7
- python3-libselinux for CentOS / RHEL

## Role Variables

You will most likely need to override the interface on which MariaDB will listen on, as this name depends on your virtualization / hardware platform:

    galera_cluster_bind_interface: "enp0s8"

The mariadb_bind_address will be calculated from the address of the interface you defined at the galera_cluster_bind_interface variable.
You can also directly set a bind address when overriding the variable mariadb_bind_address:

    mariadb_bind_address: 0.0.0.0

All Role variables are found at [defaults/main.yml](defaults/main.yml), you can override all of them, the default values will work in a clean environment.

## Example Playbook

[Example playbook](./playbook.yml)

## License

MIT

## Author Information

Nils Berg

-   nils.berg [at] helmholtz-berlin.de
-   n.berg [at] backslashseven.de
