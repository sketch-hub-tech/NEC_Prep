# Chapter 5 — Concept of Computer Network and Network Security System
*(Code ACtE05 — 10 questions)*

---

## 5.1 Introduction to Computer Networks and Physical Layer

### Basics
- **Network:** collection of interconnected autonomous computers that exchange data.
- **Networking model:** layered; each layer provides services to the layer above.
- **Protocol:** set of rules governing communication. **Standards:** de facto/de jure (ISO, IEEE, IETF, ITU).

### OSI model (7 layers — bottom up)
| Layer | Function | PDU | Devices |
|---|---|---|---|
| 7 Application | Network services to apps (HTTP, FTP, SMTP) | Data | Gateway |
| 6 Presentation | Encryption, compression, formatting | Data | — |
| 5 Session | Establishes/manages sessions, dialog control | Data | — |
| 4 Transport | End-to-end delivery, flow & error control | **Segment** | Gateway |
| 3 Network | Logical addressing (IP), routing | **Packet** | **Router** |
| 2 Data link | Framing, MAC addressing, error detection | **Frame** | **Switch/Bridge** |
| 1 Physical | Bits on medium | **Bits** | Hubs, repeaters, NIC |

### TCP/IP model (4 layers)
1. **Application** (HTTP, FTP, SMTP, DNS…) — combines OSI 5-7
2. **Transport** (TCP/UDP)
3. **Internet/Network** (IP)
4. **Network Access/Link** (Ethernet, WiFi)

### Networking devices
- **Hub:** physical layer, broadcasts to all ports (collision domain = all).
- **Repeater:** regenerates signal (physical).
- **Bridge:** data link, filters by MAC.
- **Switch:** multiport bridge, MAC-based forwarding (dedicated bandwidth).
- **Router:** network layer, IP-based routing between networks.
- (Older L3: gateway works across protocols.)

### Transmission media
- **Guided:** twisted pair (UTP/STP), coaxial, **optical fiber** (highest bandwidth, immune to EMI).
- **Unguided (wireless):** radio, microwave, infrared, satellite.
- UTP categories: Cat5e, Cat6 (100m limit).

---

## 5.2 Data Link Layer

### Services & framing
- Framing, error control, flow control, access control.

### Error detection & correction
- **Parity check:** 1 bit, catches odd number of bit errors only.
- **Checksum:** sum of data, 1's complement.
- **CRC (Cyclic Redundancy Check):** polynomial division; strong; used in Ethernet; remainder = CRC (usually 32-bit).
- **Hamming code:** error **detection + correction** (single-bit); redundancy bits: `2^r ≥ m + r + 1`.

### Flow control
- **Stop-and-Wait:** send one frame, wait ACK — inefficient.
- **Sliding window:** multiple frames in flight; Go-Back-N (retransmit from lost), Selective Repeat (retransmit only lost).

### ARQ protocols
- **Stop-and-Wait ARQ, Go-Back-N ARQ, Selective-Repeat ARQ.**

### Multiple access protocols
- **Random access:** ALOHA (pure/slotted), **CSMA**, **CSMA/CD** (Ethernet, collision detection, backoff), **CSMA/CA** (wireless).
- **Controlled access:** polling, token passing.
- **Channelization:** FDMA, TDMA, CDMA.

### Addressing, ARP, Ethernet, IEEE standards
- **MAC address:** 48-bit physical address burnt into NIC (12 hex digits).
- **ARP (Address Resolution Protocol):** maps **IP → MAC** on LAN; **RARP** reverse (MAC→IP, legacy).
- **Ethernet IEEE 802.3** — CSMA/CD; frame: preamble, dest/source MAC, type, data, **CRC/FCS (trailer)**.
- **802.4 Token Bus, 802.5 Token Ring** — token passing (no collision).
- **Wireless LAN IEEE 802.11 (Wi-Fi); Bluetooth 802.15.**
- **PPP (Point-to-Point Protocol):** dial/DSL connections; framing + LCP/NCP; HDLC-like.
- **Wide area protocols:** X.25, frame relay, ATM (fixed 53-byte cells).

---

## 5.3 Network Layer

### IP addressing (IPv4, classful)
| Class | Range (first octet) | Default mask | Hosts/network |
|---|---|---|---|
| A | 1–126 | 255.0.0.0 (/8) | ~16.7 M |
| B | 128–191 | 255.255.0.0 (/16) | 65,534 |
| C | 192–223 | 255.255.255.0 (/24) | 254 |
| D | 224–239 (multicast) | — | — |
| E | 240–255 (reserved) | — | — |

- **Private addresses:** 10.x, 172.16–31.x, 192.168.x; loopback 127.0.0.1.
- **Subnetting:** borrow host bits → subnet bits; usable hosts = `2^h − 2`. **VLSM/CIDR:** `/26` = 255.255.255.192 = 64 addresses → 62 usable.
- **IPv6:** **128-bit**, 8 groups of 4 hex digits; no NAT needed; supports multicast/anycast; transition: dual-stack, tunneling, translation; auto-configuration, header simpler (fixed 40 bytes), extension headers.

### Routing
- **Routing algorithm types:**
  - **Shortest path (Dijkstra):** link-state, computes min-cost tree, global info.
  - **Flooding:** every packet to every link except incoming (broadcast/simple).
  - **Distance vector (Bellman-Ford):** share "distance vector" with neighbors (RIP); **count-to-infinity** problem.
  - **Link state:** share map with all routers (OSPF); Dijkstra.
- **Protocols:**
  - **RIP (Routing Information Protocol):** distance vector; metric = hop count (max 15); UDP port 520; 30s updates.
  - **OSPF (Open Shortest Path First):** link-state; Dijkstra; fast convergence; area-based; IP protocol 89.
  - **BGP (Border Gateway Protocol):** path vector, inter-AS (Internet) routing; TCP 179.
  - Unicast (one-to-one) vs multicast (one-to-many, IGMP) routing.
- **ICMP:** error reporting & diagnostics (**ping** uses echo/reply); **ARP/RARP** at network/data-link boundary. IP is **connectionless, best-effort, unreliable**.

---

## 5.4 Transport Layer

### Services
- End-to-end delivery between processes; port and socket addressing.
- **Multiplexing/demultiplexing** (many apps → transport, split back).
- **Port numbers:** well-known (0–1023), registered (1024–49151), ephemeral (49152+).
- Well-known ports: **HTTP 80, HTTPS 443, FTP 21, SSH 22, Telnet 23, SMTP 25, POP3 110, IMAP 143, DNS 53, DHCP 67/68, SNMP 161.**

### TCP vs UDP
| TCP | UDP |
|---|---|
| **Connection-oriented** (3-way handshake) | Connectionless |
| Reliable (ACKs, retransmission) | Unreliable (best effort) |
| Flow & congestion control | No flow control |
| Byte stream (segments) | Datagram |
| Slower, headers 20+ bytes | Fast, header 8 bytes |
| Used: HTTP, FTP, SMTP | Used: DNS, VoIP, streaming, DNS queries |

- **TCP connection establishment (3-way handshake):** `SYN → SYN+ACK → ACK`.
- **Connection release:** 4-way handshake (FIN/ACK); 2×MSL wait.
- **Flow control via sliding window** (advertised window); **congestion control:** slow start, congestion avoidance, fast retransmit/recovery; **AIMD**.

### Socket
- **Socket = IP + port** ("protocol endpoint"). Server: bind → listen → accept; client: connect. Socket programming with `socket(), bind(), listen(), accept(), connect(), send/recv, close()`.

---

## 5.5 Application Layer

- **Web:** **HTTP/HTTPS** — request/response, stateless; **HTTPS = HTTP over TLS/SSL** (port 443). Methods: GET, POST, PUT, DELETE, HEAD.
- **FTP:** **File Transfer Protocol** (port 21 control, 20 data); connection-oriented. Clients: **PuTTY, WinSCP** (also SSH clients).
- **Electronic mail:**
  - **SMTP (port 25):** send/mail transfer (MTA→MTA).
  - **POP3 (110) / IMAP (143):** retrieval. IMAP keeps mail on server, syncs; POP3 downloads & deletes.
- **DNS:** hierarchical name → IP; records A (IPv4), AAAA (IPv6), MX (mail), CNAME, NS, PTR; distributed servers (root → TLD → authoritative); uses **UDP port 53** (TCP for zone transfer).
- **P2P applications:** BitTorrent, file sharing; peers act as client+server.
- **Socket programming:** as in 5.4.
- **Application server concept:** servers hosting apps (web/app/database) accessible over network; 3-tier architecture.
- **Traffic analyzers/monitoring:**
  - **MRTG / PRTG:** monitor & graph network bandwidth/traffic.
  - **SNMP (Simple Network Management Protocol, port 161):** manager–agent model, MIB, traps; network device monitoring.
  - **Packet Tracer:** Cisco network simulator.
  - **Wireshark:** packet capture & protocol analyzer.

---

## 5.6 Network Security

### Security concepts
- **CIA triad:** **Confidentiality** (secrecy), **Integrity** (no tampering), **Availability** (accessible).
- **Additional:** authentication, authorization (AAA), non-repudiation.
- **Types of security/attacks:**
  - **Passive:** eavesdropping, traffic analysis (hard to detect).
  - **Active:** **DoS/DDoS, Man-in-the-Middle (MITM), replay, masquerade, sniffing, session hijacking, malware (virus/worm/trojan/ransomware/spyware), phishing, password attacks.**

### Cryptography
- **Symmetric (private/secret key):** same key both sides; fast; DES, 3DES, **AES**, RC4.
- **Asymmetric (public key):** key pair (public + private); slow; **RSA**, Diffie-Hellman, ECC, ElGamal.
- **RSA algorithm:**
  1. Choose primes p, q; n = p·q; φ(n) = (p−1)(q−1).
  2. Choose e (1<e<φ, gcd(e,φ)=1).
  3. d = e⁻¹ mod φ (d·e ≡ 1 mod φ).
  4. **Public key (e, n); Private key (d, n).**
  5. Encrypt: C = Mᵉ mod n; Decrypt: M = Cᵈ mod n.
- **Hybrid systems:** use asymmetric to exchange symmetric (session) key (SSL/TLS, PGP).
- **Hash & MAC:** **SHA-1/SHA-256**, MD5 (broken), HMAC; integrity check.

### Digital signatures, e-mail & connections
- **Digital signature = encrypt hash of message with sender's private key**; verifies **authenticity + integrity + non-repudiation**.
- **PGP (Pretty Good Privacy):** e-mail encryption (hybrid: symmetric key + RSA); compression + signing.
- **SSL/TLS:** secures TCP connections; handshake exchanges keys & certificates; provides confidentiality & integrity. **HTTPS uses it.** TLS handshake: ClientHello → ServerHello(hello + cert) → key exchange → ChangeCipherSpec → Finished.
- **IPsec:** network-layer security; **AH** (integrity/auth), **ESP** (confidentiality + auth); modes: **transport & tunnel**. **VPN** = encrypted tunnel over public internet (IPsec, SSL/TLS, PPTP, L2TP).
- **Wireless security: WEP** (weak, RC4) → **WPA** (TKIP) → **WPA2/WPA3** (AES-CCMP).
- **Firewalls:** filter traffic between networks; packet filtering, stateful inspection, application-level **proxy/IDS/IPS**.

---

## Formula Box (Chapter 5 — must memorize)
- OSI 7 layers (mnemonic): Application/Physical at ends; Transport=segment, Network=packet, DLL=frame
- 802.3 Ethernet, 802.4 Token Bus, 802.5 Token Ring, 802.11 Wi-Fi; ARP = IP→MAC
- Class A /8, B /16, C /24; private: 10., 172.16-31., 192.168.; IPv6 = 128-bit
- RIP hop≤15; OSPF link-state/Dijkstra; BGP = path vector, TCP 179
- Ports: HTTP 80, HTTPS 443, FTP 21, DNS 53, SMTP 25, POP3 110, IMAP 143, SNMP 161, SSH 22
- TCP 3-way: SYN→SYN+ACK→ACK; TCP reliable, UDP fast (8-byte header)
- Hamming: 2^r ≥ m+r+1; CRC → Ethernet
- RSA: C = M^e mod n, M = C^d mod n; public key (e,n)
- CIA triad; PGP for mail; SSL/TLS for TCP; IPsec/VPN for IP; WEP→WPA2→WPA3