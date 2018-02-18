---
title: Fix broken package groups
layout: default
---

# Fix broken package groups

> fix broken package groups from a live desktop

After installing and removing XFCE desktop enviornment, WiFi was gone. Parts of the system were lost and networking failed to start up. The WiFi tab in Gnome was missing. Reinstalling Fedora packages from a Live USB fixed the problem.

Boot from a LiveCD/USB desktop, mount the system root directory, and reinstall the `Fedora Workstation` package group.

```sh
dnf --installroot /run/media/users/1000/uuid-ugly-abra-cada-bra0 groups install "Fedora Workstation"
```

# References

* [https://ask.fedoraproject.org/en/question/70353/network-manager-and-internet-not-working-after-yum-autoremove/?answer=70409#post-id-70409](https://ask.fedoraproject.org/en/question/70353/network-manager-and-internet-not-working-after-yum-autoremove/?answer=70409#post-id-70409)
