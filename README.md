# Automated Network Infrastructure Diagnostics Tool

A lightweight, automated Python automation script designed to execute real-time Level-1 network health assessments for enterprise IT environments. 

## 📌 Project Overview
In a corporate environment, manual troubleshooting of network issues consumes significant support time. This project automates the initial diagnostic routines by sequentially verifying endpoints to isolate where a network failure lies—whether it is an issue with the local gateway (router), the external internet provider, or the internal corporate server.

## 🛠️ Technology Stack
* **Language:** Python 3.x
* **Core Libraries:** `os` (System interaction library)
* **Network Protocol:** ICMP (Ping requests)

## ⚙️ How It Works (The Logic)
1. **Target Mapping:** Uses a Python Dictionary to map critical network nodes (Local Router, Google DNS, and Internal Corporate Server) to their respective IP addresses.
2. **Automated Iteration:** A `for` loop automatically steps through each infrastructure node without requiring manual command entry.
3. **Connectivity Validation:** Utilizes `os.system` to send ICMP ping packets to check node responsiveness.
4. **Conditional Alerting:** Executes an `if-else` path to capture system return codes. If a packet drops, it immediately triggers an alert indicating exactly where the network chain is broken.

## 💻 Sample Project Output
When a network connection fails locally, the system automatically detects the disruption and flags the chain reaction downstream:

```text
--- Starting IT Support Diagnostic Check ---
❌ Local Router (Gateway) (192.168.1.1) is OFFLINE! Attention Required.
❌ Google DNS (Internet Check) (8.8.8.8) is OFFLINE! Attention Required.
❌ Company Internal Server (10.0.0.1) is OFFLINE! Attention Required.
--- Diagnostic Complete ---
