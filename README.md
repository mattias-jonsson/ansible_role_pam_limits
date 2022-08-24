ansible_role_pam_limits
==============

This role performs the following actions:

* Configures PAM limits through configuraton files in /etc/security/limits.d

Requirements
---------------

This role has been tested on the following Operating Systems:

* Red Hat Enterprise Linux 7


Role variables
---------------

Variables used in the role:

ansible_role_pam_limits:
    - filename:
    order:
    settings:
    - domain:
        backup:
        comment:
        limit_item:
        limit_type:
        value:


`ansible_role_pam_limits` TODO Description  
`filename` TODO Description  
`order` TODO Description  
`settings` TODO Description  
`domain` TODO Description  
`backup` TODO Description  
`comment` TODO Description  
`limit_item` TODO Description  
`limit_type` TODO Description  
`value` TODO Description


Sample configuration
---------------

```yaml
ansible_role_pam_limits:
- filename: example.conf
  order: 99
  settings:
  - domain: '*'
    backup: yes
    comment: Example tuning
    limit_item: core
    limit_type: soft
    value: unlimited
```
