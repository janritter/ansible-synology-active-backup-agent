# Ansible role - Synology Active Backup Agent - Ubuntu

> Ansible role to install and configure Synology Active Backup for Business agent on ubuntu (tested with Ubuntu 18.04.)

:warning: This role is still very basic and was only tested on Ubuntu 18.04.
It was used to successfully install and configure the agent to the point where it successfully connects to the NAS and backups can be managed from there.

## Example playbook

```yaml
- name: Servers
  hosts: all
  roles:
    - role: janritter.synology_active_backup_agent
      vars:
        active_backup_address: 127.0.0.1
        active_backup_username: "synology-username"
        # Fake example encrypted by ansible-vault
        active_backup_password: !vault |
          $ANSIBLE_VAULT;1.2;AES256;tailscale
          32616238303134343065613038383933333733383765653166346564363332343761653761646363
          66376665631616362353839363646530373536316539646561373535610a64333439623439633237
          3537
```

## Variables

### `active_backup_address`

IP or hostname of the Synology NAS running Active Backup for Business

### `active_backup_username`

Username of the Synology NAS user to access Active Backup for Business

### `active_backup_password`

Password of the Synology NAS user to access Active Backup for Business
