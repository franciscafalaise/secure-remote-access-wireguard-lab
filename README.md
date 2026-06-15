# Secure Remote Access VPN Lab

**WireGuard Site-to-Site Routing with GL.iNet Routers**

## Skills Demonstrated

WireGuard VPN • Dynamic DNS • NAT • Port Forwarding • Router Administration • Network Troubleshooting • Secure Remote Access • Firewall Configuration • Technical Documentation

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
  

## Screenshots and Validation
> **Note:** All sensitive information including public IP addresses, VPN keys, hostnames, and MAC addresses has been redacted from screenshots and configuration examples.

### Flint 2 WireGuard Server Configuration
Configured a GL.iNet Flint 2 router as the WireGuard VPN server. Multiple peer profiles were created and assigned dedicated VPN addresses within the WireGuard subnet. This configuration enables secure encrypted connectivity between remote routers and the home network.
<img width="1030" height="645" alt="wireguard-server-configuration" src="https://github.com/user-attachments/assets/b610a4cc-fc9f-48fa-9c22-52a240f161af" />


### Puli AX WireGuard Client Configuration
Generated and exported a dedicated WireGuard client configuration for the GL.iNet Puli AX travel router. Each peer received a unique VPN address and configuration profile, allowing secure encrypted communication with the WireGuard server hosted on the Flint 2 router.
<img width="427" height="421" alt="wireguard-client-profile-export" src="https://github.com/user-attachments/assets/b75fed5a-bbbc-4b7f-8d5e-30bb14da0b73" />


### Dynamic DNS Configuration

Configured Dynamic DNS (DDNS) on the Flint 2 router to maintain reliable remote connectivity despite changes to the ISP-assigned public IP address. This allows remote VPN clients to connect using a consistent hostname rather than relying on a static public IP.
<img width="752" height="499" alt="dynamic-dns-configuration" src="https://github.com/user-attachments/assets/ac72085f-4d69-4080-aedc-f7f6aadc54a9" />

## Port Forwarding Configuration

Configured port forwarding on the home network gateway to allow inbound WireGuard VPN traffic to reach the Flint 2 VPN server. Only the required UDP port was exposed, minimizing unnecessary public-facing services while enabling secure remote connectivity.
<img width="1011" height="558" alt="port-forwarding-wireguard" src="https://github.com/user-attachments/assets/e63e756e-af3d-40bc-ba1f-0cc877aa87e0" />

## Connectivity Validation

Validated external connectivity and public IP visibility after VPN deployment. Public IP and geolocation testing confirmed successful internet access and provided a method for verifying expected routing behavior during remote connectivity testing.
<img width="1233" height="504" alt="public-ip-validation" src="https://github.com/user-attachments/assets/718de1e3-0d46-4cf0-a420-89e0beb5d4c3" />

## Real-World Validation

The solution was tested from a remote location outside the United States using the GL.iNet Puli AX travel router.

Results:

- Successfully established a WireGuard tunnel to the home Flint 2 router.
- Remote traffic was routed through the home network.
- Public IP validation reflected the home network location rather than the remote location.
- Internet access remained functional through the encrypted tunnel.
- Dynamic DNS maintained connectivity despite public IP changes.
- The configuration successfully supported secure remote connectivity while appearing to originate from the home network.

This real-world test validated the overall design and demonstrated successful encrypted routing across geographically separated networks.

## Network Diagram

```text
Internet
    |
    ▼
Verizon Router
    |
UDP 51820
    |
    ▼
GL.iNet Flint 2
(WireGuard Server)
10.0.0.1
    |
══════════════════════
Encrypted Tunnel
══════════════════════
    |
10.0.0.3
GL.iNet Puli AX
(WireGuard Client)
    |
    ▼
Remote Devices
```
## Results

The project successfully created a secure remote access solution using router-based WireGuard VPN connectivity.

Key outcomes:

* Established encrypted remote connectivity between geographically separated networks.
* Successfully routed remote client traffic through the home network using a WireGuard tunnel and Dynamic DNS.
* Maintained reliable connectivity using Dynamic DNS
* Reduced public exposure of internal resources
* Improved hands-on understanding of VPNs, NAT, routing, and firewall behavior
* Gained experience validating network activity through security monitoring tools
* Successfully validated the solution during international travel, demonstrating reliable remote connectivity across geographically separated networks.

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
* Network Routing
* VPN Troubleshooting
* DNS Configuration
* WireGuard Administration
* Secure Remote Connectivity
* Traffic Validation

## Lessons Learned

This project reinforced the importance of secure remote access design, especially when supporting users outside of a traditional office network.

It also helped build a stronger understanding of how VPN tunnels, firewall rules, Dynamic DNS, routing tables, and public IP visibility work together in real-world environments.

## Future Improvements

Potential future enhancements include:

* Adding failover connectivity
* Implementing VLAN segmentation
* Adding log screenshots with sensitive information redacted
* Testing multiple client profiles
* Monitoring VPN traffic with a SIEM
* Documenting firewall rule changes more formally
* Implement full-tunnel and split-tunnel configurations
* Deploy redundant VPN endpoints
* Add centralized logging and alerting
* Integrate SIEM monitoring for VPN activity
* Implement MFA-protected remote access

## Project Status

Completed initial deployment and validation. Future improvements will focus on monitoring, documentation, and advanced network segmentation.
