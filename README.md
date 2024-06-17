# ansible role - nextcloud docker stack (nextcloud / mariadb / redis / nginx)


#### hosts.yml - inventory example
```
---

nextcloud:
  hosts:
    host1.example:

```

#### nextcloud.yml - playbook example
```
---

- name: Deploy nextcloud

  hosts: nextcloud

  gather_facts: false

  roles:
    - nextcloud

  vars:

    ansible_user: example_user

    docker_user: example_user

    nextcloud_docker_stack_directory: "/home/example_user/docker_stacks/nextcloud_docker_stack"

    nextcloud_network_subnet: "172.17.0.0/24"
    nextcloud_network_gateway: "172.17.0.1"

    nextcloud_user_id: 1000
    nextcloud_group_id: 1000

    db_database: "nextcloud"
    db_user: "DB_USER"
    db_password: "DB_PASSWORD"
    db_root_password: "DB_ROOT_PASSWORD"

    nextcloud_admin_user: "NEXTCLOUD_ADMIN_USER"
    nextcloud_admin_password: "NEXTCLOUD_ADMIN_PASSWORD"
    nextcloud_trusted_domains: "'nextcloud.mydomain.com'"
    nextcloud_overwritecliurl: "https://nextcloud.mydomain.com"
    nextcloud_overwriteprotocol: "https"

    nginx_http_port: 8080
```