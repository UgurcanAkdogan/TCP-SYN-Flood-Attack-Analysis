# TCP-SYN-Flood-Attack-Analysis
A comprehensive Cybersecurity Incident Report analyzing a TCP SYN Flood attack and resource exhaustion. This project was completed as part of the Google Cybersecurity Professional Certificate, focusing on packet sniffing (Wireshark) and network security mitigation.
# Incident Report: TCP SYN Flood Attack Analysis

## 📌 Project Overview
In this incident, I analyzed a network interruption caused by a **TCP SYN Flood** attack. The investigation focused on identifying the attack pattern in Wireshark logs, understanding the exploitation of the TCP three-way handshake, and proposing mitigation strategies.


## 🔍 Investigation Findings

### Section 1: Identify the Attack Type
* **Symptoms:** Users reported "Connection Timeout" errors while accessing the web server.
* **Log Discovery:** Captured traffic showed a massive volume of **TCP SYN** packets originating from a **single, unfamiliar source IP address (203.0.113.0)**.
* **Attack Classification:** This is identified as a **Denial of Service (DoS)** attack, specifically a **SYN Flood**, aimed at exhausting server resources.

### Section 2: Technical Root Cause (TCP Handshake)
The attack exploits the standard TCP connection process:
1.  **Standard Handshake:** SYN -> SYN-ACK -> ACK (Connection Established).
2.  **The Attack:** The malicious actor sends thousands of **SYN** packets but never sends the final **ACK**.
3.  **Result:** The server is left with thousands of "half-open" connections in its backlog queue, leading to resource exhaustion. Legitimate users cannot establish a connection as a result.

## 🛠 Tools Used
* **Wireshark:** Packet analysis and traffic pattern identification.
* **Network Fundamentals:** TCP/IP Suite, Three-Way Handshake analysis.

## 🎓 Learning Outcomes
* Identified the difference between a single-source DoS and a distributed DDoS.
* Analyzed protocol-level vulnerabilities in the transport layer.
* Documented findings in a professional Cybersecurity Incident Report.
