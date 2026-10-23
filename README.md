# UniFi IoT Isolation Guide

A practical, tested guide to isolating smart TVs and IoT devices using UniFi VLANs, Zone-Based Firewall rules, DNS Content Filtering, and IPv4/IPv6 verification.

## Download the Guide

**[Download the UniFi IoT Isolation Guide (PDF)](UniFi_IoT_Isolation_Guide.pdf)**

## Tested Configuration

- **Gateway:** UniFi Dream Machine SE (UDM-SE)
- **UniFi OS:** 6.0.15
- **UniFi Network:** 11.0.94
- **Device:** LG Smart TV
- **Test client:** Linux laptop
- **Network:** Dual-stack IPv4/IPv6

## What This Guide Covers

- Creating a dedicated VLAN and Wi-Fi SSID
- Isolating untrusted devices using UniFi's Zone-Based Firewall
- Applying DNS Content Filtering to an entire VLAN
- Testing DNS filtering over both IPv4 and IPv6
- Verifying network isolation
- Configuring the gateway's mDNS proxy
- Considerations for Plex, Emby, NAS and other IoT devices

## Important IPv6 Discovery

During testing, I discovered that UniFi's DNS Content Filtering worked over IPv4 but could be bypassed by sending DNS queries to the gateway's IPv6 address.

The problem was reproduced with UniFi Network 10.x and 11.0.94 on earlier UniFi OS versions.

Upgrading to **UniFi OS 6.0.15** resolved the issue in my configuration.

**Always test both IPv4 and IPv6.**

## The Naming Convention

Because network security doesn't have to be boring:

- **Hobble Skirt** — VLAN 107, restricting where the television can wander.
- **Ball Gag** — DNS Content Filtering, stopping unwanted communications.
- **Armbinder** — Dedicated firewall zone, preventing access to the trusted LAN.

## Disclaimer

This guide documents my own configuration and testing. It is not an official Ubiquiti publication.

Different UniFi versions, network architectures and IoT devices may require adjustments.

Always verify firewall behaviour and connectivity in your own environment.

## Contributions

Suggestions, corrections and improvements are welcome through GitHub Issues.

If you find something that could be improved, please let me know!

## Licence

Creative Commons Attribution 4.0 International (CC BY 4.0).
