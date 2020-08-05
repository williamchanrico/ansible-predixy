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
	  	# Choose either ONE of these 2:
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

### Under Construction

Simple installation and config should works.
