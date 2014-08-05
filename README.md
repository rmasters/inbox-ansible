# inbox

This role installs and configures an [Inbox][inbox-web] server from source.

Based on Inbox's [Vagrant setup script][inbox-setup].

## Requirements

Requires a Debian or RedHat family server.

## Role variables

*   `inbox.repo`: Git repository to get Inbox from
*   `inbox.branch`: Git version (branch, tag, commit) to checkout
*   `inbox.install_dir`: Where to install Inbox
*   `inbox.config_dir`: Where to store configuration files
*   `inbox.log_dir`: Where to store log files
*   `inbox.user`: User to run Inbox under

## Dependencies

-   [bennojoy.mysql](https://galaxy.ansible.com/list#/roles/1)

## Example playbook

```yaml
- hosts: servers
  roles:
    - role: rmasters.inbox
      # Modify defaults
      inbox:
        database:
          host: mydbserver.rds.amazon.com
```

See [Inbox-PHP][inbox-php-test-env]'s test environment for example usage.

## License

[MIT Licensed](LICENSE)

[inbox-web]: http://inboxapp.com/
[inbox-setup]: https://github.com/inboxapp/inbox/blob/master/setup.sh
[inbox-php-test-env]: https://github.com/rmasters/inbox-php/blob/master/tests/env
