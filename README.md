# Dynamic Host Configuration Protocol (DHCP) Simulation

This repository contains a simplified UDP-based simulation of the Dynamic Host Configuration Protocol (DHCP). 
It demonstrates the core lifecycle of network IP assignment, including discovery, offering, request, acknowledgment (DORA), renewal, and release.

## Overview
The project consists of a server-client architecture that mimics how devices on a local network interact with a DHCP server to obtain and maintain an IP address.
- ```server.py``` : Manages a pool of available IP addresses, handles incoming requests, tracks lease expiration times, and runs a background thread to reclaim expired IPs.
- ```client.py``` : Simulates a network device. It broadcasts a discovery message, requests an IP from the server, performs periodic renewals to keep the lease active, and finally releases the IP upon exit.

## Features
- Full DHCP Lifecycle: Implements DISCOVER, OFFER, REQUEST, ACK, RENEW, and RELEASE sequences.
- Dynamic IP Management: The server manages a pool of addresses (192.168.1.10 to 192.168.1.20).
- Automatic Lease Expiry: A background "cleaner" thread on the server monitors and expires leases in real-time.
- Renewal Logic: The client is programmed to renew its lease at the half-way point of the lease duration.
- Release: Ensuring the IP returns to the pool when the client shuts down.

## Technical Specifications
- Language - Python
- Protcol - UDP (User Datagram Protocol)

## Copyright
Copyright (c) 2026 Meghna Ravikumar. All rights reserved. No part of this software may be reproduced or distributed without permission.
