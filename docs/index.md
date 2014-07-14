# Automatic server hardening

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


### Continuous management

This area includes tasks like patch management, attack monitor systems and fixing of known vulnerabilities and exposures. Various solutions are available, but we will not cover issues within this area.
