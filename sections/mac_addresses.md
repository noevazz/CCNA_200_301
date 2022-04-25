# MAC Addresses

MAC (Media Access Control) addresses are primarily assigned by device manufacturers, and are therefore referred to as the `burned-in address`, or as an Ethernet hardware address, hardware address and physical address.

Each MAC address can be stored in hardware, such as the card's read-only memory, or by a firmware mechanism.

> You can chance MAC addresses, but generally you don't have to.

## Representation

MAC addresses are `48 bits` long and is represented as a string of `12 hexadecimal digits`.

These are example of common representations across multiple systems/vendors:

```
00-0a-83-b1-c0-83
00:0a:83:b1:c0:83
000.a83.b1.c083
```

## How to find MAC addresses

- Command for UNIX/Linux
```
ifconfig -a
ip link list 
ip address show
```

- Command for Windows OS
```
ipconfig /all 
```

- MacOS

TCP/IP Control Panel

## OUI

The first 24 bits (3 octets) are called `Organizationally Unique Identifier (OUI)`.

The IEEE assigns these first 24 bits to its registered vendors.
You can see a list of OUIs and the organization that use it here: https://standards-oui.ieee.org/oui/oui.txt

## Network Interface Controller (NIC) Specific

The last 24 bits is used by vendors to uniquely identify each device.