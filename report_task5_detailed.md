# Technical Report - Advanced Protocol Analysis Report — Task 5

## **Objective**:
To perform real-time network traffic capture using Wireshark and conduct protocol-layer analysis focusing on TCP, DNS, and HTTP communications.

## Tools Used:
- Wireshark (GUI-based packet analyzer)
- Browser: Google Chrome
- Command-line Utilities: ping, curl

## Network Interface: Wireless LAN (802.11)

## Methodology:

### Setup:

- Wireshark was configured to monitor the active interface (Wi-Fi).
- Capture began using standard live traffic conditions.
- Simulated Network Activity:
- Visited public domains (google.com).
- Executed ping to generate ICMP and DNS traffic.
- Used curl ifconfig.me to trigger HTTP requests.

## Filtered Protocol Views:

### Applied structured filters:

`tcp.stream eq 0` — isolate a specific TCP conversation

`http.request.method == "GET"` — inspect web requests

`dns.qry.name == "google.com"` — observe name resolutions

## Protocol Dissection:
1. DNS (Domain Name System):
Layer: Application
Behavior: 
- Standard query/response using UDP port 53. 
- Observed recursive queries, including A record requests.
- Advanced Insight: TTL values and multiple answer sections show DNS caching behavior.

2. HTTP (HyperText Transfer Protocol):
Layer: Application
Behavior:
- HTTP GET request to Google domains.
- Observed HTTP/2 upgrade attempts.
Headers Analyzed: User-Agent, Host, Accept, Referer.

3. TCP (Transmission Control Protocol):
Layer: Transport
Behavior:
- Typical 3-way handshake with proper flag sequencing (SYN, SYN-ACK, ACK).
- Captured session teardown using FIN/ACK.
Metrics Observed:
- Sequence and acknowledgment numbers.
- Retransmissions and TCP window sizes.

## Packet Export:
- **Format**: .pcapng (Preferred for Wireshark metadata compatibility)
- **File**: task5_capture.pcapng
- **Capture Duration**: ~60 seconds

## Key Takeaways:
- Proficiency in using Wireshark for protocol filtering and session tracking.
- Enhanced understanding of how common protocols behave under real traffic.
- Awareness of how traffic inspection can assist in incident response and diagnostics.

## Conclusion:
The task demonstrated how protocol-specific traffic flows across a network and how to dissect packets at different OSI layers. Wireshark proved to be a powerful tool in network diagnostics and cybersecurity awareness.
