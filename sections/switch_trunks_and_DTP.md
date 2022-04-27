# Trunk links and DTP

## What is a trunk

A trunk is a point-to-point link between two switches. This link allows traffic from many VLANs to move between the switches.

When configuring trunk ports it is important to know these other concepts:

- **Native VLAN**: This is the port that the switch uses to send untagged traffic. Tagged traffic is all traffic destined to a particular VLAN. Untagged traffic may be any traffic which is not destined to any particular VLAN such as control information.
- **Dynamic trunk protocol**: DTP is a CISCO proprietary protocol that negotiates the trunking modes between switches.

## Switchport modes

A switch port can be in one of two modes: access and trunk.

There are two ways a switch port can settle down into one of these two modes:

- **Static**: You manually configure a switch port to be in the access or trunk mode in the static method.
- **Dynamic**: You can let Dynamic Trunking Protocol (DTP) run on an interface to negotiate trunking in the dynamic method.

## DTP

Cisco switches exchange DTP messages to dynamically learn whether the device at the other end of the link wants to perform trunking and, if so, which trunking protocol (**ISL or 802.1Q**) to use.

These are the available options when configuring switchport mode:

```
Switch(config)#int f0/1
Switch(config-if)#switchport mode ?
  access   Set trunking mode to ACCESS unconditionally
  dynamic  Set trunking mode to dynamically negotiate access or trunk mode
  trunk    Set trunking mode to TRUNK unconditionally
Switch(config-if)#
```

**dynamic** has a 2 configurations:

```
Switch(config-if)#switchport mode dynamic ?
  auto       Set trunking mode dynamic negotiation parameter to AUTO
  desirable  Set trunking mode dynamic negotiation parameter to DESIRABLE
```

Below you can see the default configuration of a FastEthernet port:

```
Switch#show interfaces FastEthernet 0/5 switchport 
Name: Fa0/5
Switchport: Enabled
Administrative Mode: dynamic auto   <--- ATTENTION TO THIS
Operational Mode: down
Administrative Trunking Encapsulation: dot1q
Operational Trunking Encapsulation: native
Negotiation of Trunking: On
Access Mode VLAN: 1 (default)
Trunking Native Mode VLAN: 1 (default)
Voice VLAN: none
Administrative private-vlan host-association: none
Administrative private-vlan mapping: none
Administrative private-vlan trunk native VLAN: none
Administrative private-vlan trunk encapsulation: dot1q
Administrative private-vlan trunk normal VLANs: none
Administrative private-vlan trunk private VLANs: none
Operational private-vlan: none
Trunking VLANs Enabled: All
Pruning VLANs Enabled: 2-1001
Capture Mode Disabled
Capture VLANs Allowed: ALL
Protected: false
Unknown unicast blocked: disabled
Unknown multicast blocked: disabled
Appliance trust: none

Switch#
```

> Switch ports are configured in `dynamic auto` mode by default **in Switches Cisco Catalyst 2960**.

These are the possible options and resulting mode when configuring the switchport mode in 2 connected switches:

|                 |Dynamic Auto|Dynamic Desirable|Trunk               |Access              |
|-----------------|------------|-----------------|--------------------|--------------------|
|Dynamic Auto     |Access      |Trunk            |Trunk               |Access              |
|Dynamic Desirable|Trunk       |Trunk            |Trunk               |Access              |
|Trunk            |Trunk       |Trunk            |Trunk               |Limited Connectivity|
|Access           |Access      |Access           |Limited Connectivity|Access              |

## External resources

1. [En] [https://www.freeccnastudyguide.com/study-guides/ccna/ch7/7-3-types-switch-ports/](https://www.freeccnastudyguide.com/study-guides/ccna/ch7/7-3-types-switch-ports/)