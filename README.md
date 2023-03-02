Ansible Role: ansible_role_pam_limits
=========

Configures PAM limits through configuraton files in /etc/security/limits.d on the following Linux distributions:

<ul>
<li>Red Hat Enterprise Linux 7
</ul>

Requirements
------------

This role is dependent on the following Ansible collections:

`community.general`


Role Variables
--------------

| Variable | Required | Default | Comments |
| -------- | -------- | ------- | -------- |
| `filename` | Yes | | Name of the configuration file to hold limits configuration, the file will be created in `/etc/security/limits.d`. |
| `order` | Yes | | Integer prefix for the file specified in `filename`. |
| `domain` | Yes | | What is the limit applied to, refer to `limits.conf.5` for valid values. |
| `backup` | No | | Boolean. Optionally backup the configuration file at changes. |
| `comment` | No | | Optional comment to describe the settings. |
| `limit_item` | Yes | | Specifies which resource we are going to limit for the domain Refer to `limits.conf.5` for valid values. |
| `limit_type` | Yes | | What type of limit `hard` or `soft`. Refer to `limits.conf.5` for additional explainations. |
| `value` | Yes| | Value of the limit to be applied. |


Dependencies
------------

None.

Example Playbook
----------------


    - hosts: servers

      vars:
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

      roles:
         - ansible_role_pam_limits

License
-------

MIT

Author Information
------------------

Mattias Jonsson
