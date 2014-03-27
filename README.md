# New Relic PHP Agent

Sets up New Relic PHP agent: https://docs.newrelic.com/docs/php/new-relic-for-php

## Requirements

Debian Wheezy, with PHP installed. This role tries to restart PHP-FPM and/or the Apache web server.

## Role Variables

The variables that can be passed to this role and a brief description about them are as follows

    # License key (required)
    newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16

    # Application name (required)
    newrelic_appname: myapp-host1;myapp

# Dependencies

Requires the New Relic repository to be set up; depends on [sivel.newrelic](https://github.com/sivel/ansible-newrelic) for this purpose.

## Examples

### Paramaterized Role

    ---
    - hosts: all
      roles:
        - { role: praseodym.newrelic, newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16, newrelic_appname: myapp-host1;myapp }

### Vars

    ---
    - hosts: all
      vars:
        newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16
        newrelic_appname: myapp-host1;myapp
      roles:
        - praseodym.newrelic-php

### Group vars

#### group_vars/production

    ---
    newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16
    newrelic_appname: myapp-host1;myapp

#### site.yml

    ---
    - hosts: all
      roles:
        - praseodym.newrelic-php