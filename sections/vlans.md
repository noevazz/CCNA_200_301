# Virtual Local Area Networks (VLANs)

## What is a VLAN?

VLANs are **logical** grouping of devices in the **same broadcast domain**.

This means VLANs group devices using software (that's what logical means).

## Characteristics

- VLANs are usually configured on switches.
- VLANs can spread across multiple switches. That means broadcasts to a VLAN will be sent to all hosts even if they are not connected to the same switches, hosts only need to be in the same VLAN.

## Why VLANs are used?

- Increase number of broadcast domain. This reduce the amount of traffic since broadcasts are sent to fewer devices.
- Isolate hosts that hold sensitive data.
- Reduce security risks by reducing the number of hosts that receive copies of frames that the switches flood.
- Use VLAN to separate devices logically rather than physical location.
- Reduction of costs, we can reduce the costs that would be needed if each department in an organization needed a physical switch. With a 24 port switch, and 20 users in different departments, we can implement VLANs to separate them without needing additional hardware.
- Administrative tasks improvement, the use of VLANs eases the work IT administrators have to perform to maintain the network. With VLANs, upgrading of the network, troubleshooting and other tasks are made easier.

## Network without VLANS vs network with VLANs

## Default VLAN

By default all ports belong to VLAN 1.

## Trunks

A trunk is a point-to-point link between two switches. This link allows traffic from many VLANs to move between the switches.

When configuring trunk ports it is important to know these other concepts:

- **Native VLAN**: This is the port that the switch uses to send untagged traffic. Tagged traffic is all traffic destined to a particular VLAN. Untagged traffic may be any traffic which is not destined to any particular VLAN such as control information.
- **Dynamic trunk protocol**: DTP is a CISCO proprietary protocol that negotiates the trunking modes between switches.



## Port security



## External resources

1. [En] https://study-ccna.com/what-is-a-vlan/
2. [En] https://www.ccnablog.com/vlans-part-i/
