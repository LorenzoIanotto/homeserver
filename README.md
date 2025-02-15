# Ianotto's Homeserver

## Configuration

Create a `hosts.ini` file from the template and a `group_vars/all/secret.yml` using ansible-vault with the following vars:

- `system_password`
- `duckdns_token`
- `nextcloud_db_password`

## Installation

`ansible-playbook run.yml -K --ask-vault-pass`
