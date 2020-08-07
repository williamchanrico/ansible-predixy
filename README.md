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
        # Choose either servers_dynamic_domain OR servers_static

        # Dynamically resolve target servers domain via ansible
        servers_dynamic_domain: target-cluster.service.consul
        servers_dynamic_port: 6379

        # Or statically configure target servers
        servers_static:
          - 10.1.2.3:6379
          - 10.1.2.4:6379
          - 10.1.2.5:6379

  roles:
    - predixy
```

Note: The `predixy_config.cluster.servers_dynamic_domain` option will try to [resolve](./tasks/config.yml#L9) the domain from remote server.

### Under Construction

Simple installation and config should works.
