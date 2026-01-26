# 📡 Nmap Network Scanning Guide
*Reference for network discovery and vulnerability scanning.*

## 🎯 Target Specification
How to tell Nmap what to scan.
| Command | Description |
| :--- | :--- |
| `nmap 192.168.1.1` | Scan a single IP |
| `nmap 192.168.1.1-254` | Scan a range (entire subnet) |
| `nmap -iL targets.txt` | Scan a list of IPs from a file |
| `nmap -p 80,443 <IP>` | Scan only specific ports (Web) |
| `nmap -p- <IP>` | Scan ALL 65,535 ports (Takes longer) |

## 🕵️ Scan Techniques
Different ways to connect.
| Flag | Name | Description |
| :--- | :--- | :--- |
| `-sS` | **SYN Scan** (Stealth) | Default root scan. Doesn't complete the connection (quieter). |
| `-sT` | **Connect Scan** | Default non-root scan. Completes the connection (easier to detect). |
| `-sU` | **UDP Scan** | Scans UDP ports (DNS, DHCP). Slow but necessary. |
| `-Pn` | **No Ping** | Assume target is up (Skip host discovery). Useful for firewalls. |

## 🛠️ Service & OS Detection
Find out what is running.
| Flag | Description |
| :--- | :--- |
| `-sV` | **Version Detection**. Finds software versions (e.g., Apache 2.4.49). |
| `-O` | **OS Detection**. Guesses the operating system (Windows/Linux). |
| `-A` | **Aggressive Scan**. Combines OS, Version, Scripts, and Traceroute. |

## ⚡ Timing & Performance
Speed it up or slow it down.
| Flag | Mode | Use Case |
| :--- | :--- | :--- |
| `-T0` | Paranoid | Extremely slow to evade IDS. |
| `-T3` | Normal | Default speed. |
| `-T4` | Aggressive | Fast scan (Best for CTFs/Learning). |
| `-T5` | Insane | Very fast (Can crash targets/miss ports). |

## 📜 Useful NSE Scripts
Using the Nmap Scripting Engine.
| Command | Description |
| :--- | :--- |
| `--script=default` | Run basic default scripts. |
| `--script=vuln` | Check for known vulnerabilities (CVEs). |
| `--script=http-title` | Grab the title of the website. |
