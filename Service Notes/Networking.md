## 1. What is Networking?

Networking is the connection of computers/devices to share data.

Uses IP addresses, protocols, and network devices to communicate.

## 2. Key Networking Terms
## IP Address

A unique number identifying a device on a network.

## Two types:

IPv4: 192.168.1.1

IPv6: long format for more addresses

# Public IP

Accessible over the internet.

# Private IP

Used inside a private network (LAN).

## 3. MAC Address

Physical hardware address of a network card.

Unique for every device.

## 4. Subnet

A smaller network inside a larger network.

Helps organize and secure networks.

Uses subnet mask (e.g., 255.255.255.0) to divide IP ranges.

## 5. DNS (Domain Name System)

Converts names → IP addresses
Example: google.com → 142.250.72.14

Like a "phonebook" for the internet.

## 6. DHCP (Dynamic Host Configuration Protocol)

## Automatically assigns:

IP address

Subnet mask

Gateway

DNS

Removes need to configure IPs manually.

## 7. Router

Forwards traffic between networks.

Connects local network → internet.

## 8. Switch

Connects devices inside a LAN.

Sends data only where it needs to go (smart).

## 9. Firewall

Controls incoming & outgoing traffic.

Protects the network.

Can allow or block ports.

## 10. Ports

Virtual doors used by services.

Common ports:

80 → HTTP

443 → HTTPS

22 → SSH

25 → SMTP

3306 → MySQL

## 11. Protocols

Protocols = set of rules devices follow.

## Common protocols

HTTP/HTTPS – web communication

FTP – file transfer

SSH – secure remote access

TCP – reliable, connection-based

UDP – fast, no confirmation

ICMP – used for ping/diagnostics

## 12. NAT (Network Address Translation)

Translates private IP → public IP.

Allows many devices to share one public IP.

## 13. VPN (Virtual Private Network)

Secure encrypted tunnel over the internet.

Used for remote access to private networks.

## 14. Load Balancer

Distributes traffic across multiple servers.

Improves performance & availability.

## 15. Basic Troubleshooting Commands

ping – test connectivity

traceroute / tracert – see path taken

ip addr / ifconfig – show IP

nslookup domain – DNS lookup

curl – test URL response

netstat -tulnp – see open ports
