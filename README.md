Ansible role Yum package management
---

# Example

```yaml
---
- hosts: all
  become: yes
  vars:
    yum_install_packages:
      - python-pip

  pre_tasks:
    - name: Update yum cache.
      yum:
        update_cache: yes
        cache_valid_time: 600
      when: ansible_os_family == 'RedHat'

  roles:
    - mallear.yum
```