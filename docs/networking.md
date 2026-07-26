# Basic Linux Commands

> **Operating System:** Kali Linux 2026.x  
> **Shell:** Bash  
> **Author:** Ridwan  
> **Purpose:** Practical documentation of basic Linux commands with screenshots and explanations.

This document contains the basic Linux commands executed during this lab.

# Networking Commands

## Introduction

Networking commands allow Linux users to test network connectivity, communicate with remote systems, and transfer files across a network. These commands are commonly used by Linux administrators, network engineers, and cybersecurity professionals.

---

## Table of Contents

- Lab 01 – Testing Network Connectivity
- Lab 02 – Connecting to a Remote System
- Lab 03 – File Transfer Commands

---

# Lab 01 – Testing Network Connectivity

## Objective

Learn how to test network connectivity and verify that a remote host is reachable using the `ping` command.

---

### Command 1: `ping google.com`

#### Description

The `ping` command sends ICMP Echo Request packets to a remote host to determine whether it is reachable and to measure response time.

#### Syntax

```bash
ping google.com
```

#### Expected Output

Displays continuous replies similar to:

```text
64 bytes from ...
icmp_seq=1 ttl=...
time=...
```

> **Note:** Press **Ctrl + C** to stop the command.

---

### Command 2: `ping 8.8.8.8`

#### Description

Tests connectivity directly to Google's public DNS server using its IP address.

#### Syntax

```bash
ping 8.8.8.8
```

#### Expected Output

Displays successful replies if the internet connection is working correctly.

---

## Commands Executed

```bash
ping google.com
ping 8.8.8.8
```

---

## Screenshot

```
screenshots/networking/lab-01-ping-command.png
```

---

## Skills Gained

After completing this lab, I can:

- Test network connectivity.
- Ping a hostname.
- Ping an IP address.
- Read packet loss and response times.

---

## Conclusion

This lab introduced the `ping` command, which is one of the most important networking tools for verifying connectivity and troubleshooting network issues.


---


# Lab 01 – Viewing Network Interface Information

## Objective

Learn how to display network interfaces, IP addresses, MAC addresses, and interface status using the `ip` command.

---

### Command 1: `ip a`

#### Description

The `ip a` command displays detailed information about every network interface on the system.

It shows:

- Interface name
- Interface state
- MAC address
- IPv4 address
- IPv6 address
- Broadcast address

---

#### Syntax

```bash
ip a
```

---

#### Breaking Down the Command

| Part | Meaning |
|------|---------|
| `ip` | Linux networking utility used to manage network interfaces, routing, and addresses. |
| `a` | Short for **address**. Displays all IP addresses assigned to every network interface. |

The command can also be written as:

```bash
ip address
```

Both commands perform exactly the same function.

---

#### Example Output

```text
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536
    inet 127.0.0.1/8

2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500
    link/ether 08:00:27:8d:2e:6b
    inet 192.168.1.20/24
    inet6 fe80::a00:27ff:fe8d:2e6b/64
```

---

#### Understanding the Output

##### `lo`

The **loopback interface**.

Linux uses this interface to communicate with itself.

Default address:

```text
127.0.0.1
```

---

##### `eth0`

The primary Ethernet network interface.

Depending on your Linux version, it could also appear as:

- eth0
- ens33
- enp0s3
- wlan0 (Wireless)

---

##### `UP`

Means the interface is enabled.

If it says:

```text
DOWN
```

The interface is disabled.

---

##### `LOWER_UP`

Indicates that the physical connection is active.

For example:

- Ethernet cable connected
- Wi-Fi connected

---

##### `mtu 1500`

Maximum Transmission Unit.

This is the largest packet size the interface can send.

Standard Ethernet MTU:

```text
1500 bytes
```

---

##### `link/ether`

Displays the MAC Address.

Example:

```text
08:00:27:8d:2e:6b
```

Every network card has its own unique MAC address.

---

##### `inet`

Displays the IPv4 Address.

Example:

```text
192.168.1.20/24
```

Where:

- 192.168.1.20 = IP Address
- /24 = Subnet Mask (255.255.255.0)

---

##### `inet6`

Displays the IPv6 Address.

Example:

```text
fe80::a00:27ff:fe8d:2e6b/64
```

---

## Commands Executed

```bash
ip a
```

---

## Screenshot

```
screenshots/networking/lab-01-ip-address.png
```

---

## Skills Gained

After completing this lab, I can:

- Display all network interfaces.
- Identify my IPv4 address.
- Identify my IPv6 address.
- Identify my MAC address.
- Determine whether an interface is active.
- Interpret the output of the `ip a` command.

---

## Conclusion

This lab introduced the `ip a` command, one of the most important networking commands in Linux. I learned how to identify network interfaces, interpret IP addressing information, recognize MAC addresses, and understand interface status.


---

# Lab 03 – Viewing Network Interface Status

## Objective

Learn how to display network interfaces, identify their status, and retrieve the system hostname and assigned IP address.

---

## What is this command?

The `ip link` command displays information about every network interface installed on the Linux system.

Unlike `ip a`, which focuses on IP addresses, `ip link` focuses on the physical and logical state of network interfaces.

---

## Why is this command used?

System administrators use `ip link` to:

- View available network interfaces.
- Check whether an interface is UP or DOWN.
- View MAC addresses.
- Troubleshoot network connectivity issues.

---

### Command 1: `ip link`

#### Syntax

```bash
ip link
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `ip` | Linux networking utility. |
| `link` | Displays information about network interfaces (links). |

---

#### Example Output

```text
1: lo: <LOOPBACK,UP,LOWER_UP>
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP>
```

---

## Understanding the Output

### `lo`

The Loopback Interface.

Used by Linux to communicate with itself.

---

### `eth0`

The primary Ethernet interface.

Depending on your distribution, you may instead see:

- ens33
- enp0s3
- eno1
- wlan0

---

### `UP`

The interface is enabled.

---

### `DOWN`

The interface is disabled.

---

### `LOWER_UP`

Indicates that the physical connection is active.

For example:

- Ethernet cable connected.
- Wi-Fi connected.

---

### Real-world Use Case

If your internet suddenly stops working, `ip link` quickly tells you whether your network interface is active.

---

### Command 2: `hostname`

## What is this command?

The `hostname` command displays the name of the current Linux machine.

---

#### Syntax

```bash
hostname
```

---

#### Expected Output

```text
cypher
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `hostname` | Displays the computer's hostname. |

---

### Real-world Use Case

When managing multiple Linux servers, every machine has its own hostname to help identify it on the network.

---

### Command 3: `hostname -I`

## What is this command?

Displays the IP addresses currently assigned to the computer.

---

#### Syntax

```bash
hostname -I
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `hostname` | Displays hostname information. |
| `-I` | Shows all assigned IP addresses. |

---

#### Example Output

```text
192.168.1.120
```

---

## Understanding the Output

The displayed address is your computer's IPv4 address on the local network.

If multiple interfaces are active, more than one IP address may be displayed.

---

### Real-world Use Case

Before connecting to another computer using SSH, you first need to know its IP address. One of the quickest ways to find it is:

```bash
hostname -I
```

---

## Commands Executed

```bash
ip link
hostname
hostname -I
```

---

## Screenshot

```
screenshots/networking/lab-02-network-interface-status.png
```

---

## Skills Gained

After completing this lab, I can:

- View available network interfaces.
- Determine whether an interface is active.
- Identify my computer's hostname.
- Display my local IP address.
- Interpret basic network interface information.

---

## Conclusion

This lab introduced commands used to identify a Linux system on a network. I learned how to inspect network interfaces, determine their operational state, retrieve the system hostname, and display the assigned IP address.


---

# Lab 04 – Testing Network Connectivity

## Objective

Learn how to verify network connectivity, trace the path packets take across a network, and understand the information returned by network diagnostic tools.

---

## What is Network Connectivity Testing?

Network connectivity testing is the process of determining whether one computer can successfully communicate with another over a network.

Linux provides several tools to troubleshoot connectivity problems, including:

- `ping`
- `traceroute`
- `tracepath`

These tools are essential for system administrators, network engineers, and cybersecurity professionals.

---

# Command 1: `ping`

## What is the `ping` command?

The `ping` command tests communication between your computer and another device by sending **ICMP (Internet Control Message Protocol) Echo Request** packets.

If the destination is reachable, it responds with an **ICMP Echo Reply**.

---

## Why is it used?

The `ping` command helps you:

- Verify network connectivity.
- Determine whether a host is online.
- Measure network latency.
- Detect packet loss.
- Troubleshoot network problems.

---

## Syntax

```bash
ping hostname
```

Example

```bash
ping google.com
```

or

```bash
ping 8.8.8.8
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `ping` | Sends ICMP Echo Request packets. |
| `google.com` | The destination hostname. |

---

## Example Output

```text
PING google.com (142.250.190.14) 56(84) bytes of data.

64 bytes from 142.250.190.14:
icmp_seq=1 ttl=118 time=19.4 ms

64 bytes from 142.250.190.14:
icmp_seq=2 ttl=118 time=20.1 ms
```

---

## Understanding the Output

### 64 bytes

The size of the packet received.

---

### icmp_seq

The packet sequence number.

Every new packet increases the sequence.

Example:

```
icmp_seq=1
icmp_seq=2
icmp_seq=3
```

---

### ttl

Time To Live.

TTL prevents packets from circulating forever.

Each router decreases the TTL by one.

---

### time

Round Trip Time (RTT).

The amount of time required for the packet to travel to the destination and back.

Lower values indicate a faster connection.

---

## Packet Statistics

When you stop the command using **Ctrl + C**, Linux displays statistics similar to:

```text
4 packets transmitted,
4 received,
0% packet loss
```

This tells you:

- Number of packets sent.
- Number of packets received.
- Percentage of packet loss.

---

## Real-world Use Case

Before connecting to a remote server using SSH, an administrator first verifies that the server is reachable using:

```bash
ping 192.168.1.10
```

---

# Command 2: `traceroute`

## What is traceroute?

The `traceroute` command displays every router (hop) that a packet passes through before reaching its destination.

---

## Why is it used?

It helps identify:

- Where network delays occur.
- Routing problems.
- Connectivity failures.

---

## Syntax

```bash
traceroute google.com
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `traceroute` | Displays the route packets follow. |
| `google.com` | Destination host. |

---

## Example Output

```text
1 192.168.1.1
2 105.xxx.xxx.xxx
3 ...
10 google.com
```

---

## Understanding the Output

Each numbered line represents a **hop**.

A hop is a router that forwards your packet toward its destination.

---

## Real-world Use Case

If users complain that a website is slow, `traceroute` can help identify the network segment causing the delay.

---

# Command 3: `tracepath`

## What is tracepath?

`tracepath` is similar to `traceroute` but does not require administrative privileges on most Linux distributions.

---

## Why is it used?

It is used to:

- Discover network paths.
- Measure network latency.
- Detect Maximum Transmission Unit (MTU) issues.

---

## Syntax

```bash
tracepath google.com
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `tracepath` | Traces the network path to a destination. |
| `google.com` | Destination host. |

---

## Real-world Use Case

Network engineers use `tracepath` to identify routing problems and MTU limitations without requiring root privileges.

---

## Commands Executed

```bash
ping google.com
ping 8.8.8.8
traceroute google.com
tracepath google.com
```

---

## Screenshot

```
screenshots/networking/lab-03-connectivity-testing.png
```

---

## Skills Gained

After completing this lab, I can:

- Test whether a remote host is reachable.
- Measure network latency.
- Interpret ICMP replies.
- Understand packet loss.
- Explain TTL (Time To Live).
- Identify network hops.
- Trace the route packets take across a network.
- Use traceroute and tracepath for troubleshooting.

---

## Conclusion

This lab introduced three essential Linux networking tools: `ping`, `traceroute`, and `tracepath`. Together, these commands help diagnose connectivity issues, measure network performance, and understand how data travels across networks.
---

# Lab 05 – DNS Resolution

## Objective

Learn how the Domain Name System (DNS) translates human-readable domain names into IP addresses using Linux DNS lookup utilities.

---

## What is DNS?

The **Domain Name System (DNS)** is often called the **phonebook of the Internet**.

Humans remember names such as:

```
google.com
github.com
openai.com
```

Computers communicate using IP addresses such as:

```
142.250.190.14
140.82.121.4
104.18.33.45
```

DNS converts domain names into IP addresses so computers can communicate with each other.

Without DNS, users would have to remember the IP address of every website they visit.

---

## Why is DNS Important?

DNS allows users to:

- Access websites using domain names.
- Locate servers on a network.
- Troubleshoot connectivity problems.
- Verify DNS records.
- Diagnose DNS configuration issues.

---

# Command 1: `nslookup`

## What is `nslookup`?

`nslookup` (Name Server Lookup) is a command-line utility used to query DNS servers and retrieve information about domain names.

---

## Why is it used?

It helps administrators:

- Resolve domain names.
- Verify DNS records.
- Troubleshoot DNS problems.

---

## Syntax

```bash
nslookup google.com
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `nslookup` | Queries a DNS server. |
| `google.com` | The domain name being queried. |

---

## Example Output

```text
Server: 192.168.1.1
Address: 192.168.1.1#53

Non-authoritative answer:
Name: google.com
Address: 142.250.190.14
```

---

## Understanding the Output

### Server

The DNS server that answered the request.

---

### Address

The IP address of the DNS server.

---

### Non-authoritative Answer

The response was obtained from a DNS cache rather than directly from the domain's authoritative DNS server.

---

### Name

The domain name queried.

---

### Address

The IPv4 address associated with the domain.

---

## Real-world Use Case

A website is not loading.

An administrator runs:

```bash
nslookup google.com
```

to determine whether the problem is related to DNS resolution.

---

# Command 2: `dig`

## What is `dig`?

`dig` (Domain Information Groper) is a powerful DNS diagnostic tool that provides detailed information about DNS queries and responses.

It is one of the most commonly used DNS troubleshooting tools by Linux administrators and cybersecurity professionals.

---

## Why is it used?

It allows users to:

- Query DNS records.
- Verify DNS servers.
- Troubleshoot DNS issues.
- Inspect DNS response details.

---

## Syntax

```bash
dig google.com
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `dig` | Performs a DNS query. |
| `google.com` | Domain being queried. |

---

## Example Output

```text
QUESTION SECTION:
google.com.

ANSWER SECTION:
google.com. 300 IN A 142.250.190.14
```

---

## Understanding the Output

### QUESTION SECTION

Displays the DNS record requested.

---

### ANSWER SECTION

Displays the DNS server's response.

---

### A Record

Maps a domain name to an IPv4 address.

Example:

```
google.com → 142.250.190.14
```

---

## Real-world Use Case

Cybersecurity professionals use `dig` to verify DNS records when investigating phishing domains or troubleshooting DNS issues.

---

# Command 3: `host`

## What is `host`?

The `host` command performs simple DNS lookups and displays the IP address associated with a domain name.

---

## Why is it used?

It provides a quick method for verifying DNS resolution without displaying extensive output.

---

## Syntax

```bash
host google.com
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `host` | Performs a DNS lookup. |
| `google.com` | Domain being queried. |

---

## Example Output

```text
google.com has address 142.250.190.14
```

---

## Real-world Use Case

An administrator quickly verifies whether a domain resolves to the expected IP address before investigating other network issues.

---

# Common DNS Record Types

| Record | Purpose |
|---------|---------|
| A | Maps a hostname to an IPv4 address. |
| AAAA | Maps a hostname to an IPv6 address. |
| CNAME | Creates an alias for another domain name. |
| MX | Specifies the mail server responsible for receiving email. |
| NS | Identifies the authoritative name servers for a domain. |
| TXT | Stores text-based information, often used for email verification and security. |

---

## Commands Executed

```bash
nslookup google.com
dig google.com
host google.com
```

---

## Screenshot

```
screenshots/networking/lab-04-dns-resolution.png
```

---

## Skills Gained

After completing this lab, I can:

- Understand how DNS translates domain names into IP addresses.
- Perform DNS lookups using `nslookup`.
- Retrieve detailed DNS information using `dig`.
- Perform quick DNS lookups using `host`.
- Identify common DNS record types.
- Troubleshoot DNS-related connectivity issues.

---

## Conclusion

This lab introduced the Linux DNS utilities `nslookup`, `dig`, and `host`. I learned how DNS resolution works, how to query DNS servers, interpret common DNS records, and use these tools to troubleshoot name resolution problems.


---

# Lab 06 – Routing and Neighbor Discovery

## Objective

Learn how Linux determines where network traffic should be sent by viewing the routing table and the neighbor (ARP) table.

---

## What is Routing?

Routing is the process of selecting the best path for data packets to travel from one network to another.

Every time you access a website, send an email, or connect to another device, Linux checks its **routing table** to determine where the packet should go.

If the destination is:

- On the same network → send it directly.
- On another network → send it to the **default gateway (router).**

---

# Command 1: `ip route`

## What is `ip route`?

The `ip route` command displays the system's routing table.

It shows how Linux decides where to send network traffic.

---

## Why is it used?

System administrators use `ip route` to:

- View the routing table.
- Identify the default gateway.
- Troubleshoot routing issues.
- Verify network configuration.

---

## Syntax

```bash
ip route
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `ip` | Linux networking utility. |
| `route` | Displays or manages the routing table. |

---

## Example Output

```text
default via 192.168.1.1 dev eth0

192.168.1.0/24 dev eth0 proto kernel scope link src 192.168.1.120
```

---

## Understanding the Output

### `default`

The default route.

If Linux does not know where a destination is located, it sends the packet here.

---

### `via 192.168.1.1`

The default gateway.

Usually your home or office router.

---

### `dev eth0`

The interface used to send packets.

Your interface could also appear as:

- enp0s3
- ens33
- wlan0

---

### `192.168.1.0/24`

Your local network.

Devices inside this subnet communicate directly without using the router.

---

### `src`

The source IP address Linux will use.

---

## Real-world Use Case

If your computer can communicate with local devices but cannot access the Internet, checking the routing table can help determine whether the default gateway is configured correctly.

---

# Command 2: `route`

## What is `route`?

The `route` command displays the routing table using the legacy networking utilities.

Although still available on many systems, it has largely been replaced by the `ip` command.

---

## Why is it used?

It allows administrators to:

- View routing information.
- Add or remove routes.
- Troubleshoot network communication.

---

## Syntax

```bash
route
```

or

```bash
route -n
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `route` | Displays the routing table. |
| `-n` | Displays numerical IP addresses instead of resolving hostnames. |

---

## Example Output

```text
Destination     Gateway         Genmask
0.0.0.0         192.168.1.1     0.0.0.0
192.168.1.0     0.0.0.0         255.255.255.0
```

---

## Real-world Use Case

Older Linux systems and legacy documentation often use the `route` command, so understanding it helps when maintaining existing environments.

---

# Command 3: `ip neigh`

## What is `ip neigh`?

The `ip neigh` command displays the **neighbor table**, also known as the **ARP table** for IPv4.

It maps IP addresses to MAC addresses on the local network.

---

## Why is it used?

It helps administrators:

- View neighboring devices.
- Verify ARP entries.
- Troubleshoot local network communication.

---

## Syntax

```bash
ip neigh
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `ip` | Linux networking utility. |
| `neigh` | Displays the neighbor (ARP) table. |

---

## Example Output

```text
192.168.1.1 dev eth0 lladdr 00:11:22:33:44:55 REACHABLE

192.168.1.15 dev eth0 lladdr AA:BB:CC:DD:EE:FF STALE
```

---

## Understanding the Output

### IP Address

The address of the neighboring device.

---

### dev

The network interface used.

---

### lladdr

The MAC address (Layer 2 address) of the neighboring device.

---

### REACHABLE

Linux has recently communicated with the device.

---

### STALE

The ARP entry exists but has not been used recently.

---

## Real-world Use Case

If two computers are on the same local network but cannot communicate, `ip neigh` can help verify whether Linux has successfully resolved the destination's MAC address.

---

## Commands Executed

```bash
ip route

route

route -n

ip neigh
```

---

## Screenshot

```
screenshots/networking/lab-05-routing.png
```

---

## Skills Gained

After completing this lab, I can:

- View the Linux routing table.
- Identify the default gateway.
- Interpret routing table entries.
- Understand how Linux chooses a path for network traffic.
- View the ARP (neighbor) table.
- Associate IP addresses with MAC addresses.

---

## Conclusion

This lab introduced routing and neighbor discovery in Linux. I learned how Linux determines where packets should be sent, how to identify the default gateway, and how the neighbor table maps IP addresses to MAC addresses for communication on a local network.


---

# Lab 07 – Viewing Network Connections and Listening Ports

## Objective

Learn how to view active network connections, listening ports, and identify which processes are using network resources.

---

## What are Network Connections?

Whenever your computer communicates over a network, it creates a **network connection**.

Examples include:

- Visiting a website
- Connecting to a server using SSH
- Downloading files
- Streaming videos
- Running a web server

Linux provides several tools to inspect these connections and identify which applications are using them.

---

# Command 1: `ss -tulnp`

## What is `ss`?

The `ss` (Socket Statistics) command displays information about network sockets.

It is the modern replacement for the older `netstat` command.

---

## Why is it used?

System administrators and cybersecurity professionals use `ss` to:

- View listening ports.
- Display active network connections.
- Identify which process is using a specific port.
- Troubleshoot networking problems.

---

## Syntax

```bash
ss -tulnp
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `ss` | Displays socket statistics. |
| `-t` | Show TCP sockets. |
| `-u` | Show UDP sockets. |
| `-l` | Show only listening sockets. |
| `-n` | Display numerical IP addresses and port numbers. |
| `-p` | Show the process using each socket. |

---

## Example Output

```text
Netid State  Recv-Q Send-Q Local Address:Port

tcp   LISTEN 0      128    0.0.0.0:22

udp   UNCONN 0      0      0.0.0.0:68
```

---

## Understanding the Output

### Netid

The network protocol.

Examples:

- TCP
- UDP

---

### State

Shows the socket's current state.

Common values include:

- LISTEN
- ESTABLISHED
- CLOSE-WAIT
- TIME-WAIT

---

### Local Address

The IP address where the application is listening.

---

### Port

The communication endpoint.

Example:

```text
22
```

Port **22** is used for SSH.

---

### Process

Displays the application that owns the socket.

Example:

```text
sshd
```

---

## Real-world Use Case

If a web server should be running on port **80**, you can verify it with:

```bash
ss -tulnp
```

---

# Command 2: `netstat -tulnp`

## What is `netstat`?

`netstat` (Network Statistics) is an older command used to display network connections, routing tables, interface statistics, and listening ports.

Although it has largely been replaced by `ss`, it is still available on many Linux systems.

---

## Why is it used?

It helps administrators:

- View open ports.
- Monitor active network connections.
- Troubleshoot network services.

---

## Syntax

```bash
netstat -tulnp
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `netstat` | Displays network statistics. |
| `-t` | TCP connections. |
| `-u` | UDP connections. |
| `-l` | Listening sockets only. |
| `-n` | Show numerical addresses. |
| `-p` | Show process information. |

---

## Example Output

```text
Proto Local Address      State

tcp   0.0.0.0:22         LISTEN

udp   0.0.0.0:68
```

---

## Real-world Use Case

Many older Linux tutorials still use `netstat`. Knowing this command helps you work with legacy systems.

---

# Command 3: `lsof -i`

## What is `lsof`?

`lsof` stands for **List Open Files**.

In Linux, network sockets are treated as files, so `lsof` can display which processes are using network connections.

---

## Why is it used?

It helps administrators:

- Identify which application is using a port.
- Detect unauthorized services.
- Troubleshoot port conflicts.

---

## Syntax

```bash
lsof -i
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `lsof` | Lists open files. |
| `-i` | Displays network-related files (Internet sockets). |

---

## Example Output

```text
COMMAND PID USER FD TYPE DEVICE NODE NAME

sshd    912 root 3u IPv4 TCP *:22 (LISTEN)
```

---

## Understanding the Output

### COMMAND

The application using the connection.

---

### PID

The Process ID.

---

### USER

The user running the process.

---

### NAME

Displays the IP address, port number, and connection state.

---

## Real-world Use Case

If port **8080** is already in use, `lsof -i` quickly identifies the process occupying that port so you can stop or reconfigure it.

---

## Commands Executed

```bash
ss -tulnp

netstat -tulnp

lsof -i
```

---

## Screenshot

```
screenshots/networking/lab-06-network-connections.png
```

---

## Skills Gained

After completing this lab, I can:

- View listening TCP and UDP ports.
- Identify active network connections.
- Determine which process owns a network socket.
- Interpret common socket states such as LISTEN and ESTABLISHED.
- Troubleshoot port conflicts using Linux networking tools.

---

## Conclusion

This lab introduced three essential Linux networking commands: `ss`, `netstat`, and `lsof`. These tools allow administrators and cybersecurity professionals to inspect active connections, identify listening services, and determine which applications are using specific network ports. Mastering these commands is fundamental for network troubleshooting and security investigations.


---

# Lab 08 – Remote Administration and File Transfer

## Objective

Learn how to securely connect to a remote Linux system and transfer files using SSH-based tools.

---

## What is Remote Administration?

Remote administration allows you to manage another computer over a network without being physically present at the machine.

Linux commonly uses **SSH** for secure remote access, and related tools such as **SCP** and **SFTP** for file transfer.

---

# Command 1: `ssh username@ip-address`

## What is `ssh`?

The `ssh` command stands for **Secure Shell**. It creates an encrypted connection between your local machine and a remote Linux system.

---

## Why is it used?

It is used to:

- Log in to remote Linux machines.
- Run commands on remote servers.
- Manage systems securely over the network.

---

## Syntax

```bash
ssh username@ip-address
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `ssh` | Secure Shell client. |
| `username` | The account on the remote system. |
| `ip-address` | The remote machine’s IP address. |

---

## Example

```bash
ssh cypher@192.168.1.10
```

---

## Expected Output

If the connection is successful, you may see a message asking whether you trust the host, followed by a password prompt. After authentication, the shell changes to the remote system.

---

## Real-world Use Case

System administrators use SSH to manage servers, fix problems, and run maintenance tasks without being physically at the machine.

---

# Command 2: `scp file username@ip-address:/path/`

## What is `scp`?

The `scp` command stands for **Secure Copy**. It transfers files securely between two computers over SSH.

---

## Why is it used?

It is used to:

- Upload files to a remote system.
- Download files from a remote system.
- Transfer files securely without using plain text protocols.

---

## Syntax

```bash
scp file username@ip-address:/path/
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `scp` | Secure copy utility. |
| `file` | The file being transferred. |
| `username@ip-address` | Remote login details. |
| `/path/` | Destination path on the remote system. |

---

## Example

```bash
scp notes.txt cypher@192.168.1.10:/home/cypher/
```

---

## Expected Output

The file is copied to the remote machine over an encrypted connection.

---

## Real-world Use Case

Administrators use `scp` to copy configuration files, scripts, and logs between systems.

---

# Command 3: `sftp username@ip-address`

## What is `sftp`?

The `sftp` command stands for **Secure File Transfer Protocol**. It opens an interactive file transfer session over SSH.

---

## Why is it used?

It is used to:

- Upload files.
- Download files.
- Browse remote directories.
- Transfer files securely.

---

## Syntax

```bash
sftp username@ip-address
```

---

## Breaking Down the Command

| Part | Meaning |
|------|---------|
| `sftp` | Secure file transfer client. |
| `username` | Remote account name. |
| `ip-address` | Remote system IP address. |

---

## Expected Output

A secure file transfer prompt opens after successful authentication.

---

## Real-world Use Case

SFTP is useful when you want an interactive file transfer session instead of a one-line copy command.

---

# Command 4: `exit`

## What is `exit`?

The `exit` command closes the current shell session.

---

## Why is it used?

It is used to:

- Leave an SSH session.
- Close an SFTP session.
- Exit the current terminal shell.

---

## Syntax

```bash
exit
```

---

## Expected Output

The remote or local session closes and returns you to the previous shell or terminal state.

---

## Real-world Use Case

After finishing remote administration or file transfer, use `exit` to close the session safely.

---

## Commands Executed

```bash
ssh cypher@192.168.1.10
scp notes.txt cypher@192.168.1.10:/home/cypher/
sftp cypher@192.168.1.10
exit
```

---

## Screenshot

```
screenshots/networking/lab-07-remote-administration.png
```

---

## Skills Gained

After completing this lab, I can:

- Connect to a remote Linux machine using SSH.
- Copy files securely using SCP.
- Start an interactive SFTP session.
- Exit remote sessions properly.
- Understand the purpose of SSH-based remote administration tools.

---

## Conclusion

This lab introduced remote administration and secure file transfer in Linux. I learned how to connect to a remote machine using SSH, transfer files with SCP and SFTP, and safely end a session using `exit`.


---

# Lab 08 – FTP and SFTP Session Commands

## Objective

Learn how to navigate and transfer files inside an active FTP or SFTP session.

> **Note:** These commands are not used in the normal Linux terminal.  
> They work **after connecting to a remote FTP or SFTP server**.

---

## What is FTP/SFTP?

- **FTP** means *File Transfer Protocol*.
- **SFTP** means *Secure File Transfer Protocol*.

These are used to move files between your local computer and a remote server.

---

### Command 1: `dir`

#### Description

The `dir` command displays the files and folders in the current remote directory.

#### Syntax

```bash
dir
```

#### Expected Output

Shows a list of files and folders on the remote server.

#### Real-world Use Case

Used to check what files already exist on the remote server before uploading or downloading anything.

---

### Command 2: `cd "dirname"`

#### Description

The `cd` command changes the current directory inside the FTP or SFTP session.

#### Syntax

```bash
cd dirname
```

#### Example

```bash
cd documents
```

#### Expected Output

Moves into the specified remote directory.

#### Real-world Use Case

Used to move into a folder on the remote server before transferring files.

---

### Command 3: `put file`

#### Description

The `put` command uploads a file from your local computer to the remote server.

#### Syntax

```bash
put file
```

#### Example

```bash
put notes.txt
```

#### Expected Output

Uploads `notes.txt` to the current remote directory.

#### Real-world Use Case

Used to send scripts, documents, or configuration files to a remote server.

---

### Command 4: `get file`

#### Description

The `get` command downloads a file from the remote server to your local computer.

#### Syntax

```bash
get file
```

#### Example

```bash
get report.txt
```

#### Expected Output

Downloads `report.txt` from the remote server to your local machine.

#### Real-world Use Case

Used to retrieve log files, backups, or documents from a remote server.

---

### Command 5: `quit`

#### Description

The `quit` command ends the FTP or SFTP session.

#### Syntax

```bash
quit
```

#### Expected Output

Closes the remote file transfer session and returns you to the local terminal.

#### Real-world Use Case

Used when you are done transferring files and want to disconnect safely.

---

## Commands Executed

```bash
dir
cd documents
put notes.txt
get report.txt
quit
```

---

## Screenshot

```
screenshots/networking/lab-08-ftp-sftp-session.png
```

---

## Skills Gained

After completing this lab, I can:

- List files in a remote directory.
- Change directories inside an FTP or SFTP session.
- Upload files to a remote server.
- Download files from a remote server.
- Exit an FTP or SFTP session safely.

---

## Conclusion

This lab introduced the basic commands used inside FTP and SFTP sessions. I learned how to browse remote directories, transfer files in both directions, and close the session when finished.
