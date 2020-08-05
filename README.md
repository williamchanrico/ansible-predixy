## Ansible Predixy

Simple ansible role to install Predixy - Redis Proxy.

Github: [https://github.com/joyieldInc/predixy](https://github.com/joyieldInc/predixy)

### Example Playbook

```yaml
---
- name: Predixy
  hosts: "{{ custom_hosts | default('tag_Hostgroup_example_predixy') }}"
  vars:
    predixy_config:
	  bind: 0.0.0.0:6379
      cluster:
        servers:
          - 10.x.x.x:6379
          - 10.x.x.x:6379

  roles:
    - predixy
```

### Under Construction

Simple installation and config should works.
