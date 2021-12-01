---
layout: post
title: Oracle Linux 7 in OCI - do not modify /etc/resolv.conf
tags: OCI Oracle linux OL7
disqus_id: OCI-OL7-resolv
comments: false
---


If you want to preserve `/etc/resolv.conf` configuration, following steps must be taken:

0. include `PEERDNS=no` in your `/etc/sysconfig/network-scripts/ifcfg-<your_interface>`
0. because initram rewrites `ifcfg-*` files every time system reboots (and we would loose our `PEERDNS=no` modification), initramfs must be modified to exclude ifcfg modules. Execute `dracut -f -o ifcfg`
0. every new kernel image modifies initram, therefore it is necessary to force dracut not to modify it even new kernel is installed. Place `90-dracut.conf` file to `/etc/dracut.conf.d`
```
omit_dracutmodules+="ifcfg"
```

Now you can modify your `/etc/resolv.conf` and test the changes by rebooting/restarting network.

