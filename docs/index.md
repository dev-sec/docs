# Telekom Security Automation

## Scope

Server Hardening is not a new topic. Various people around the world spent ages on this topic. Why do we need another?

At Deutsche Telekom we need to manage thousands of servers for our customers and ourselves. All servers need to be configured properly and maintained. It becomes quite a task to keep all servers with the best known configuration.

Since we use Chef and Puppet to automate the deployment, why shouldn't we automate the server and application hardening? We identified 3 phases to secure a server.

1.  Installation of operating system
2.  Installation and hardening of operating system and applications
3.  Continuous management and verification of security configuration

### Installation of OS

We recommend to install operating systems from trusted sources. This could be an operating system vendor or a trusted third party. If possible, we use vendor images. Since we use virtualize environments like OpenStack in our own infrastructure, the secure generation of operating systems is part of a secure infrastrucutre too. Therefore we automated the building of RedHat, Centos and Oracle Linux for those.

* [packer-rhel](https://github.com/TelekomLabs/packer-rhel)

### Hardening of OS and Applications

We provide multiple recipes in this area. We used best-known guides like [Deutsche Telekom (German)](http://www.telekom.com/static/-/155996/7/technische-sicherheitsanforderungen-si), [BetterCrypto](https://bettercrypto.org/) or [NSA](http://www.nsa.gov/ia/_files/os/redhat/NSA_RHEL_5_GUIDE_v4.2.pdf)

Chef Cookbooks

* [chef-os-hardening](https://github.com/TelekomLabs/chef-os-hardening)
* [chef-ssh-hardening](https://github.com/TelekomLabs/chef-ssh-hardening)
* [chef-mysql-hardening](https://github.com/TelekomLabs/chef-mysql-hardening)

Puppet Modules

* [puppet-os-hardening](https://github.com/TelekomLabs/puppet-os-hardening)
* [puppet-ssh-hardening](https://github.com/TelekomLabs/puppet-ssh-hardening)

### Continuous management

This area includes tasks like patch management, attack monitor systems and fixing of known vulnerabilities and exposures. Various solutions are available, but we will not cover issues within this area.

## Supported Operating Systems

✔ supported, ∅ not supported yet, ✘ will not be supported

| Operating System    | Supported     | Status |
| ------------- | ---------- | --------- |
| RedHat 6.5 | ✔ | full coverage |
| RedHat 7 | ∅ | not tested |  
| CentOS 6.5 | ✔ | full coverage | 
| Oracle Linux 6.5 | ✔ | full coverage | 
| Ubuntu 12.04 | ✔ | full coverage | 
| Ubuntu 14.04 | ✔ | full coverage |
| Debian 6 | ∅ | not fully tested, but should work | 
| Debian 7 | ∅ | not fully tested, but should work | 
| Suse Enterprise 11 SP3 | ∅ | not tested | 

## Blog 

We collect interesting findings in our blogs:

 * [Using Test Kitchen With Puppet](http://ehaselwanter.com/en/blog/2014/05/08/using-test-kitchen-with-puppet/)
 * [How to harden a new server with Chef](http://lollyrock.com/articles/how-to-harden-a-new-server/)

## Team

This project was initiated by Dominik Richter, Patrick Meier and Christoph Hartmann, a group of specialists, security researchers and cloud engineers. 

- Dominik Richter
- Patrick Meier
- Christoph Hartmann

These people have generously contributed (in alphabetical order)

- Edmund Haselwanter 
- Bernhard Weisshuhn

