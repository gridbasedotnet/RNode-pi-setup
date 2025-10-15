# RNode-pi-setup
# RNode + Reticulum + NomadNet Raspberry Pi Setup

A complete example configuration for running a **Reticulum node**, **RNode LoRa interface**, and **self-hosted NomadNet site** on a Raspberry Pi.  
Includes persistent device mapping, startup/shutdown scripts, and example configuration files.

---

## 🧠 Overview

This repository is designed for anyone who wants to:

- Host their own NomadNet `.mu` pages locally  
- Use a connected **RNode LoRa radio** for off-grid mesh networking  
- Connect to the **RNS Amsterdam Testnet** or run fully offline  
- Maintain predictable, persistent device mapping (`/dev/rnode0`)  

---

## 🧩 Components

| File | Purpose |
|------|----------|
| `config/reticulum.conf` | Complete Reticulum configuration for TCP, LAN, and RNode |
| `config/99-rnode.rules` | udev rule for persistent RNode device mapping |
| `scripts/start` | Launches the full stack (Reticulum, announce, NomadNet) |
| `scripts/stop` | Safely shuts everything down |
| `docs/INSTALL.md` | Step-by-step setup instructions |
| `docs/NOMADNET_SETUP.md` | How to host and announce your `.mu` site |
| `docs/TROUBLESHOOTING.md` | Common fixes, port forwarding tips, etc. |

---

## 🚀 Quick Start

```bash
git clone https://github.com/YOURUSERNAME/rnode-pi-setup.git
cd rnode-pi-setup
sudo cp config/99-rnode.rules /etc/udev/rules.d/
sudo udevadm control --reload-rules && sudo udevadm trigger

