# Ansible Role: PHP

This role installs PHP on Debian/Ubuntu, RHEL/CentOS and Fedora servers.

[![Ansible Role: PHP](https://img.shields.io/ansible/role/55141?style=flat-square)](https://galaxy.ansible.com/thorian93/php)
[![Ansible Role: PHP](https://img.shields.io/ansible/quality/55141?style=flat-square)](https://galaxy.ansible.com/thorian93/php)
[![Ansible Role: PHP](https://img.shields.io/ansible/role/d/55141?style=flat-square)](https://galaxy.ansible.com/thorian93/php)

## Known issues

None.

## Requirements

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:

    - hosts: foobar
      roles:
        - role: thorian93.php
          become: yes

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    php_major_version: 7

Define the major PHP version.

    php_minor_version: 4

Define the minor PHP version.

    php_third_party_enabled: 'false'

Decide if a third party repository should be used. For details on those repositories see the `vars/` folder for the respective distribution. Probably this role will fail, if the third party repository is not enabled.

    php_ppa_enabled: 'false'
    php_ppa: "ppa:ondrej/php"

Decide if an Ubuntu PPS should be used and if yes which. The default is the well known [Sury](https://deb.sury.org/) repository. Probably this role will fail, if the PPA for Ubuntu is not enabled.

    php_enabled_modules:
    - curl

Decide which PHP module should be installed.

    php_config_options: []

Provide additional PHP configuration.

## Dependencies

[![Ansible Role: Webserver](https://img.shields.io/ansible/role/51301?style=flat-square)](https://galaxy.ansible.com/thorian93/webserver)</br>
*For webserver detection.*

## OS Compatibility

This role ensures that it is not used against unsupported or untested operating systems by checking, if the right distribution name and major version number are present in a dedicated variable named like `<role-name>_stable_os`. You can find the variable in the role's default variable file at `defaults/main.yml`:

    role_stable_os:
      - Debian 10
      - Ubuntu 18
      - CentOS 7
      - Fedora 30

If the combination of distribution and major version number do not match the target system, the role will fail. To allow the role to work add the distribution name and major version name to that variable and you are good to go. But please test the new combination first!

Kudos to [HarryHarcourt](https://github.com/HarryHarcourt) for this idea!

## Example Playbook

    ---
    - name: "Run role."
      hosts: all
      become: yes
      roles:
        - ansible-role-php

## Contributing

Please feel free to open issues if you find any bugs, problems or if you see room for improvement. Also feel free to contact me anytime if you want to ask or discuss something.

## Disclaimer

This role is provided AS IS and I can and will not guarantee that the role works as intended, nor can I be accountable for any damage or misconfiguration done by this role. Study the role thoroughly before using it.

## License

MIT

## Author Information

This role was created in 2020 by [Thorian93](http://thorian93.de/).
