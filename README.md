![stand with Ukraine](https://badgen.net/badge/support/UKRAINE/?color=0057B8&labelColor=FFD700)
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0)
[![ansible-lint](https://github.com/zerwes/ansible-role-win-acrylicdns/actions/workflows/lint.yml/badge.svg)](https://github.com/zerwes/ansible-role-win-acrylicdns/actions?query=workflow%3Aansible-lint)

# ansible-role-win-acrylicdns
ansible role to install and configure [acrylic dns](https://mayakron.altervista.org/support/acrylic/Home.htm) on windows.

[acrylic dns](https://mayakron.altervista.org/support/acrylic/Home.htm) can be used for a *split view* DNS setup with:

 + partially resolving some internal zomes via VPN
 * preventing DNS leakage of internal DNS names to the upstream public DNS
 * avoid slowdown of general DNS resolution of public resolvable DNS names (for example by routing **all** DNS queries via a VPN) by selectivly routing only the DNS traffic required via VPN etc.

## Role Variables

[defaults/main.yml](defaults/main.yml)

### Example
```yaml
acrylic_dns_proxy_servers:
  PrimaryServer:
    Address: 192.168.0.1  # DNS server reachable via VPN
    DomainNameAffinityMask: "*.my.internal.domain.tld;my.internal.domain.tld"  # domain(s) regex to resolve via VPN
  SecondaryServer:
    Address: 9.9.9.9
  TertiaryServer:
    Address: 1.1.1.1
```
