---
publish: true
title: IPv6
created: 2022-02-19T13:16:42
modified: 2026-08-05T07:58:56.686Z
---

# IPv6

# Privacy extensions

When a client acquires an address through SLAAC its IPv6 address is derived from the advertised prefix and the MAC address of the network interface of the client. This may raise security concerns as the MAC address of the computer can be easily derived by the IPv6 address. In order to tackle this problem the IPv6 Privacy Extensions standard (RFC 4941\[fn:1]) has been developed. With privacy extensions the kernel generates a temporary address that is mangled from the original autoconfigured address. Private addresses are preferred when connecting to a remote server so the original address is hidden. To enable Privacy Extensions reproduce add these lines to /etc/sysctl.d/40-ipv6.conf:

# Enable IPv6 Privacy Extensions

net.ipv6.conf.all.use\_tempaddr = 2
net.ipv6.conf.default.use\_tempaddr = 2
net.ipv6.conf.nic0.use\_tempaddr = 2
...
net.ipv6.conf.nicN.use\_tempaddr = 2

Where ~nic0~ to ~nicN~ are your Network Interface Cards. The ~all.use\_tempaddr~ or ~default.use\_tempaddr~ parameters are not applied to nic's that already exist when the sysctl settings are executed.

After a reboot, at the latest, Privacy Extensions should be enabled. NetworkManager should automatically enable ~ipv6.ip6-privacy~ by reading ~/proc/sys/net/ipv6/conf/default/use\_tempaddr~.

# Footnotes

\[fn:1] https://tools.ietf.org/html/rfc4941
