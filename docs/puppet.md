# Puppet overview

The following modules are part of the hardening framework:

Base Operating System

* [puppet-os-hardening](https://github.com/TelekomLabs/puppet-os-hardening)
* [puppet-ssh-hardening](https://github.com/TelekomLabs/puppet-ssh-hardening)

Database

* [puppet-mysql-hardening](https://github.com/TelekomLabs/puppet-mysql-hardening)
* [puppet-postgres-hardening](https://github.com/TelekomLabs/puppet-postgres-hardening)

Web Server

* [puppet-nginx-hardening](https://github.com/TelekomLabs/puppet-nginx-hardening)
* [puppet-apache-hardening](https://github.com/TelekomLabs/puppet-apache-hardening)

Example

* [example-puppet-hardening](https://github.com/TelekomLabs/example-puppet-hardening)

## Publishing Puppet Modules

Simple enough: If you have your `Modulefile` and `metadata.json` ready, just run:

    cd puppet-xxx-hardening/
    puppet module build .

Results are in pkg.

The two files may not get merged correctly, so please diff:

    colordiff metadata.json pkg/puppet-*-hardening/metadata.json
