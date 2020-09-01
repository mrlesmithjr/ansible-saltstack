# Role Name

An [Ansible](https://www.ansible.com) role to install/configure [SaltStack](https://saltstack.com/)

## Requirements

None

## Role Variables

[defaults/main.yml](defaults/main.yml)

## Dependencies

None

## Example Inventory

```yaml
all:
    hosts:
        example-host:
            ansible_host: example-host
            ansible_connection: ssh
    children:
        salt:
            hosts:
                saltstack_master:
                    ansible_host: master-host
                    ansible_connection: ssh
                    ansible_user: ubuntu
                saltstack_minion:
                    ansible_host: minion-host
                    ansible_connection: ssh
                    ansible_user: ubuntu
```

## Example Playbook

```yaml
- name: Install SaltStack Master and minions node
  hosts: salt
  gather_facts: yes
  become: yes
  tags: ['salt']

  roles:
    - role: ansible-saltstack
```


## License

MIT

## Author Information

Larry Smith Jr.

-   [EverythingShouldBeVirtual](http://everythingshouldbevirtual.com)
-   [@mrlesmithjr](https://twitter.com/mrlesmithjr)
-   mrlesmithjr [at] gmail.com
