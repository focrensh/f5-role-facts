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


| Variable   | Required | Default | Example                    | Info                                                                                                                                                            |
|------------|----------|---------|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| provider   | yes      | -       | provider: "{{ provider }}" | The  **provider**  dictionary is used in the role to define connection details to the BIG-IP in the same way F5 Modules work.                                   |
| atc_method | no       | GET     | atc_method: GET            | <li>atc_method accepted values include [POST, GET] for all services, and [DELETE]for AS3 only. <li>atc_deploy role currently does not support AS3 PATCH method. |
|            |          |         |                            |  <li>item1 <li>item2                                                                                                                                            |
|            |          |         |                            |                                                                                                                                                                 |
|            |          |         |                            |                                                                                                                                                                 |
|            |          |         |                            |                                                                                                                                                                 |
