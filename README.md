# Task 5: Network Traffic Analysis with Wireshark

## Objective
Leverage Wireshark to capture live network traffic, isolate key protocols, and analyze low-level packet behavior. This task aims to deepen understanding of packet-level data inspection and protocol dissection.

## **Deliverables**: A packet capture (.pcap) file and a short report of protocols identified.

---

## Tools & Environment

- **Wireshark** (Packet sniffer & network protocol analyzer)
- **OS:** Windows 10 / Linux (Ubuntu 22.04)
- **Interfaces:** Wireless LAN (802.11) – `wlan0` / `Wi-Fi`
- **Command line tools:** `ping`, `curl` for traffic generation

---

## Procedure Summary

1. **Capture Initialization**
   - Launched Wireshark.
     ![image](https://github.com/user-attachments/assets/6c95ecd8-701e-4d28-9006-d52effacdd6e)
   - Selected the primary network interface.
   - Initiated packet capture.
     ![image](https://github.com/user-attachments/assets/295370ee-784c-448c-86b7-86c9193fb19a)

2. **Traffic Simulation**
   - Accessed `` via browser.
   - Performed `ping google.com` and `curl ifconfig.me`.
     ![image](https://github.com/user-attachments/assets/bedc7c8d-c592-4b9f-bfe1-ce913e2aac41)

3. **Capture Termination**
   - Stopped capture after 60 seconds.
   - Applied filters to isolate protocol-specific traffic.

4. **Filtering & Inspection**
   - Applied filters:
     - `tcp`
       ![image](https://github.com/user-attachments/assets/fa88825c-ec55-4e95-bd89-0ba58292c1cf)
    - `dns`
       ![image](https://github.com/user-attachments/assets/19b11631-1544-49ef-b783-81e78bf2db32)
   - Investigated packet metadata, flags, and response codes.

6. **Export**
   - Saved session as `task5_capture.pcapng`.

---

## Protocols Identified

| Protocol | Layer | Observations |
|----------|-------|--------------|
| **DNS** | Application | Observed domain name resolution with standard query-response model |
| **TCP** | Transport | Noted 3-way handshake (SYN, SYN-ACK, ACK), ACK flags, and sequence/ack numbers |

---

## Outcome

- Developed proficiency in using Wireshark filters and dissecting packet-level data.
- Improved understanding of TCP/IP communication, protocol encapsulation, and real-time traffic analysis.
- Exported `.pcapng` file and documented findings.

---

## Deliverables

- `Task5_capture.pcapng` – Raw capture file
- `report_task5_detailed.md` – Advanced technical report
