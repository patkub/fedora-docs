---
title: Fix DNS Server
layout: default
---

# fix-dns-server

> change DNS server to use OpenDNS

Settings > Network > Select network connection to edit

IPv4 tab, add DNS servers `208.67.222.222` and `208.67.220.220`  
IPv6 tab, add DNS servers `2620:0:ccc::2` and `2620:0:ccd::2`

If you look at `/etc/resolv.conf`, you should only see the DNS addresses you added.
```sh
cat /etc/resolv.conf
```

For example,
```sh
nameserver 208.67.222.222
nameserver 208.67.220.220
```

Check if you are using OpenDNS at [https://welcome.opendns.com/](https://welcome.opendns.com/).

# References

* [OpenDNS Setup Guide](https://www.opendns.com/setupguide/)

