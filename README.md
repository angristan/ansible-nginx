# Ansible role for Nginx

[![CircleCI](https://circleci.com/gh/angristan/ansible-nginx.svg?style=svg)](https://circleci.com/gh/angristan/ansible-nginx)

This is a role I made for myself but I tried to make it as reusable as possible while keeping it fitted to my use.

The role will install Nginx from the official APT **stable** repository for Debian or Ubuntu.

It will do some basic configuration like:

- Setting up nginx.conf
- Setting up the logrotate
- Setting up a default vhost
- Seeting up vhosts trough variables.

All the variables are in `defaults/main.yml`.

## Sample playbook

```yaml
---

- hosts: myhost
  roles: nginx
  vars:
    nginx_server_tokens: 'off'
    nginx_logrotate_rotate: 7
    nginx_vhosts:
      - name: 'blog'
        hostname: 'domain.tld'
        template: 'blog.j2'
```
