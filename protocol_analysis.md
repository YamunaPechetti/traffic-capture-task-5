# Protocol Analysis Report - Wireshark Traffic Capture

## Objective
To capture and analyze live network traffic using Wireshark and identify common internet communication protocols.

---

## Identified Protocols

### 1. DNS (Domain Name System)
- **Purpose**: Translates domain names (e.g., `www.google.com`) into IP addresses.
- **Observed Behavior**:
  - Multiple DNS queries were seen for resolving domain names.
  - Queries were followed by corresponding DNS responses.

### 2. TCP (Transmission Control Protocol)
- **Purpose**: Establishes reliable, ordered, and error-checked connections between hosts.
- **Observed Behavior**:
  - TCP 3-way handshakes initiating connections on ports such as 443.
  - Reliable stream-based communication, often preceding encrypted traffic.

### 3. TLSv1.2 (Transport Layer Security)
- **Purpose**: Provides encryption, integrity, and authentication for secure communication (e.g., HTTPS).
- **Observed Behavior**:
  - TLS negotiation following TCP handshakes.
  - Server Hello, Certificate exchange, and Client Key Exchange packets.
  - Encrypted application data transfer over established secure connections.

---

## Packet Details

### DNS Query Example
- **Source Port**: 60963
- **Destination Port**: 53 (DNS)
- **Query**: A record for `brave.com`
- **Response**: 162.159.36.1

### TCP Handshake Example
- **SYN → SYN-ACK → ACK** observed for initiating a connection.
- **Destination Port**: 443 (HTTPS)

### TLSv1.2 Example
- **Client Hello** sent after TCP connection established.
- **Server Certificate** received.
- **Encrypted Application Data** starts post-handshake.
