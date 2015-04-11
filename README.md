# Usage

Each playbook (`*.yml` in the main directory) needs to define its
target hosts.  This is done with `-hosts: `, i.e., ldap.yml defines
that its hosts are the ldap_clients (group).  That said, to enable
ldap authentication on a set of machines we need to modify the
inventory file (`/etc/ansible/hosts` by default) to include a
ldap_clients group. e.g.

```
[ldap_clients]
idea.tolabaki..her.wn
thiroros.tolabaki..her.wn
```

By convention we use the playbooks name followed by `_clients` for
clients and followed by `_server` for servers.  Note that we do not
use plural for servers since we usually deploy a single server per
service.

# Notes

## ldap.yml

Please replace `<secret>` in `ldap/files/nslcd.conf` with the actual
password before deploying.

#To-Do

* Move configuration files over if needed
* Apply patch
