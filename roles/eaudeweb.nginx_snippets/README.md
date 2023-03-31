# Ansible Role: Nginx

Extends geerlingguy.nginx role.

Should be used after the geerlingguy.certbot role to make sure certificates are generated.

## Requirements

- geerlingguy.nginx Role

## Role Variables

See geerlingguy.nginx

## Dependencies

- geerlingguy.nginx Role

## Example Playbook

    - hosts: server
      roles:
        - { role: geerlingguy.certbot }
        - { role: eaudeweb.nginx }

## License

MIT / BSD
