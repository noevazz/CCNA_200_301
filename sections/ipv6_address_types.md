# IPv6 Address Types

Important notes:
- Broadcast addresses do not exist in IPv6.
- All-0s and all-1s host addresses can be assigned since broadcast addresses do not exist.
    - All-0s should be used only in routers as a subnet-router anycast address.

## Unicast
- **Global unicast address (GUA)**: These IPv6 addresses are similar to public IPv4 addresses in the sense that are routable in the Internet and are used to identify a specific host.
    - Range: `2000::/3`
- **Link-Local address**: Used for communication on the same link (subnet) and ONLY in that link. These addresses are not routable beyond the link.
    - Example: Use link-local address to communicate two routers.
    - Range: `FE80::/10`
- **Unique Local addresses (ULA)**: These addresses are similar to the IPv4 private addresses (RFC 1918).
    - Range: `FC00::/7 to FDFF::/7`
- **Loopback**: `::1/128`
- **Unspecified address**: correspond to 0.0.0.0 in IPv4.
    - Range: `::/128`
    - Read more [here](http://www.ipuptime.net/Unspecified.aspx)

## Multicast
- Range: `FF00::/8`
- There are 2 types of IPv6 multicast addresses:
    - Assigned multicast: 
    - Solicited node multicast: 

## Anycast
 An IPv6 anycast address is any IPv6 unicast address that can be assigned to multiple devices. A packet sent to an anycast address is routed to the nearest device having that address. Anycast addresses are beyond the scope of this course.


 ## More info
 - https://www.ripe.net/manage-ips-and-asns/ipv6/ipv6-address-types/ipv6-address-types