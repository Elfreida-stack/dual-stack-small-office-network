# Dual-Stack Small Office Network

## Project Overview

This project demonstrates the implementation of a small office network using Dual Stack networking. Both IPv4 and IPv6 were configured on the network devices, allowing the PCs to communicate using either IP protocol.

The network was built and tested using Cisco Packet Tracer.

## Objectives

- Configure IPv4 addressing on a small office network.
- Configure IPv6 addressing on the same network.
- Implement Dual Stack networking.
- Configure a Cisco router as the network gateway.
- Enable IPv6 routing on the router.
- Configure default gateways for IPv4 and IPv6.
- Test connectivity using IPv4 and IPv6.
- Verify successful communication between network devices.

## Network Topology

The network consists of:

- 1 Cisco 1941 Router
- 1 Cisco 2960 Switch
- 2 PCs
- Ethernet connections

Topology:

PC0 ── Switch0 ── Router0
PC1 ── Switch0

Both PCs connect to the switch, while the switch connects to the router through GigabitEthernet0/0.

## IP Addressing Plan

| Device | IPv4 Address | IPv4 Subnet Mask | IPv4 Gateway | IPv6 Address | Prefix Length | IPv6 Gateway |
|---|---|---|---|---|---|---|
| Router0 G0/0 | 192.168.10.1 | 255.255.255.0 | N/A | 2001:db8:10::1 | /64 | N/A |
| PC0 | 192.168.10.10 | 255.255.255.0 | 192.168.10.1 | 2001:db8:10::10 | /64 | 2001:db8:10::1 |
| PC1 | 192.168.10.20 | 255.255.255.0 | 192.168.10.1 | 2001:db8:10::20 | /64 | 2001:db8:10::1 |

## IPv4 Configuration

The router's GigabitEthernet0/0 interface was configured with:

- IPv4 address: 192.168.10.1
- Subnet mask: 255.255.255.0

PC0 and PC1 were configured in the 192.168.10.0/24 network.

PC0:

- IPv4 address: 192.168.10.10
- Subnet mask: 255.255.255.0
- Default gateway: 192.168.10.1

PC1:

- IPv4 address: 192.168.10.20
- Subnet mask: 255.255.255.0
- Default gateway: 192.168.10.1

## IPv6 Configuration

The router's GigabitEthernet0/0 interface was configured with:

- IPv6 address: 2001:db8:10::1/64

IPv6 routing was enabled on the router using:

    ipv6 unicast-routing

PC0 was configured with:

- IPv6 address: 2001:db8:10::10/64
- Default gateway: 2001:db8:10::1

PC1 was configured with:

- IPv6 address: 2001:db8:10::20/64
- Default gateway: 2001:db8:10::1

## Connectivity Testing

Connectivity was tested using the ping command.

### IPv4 Tests

PC0 successfully pinged PC1 using:

    ping 192.168.10.20

Result:

- 0% packet loss

PC1 successfully pinged PC0 using:

    ping 192.168.10.10

Result:

- 0% packet loss

PC0 also successfully pinged the router's IPv4 address:

    ping 192.168.10.1

Result:

- 0% packet loss

### IPv6 Tests

PC0 successfully pinged PC1 using:

    ping 2001:db8:10::20

Result:

- 0% packet loss

PC1 successfully pinged PC0 using:

    ping 2001:db8:10::10

Result:

- 0% packet loss

PC0 also successfully pinged the router's IPv6 address:

    ping 2001:db8:10::1

Result:

- 0% packet loss

## Results

The network successfully demonstrated Dual Stack communication.

Both PCs were configured with IPv4 and IPv6 addresses and were able to communicate successfully using both protocols.

All connectivity tests completed with 0% packet loss.

## Skills Demonstrated

- IPv4 addressing
- IPv6 addressing
- IPv4 subnet masks
- IPv6 /64 prefixes
- Default gateways
- Cisco router interface configuration
- IPv6 routing
- Dual Stack networking
- Basic network connectivity testing
- Packet Tracer network simulation
- Network troubleshooting and verification

## Tools Used

- Cisco Packet Tracer
- Cisco 1941 Router
- Cisco 2960 Switch
- Windows-based PC simulation

## Project Evidence

The `Screenshots` folder contains screenshots showing:

- Network topology
- Router IPv4 and IPv6 configuration
- Successful IPv4 and IPv6 connectivity tests
- PC0 addressing configuration
- PC1 addressing configuration

## Conclusion

This project demonstrates how IPv4 and IPv6 can operate simultaneously on the same network using Dual Stack. The router, switch, and PCs were configured with appropriate IPv4 and IPv6 addresses, gateways, and routing settings. Connectivity was successfully verified using ping tests over both protocols.