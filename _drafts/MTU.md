---
layout: post
title: MTU - definition matters
tags: router switch cisco HP H3C juniper linux
---

# MTU - definition matters #

MTU - Maximum Transmission Unit. What does it mean for network equipment vendors?

MTU
PDU

SDU

[PDU](https://en.wikipedia.org/wiki/Protocol_data_unit)
[SDU](https://en.wikipedia.org/wiki/Maximum_transmission_unit)

![MTU image](MTU.svg "MTU image")

[Juniper MTU](http://weblogs.com.pk/jahil/archive/2009/05/05/configuring-the-juniper-media-ip-mpls-mtu.aspx)
[Juniper vs. Cisco MTU](http://www.net-gyver.com/?p=1086)


| vendor    | MAC SDU 1500B | MAC SDU 9000B |
| --------- | ------------- | ------------- |
| Cisco     | asdf          | 23677         |
| HP/H3C    | asdfasdf      | 34545767      |
| Juniper   |               |               |
| Linux     |               |               |

## Ping implementation

Checking connectivity between hosts is usualy done using ping utility, but 

Ping size specification differs on for 
