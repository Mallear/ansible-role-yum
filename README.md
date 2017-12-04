Ansible role Yum package management
---

Manage a list of packages with yum package manager.

# Example

```yaml
---
- hosts: all
  become: yes
  vars:
    yum_install_packages:
      - python-pip
      - name: python-setuptools
        state: update

  pre_tasks:
    - name: Update yum cache.
      yum:
        update_cache: yes
        cache_valid_time: 600
      when: ansible_os_family == 'RedHat'

  roles:
    - Mallear.yum
```