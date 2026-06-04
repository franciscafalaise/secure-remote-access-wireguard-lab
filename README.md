# Secure Remote Access VPN Lab

**WireGuard Site-to-Site Routing with GL.iNet Routers**

## Project Overview

This project demonstrates the design and implementation of a secure remote access network using WireGuard VPN, port forwarding, Dynamic DNS, and router-based traffic routing.

The goal was to create an encrypted tunnel between a travel router and a home network router, allowing remote devices to securely route traffic through a trusted home network while maintaining access to internal resources.

## Business Use Case

Remote users often need secure access to trusted networks, internal resources, and consistent network routing without directly exposing devices to the public internet.

This project simulates a secure remote access solution similar to what may be used by small businesses, remote workers, IT support teams, and home lab environments.

## Technologies Used

* WireGuard VPN
* GL.iNet Flint 2 Router
* GL.iNet Puli AX Travel Router
* Dynamic DNS
* Port Forwarding
* NAT
* Firewall Rules
* Private IP Addressing
* Remote Network Troubleshooting

## Network Design

The solution uses a home router as the WireGuard VPN server and a secondary router as the WireGuard client.

Remote devices connect to the client router, which establishes an encrypted tunnel back to the home network. Traffic is then routed securely through the VPN tunnel.

## Key Objectives

* Configure a WireGuard VPN server on the home network
* Configure a WireGuard VPN client on a secondary router
* Use Dynamic DNS to support changing public IP addresses
* Forward the required VPN port through the home router
* Route client traffic through the encrypted tunnel
* Validate external connectivity and public IP routing
* Reduce exposure of internal devices to the public internet

## Implementation Steps

### 1. Home Router Configuration

Configured the GL.iNet Flint 2 router as the primary WireGuard server.

Tasks completed:

* Enabled WireGuard server functionality
* Generated server and client key pairs
* Defined VPN subnet addressing
* Configured allowed IP ranges
* Enabled traffic forwarding through the tunnel

### 2. Dynamic DNS Setup

Configured Dynamic DNS to maintain reliable connectivity even if the ISP-assigned public IP address changes.

This allowed the remote router to connect using a consistent hostname instead of relying on a static public IP address.

### 3. Port Forwarding

Configured port forwarding on the home network to allow WireGuard traffic to reach the VPN server.

Only the required WireGuard UDP port was exposed, reducing unnecessary public-facing services.

### 4. Travel Router Configuration

Configured the GL.iNet Puli AX router as the WireGuard client.

Tasks completed:

* Imported the WireGuard client configuration
* Verified peer connection to the home VPN server
* Enabled routing for connected client devices
* Tested connectivity through the VPN tunnel

### 5. Testing and Validation

Performed testing to confirm that traffic was successfully routed through the VPN tunnel.

Validation included:

* Confirming WireGuard tunnel status
* Testing public IP routing
* Verifying DNS resolution
* Testing internet connectivity
* Confirming remote access stability
* Reviewing security monitoring logs for expected connection behavior

## Security Considerations

Security was a major focus of this project.

Controls included:

* Encrypted VPN tunnel using WireGuard
* Limited port exposure
* No direct exposure of internal endpoints
* Router-based VPN authentication
* Private IP addressing
* Firewall rule review
* Network segmentation awareness
* Remote access validation through monitoring logs

## Results

The project successfully created a secure remote access solution using router-based WireGuard VPN connectivity.

Key outcomes:

* Established encrypted remote connectivity
* Routed client traffic through a trusted home network
* Maintained reliable connectivity using Dynamic DNS
* Reduced public exposure of internal resources
* Improved hands-on understanding of VPNs, NAT, routing, and firewall behavior
* Gained experience validating network activity through security monitoring tools

## Skills Demonstrated

* Network Administration
* VPN Configuration
* WireGuard Deployment
* Router Administration
* Firewall Configuration
* Port Forwarding
* Dynamic DNS
* NAT Troubleshooting
* Remote Access Security
* Security Monitoring
* Technical Documentation

## Lessons Learned

This project reinforced the importance of secure remote access design, especially when supporting users outside of a traditional office network.

It also helped build a stronger understanding of how VPN tunnels, firewall rules, Dynamic DNS, routing tables, and public IP visibility work together in real-world environments.

## Future Improvements

Potential future enhancements include:

* Adding failover connectivity
* Implementing VLAN segmentation
* Creating network diagrams
* Adding log screenshots with sensitive information redacted
* Testing multiple client profiles
* Monitoring VPN traffic with a SIEM
* Documenting firewall rule changes more formally

## Project Status

Completed initial deployment and validation. Future improvements will focus on monitoring, documentation, and advanced network segmentation.
