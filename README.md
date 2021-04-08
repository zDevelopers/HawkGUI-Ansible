# HawkGUI-Ansible

Ansible configuration to deploy Hawk website.

To deploy the latest commit from the `master` branch, run:

```shell
$ ansible-playbook --ask-vault-pass playbook.yml
```

For non-interactive setups, write the vault password to a file and run:

```shell
$ ansible-playbook --vault-password-file /path/to/vault-password-file playbook.yml
```

To install into another server, copy the `group_vars/thestias` folder to a new one,
change data you need to change, and update the hosts used in `playbook.yml`.

The `vault.yml` file is encrypted for obvious reasons, but here is its structure:

```yaml
# Only used in group_vars/thestias/vars.yaml
thestias_become_password:

# Required for installation
hawk:
  secret_key: 
  sentry_dsn: 
  database:
    host:
    port:
    user: 
    password: 
    name: 
```
