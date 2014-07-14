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

This area includes tasks like patch management, attack monitoring, and fixing known vulnerabilities. None of these areas are covered in this hardening project.

#### Patch management

It is the heart of keeping your systems secure once everything is in place. So why not patch automatically on every run? We have considered this option for our hardening components but ultimately decided against it: Patches generally aren't a trivial thing to do. Even if you reduce it to security updates only, there may still be regressions which have to be weighted against benefits. Set up a patch management system of your choice.

#### Attack monitoring

Hardening includes a small section of compliance monitoring. Every time an attacker changes a core system configuration, you can gain insights into this through hardening. Since all of our components are tested independently, you can potentially use these tests to validate the compliance of your configuration. However, we recommend against putting too much weight on the results you get. The tests created here are written to verify hardening instructions. Attackers may still find ways to modify files in a way that gets around these checks (example: if we check `main.cfg` only, but attacker writes to `main.cfg.d/my.cfg`). Use HIDS, auditing, and monitoring systems to manage these risks.

#### Vulnerability fixes

A remainder of vulnerabilities may still remain after successful patch management. There are vulnerabilities that need mitigation before proper vendor fixes are released. We won't cover such vulnerabilities in this project. Many settings, however, are meant to reduce the attack surface and thus directly contribute to reducing the risks from unpatched vulnerabilities.