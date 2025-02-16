# Ianotto's Homeserver

## Configuration

Create a `hosts.ini` file from the template and a `group_vars/all/secret.yml` using ansible-vault with the following vars:

- `system_password`
- `duckdns_token`
- `nextcloud_db_password`

## Installation

- `ansible-playbook run.yml -K --ask-vault-pass`
- Run `occ` commands in the nextcloud-app container to set the maintenance window
- Make sure Nextcloud uses cron (`settings/admin`)
- Run [Long running migration steps](https://docs.nextcloud.com/server/30/admin_manual/maintenance/upgrade.html#long-running-migration-steps) (not only after the initial installation but whenever required)

## General Infos

- Caddy reverse proxy installed as a system service
- Nextcloud and related are user services (`nextcloud`)
- System updates at 6:00 AM, only security ones
- Podman auto update at midnight
- Backup at 4 am
