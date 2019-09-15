f5-role-facts
=========

Simple example Role that gets ansible facts from a BIG-IP and returns system information.


Role Variables
--------------

Role expects **provider** to be passed to it. The defaults are below.

```
provider:
  server: "{{private_ip}}"
  user: "{{ansible_user}}"
  password: "{{ansible_ssh_pass}}"
  server_port: 8443
  validate_certs: no
```

Example Playbook
----------------

```
---
- name: Get F5 Facts
  hosts: f5
  connection: local
  gather_facts: no

  tasks:

  - include_role:
      name: focrensh.f5-role-facts
```
