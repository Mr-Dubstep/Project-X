# Project X 0.1 — Genesis Prototype

Project X 0.1 is an early prototype of a lightweight Linux-based environment designed to run inside Alpine Linux on Android.  
This release provides the initial structure, tools, and interface that future versions will build upon.

## Overview
Project X runs on top of an Alpine Linux root filesystem and uses BusyBox 1.36.1 as its core userland.  
The system includes a minimal TUI (Text User Interface) that starts automatically and provides access to basic tools and features.

This release is intended for testing, exploration, and development.  
It is not a full operating system and should be considered experimental.

---

## Setup Instructions

### Requirements
- Android device  
- Termux installed  
- Storage permission enabled (`termux-setup-storage`)  
- `proot-distro` installed in Termux  

### Setup
# 1. Navigate to the folder where you placed the archive
cd ~/storage/shared/Projects

# 2. Extract the Project X 0.1 archive
tar -xzf projectx-0.1.tar.gz

# This creates:
# projectx-rootfs/

# 3. Start Alpine (base environment)
proot-distro login alpine

# 4. Inside Alpine, start Project X
xboot

# 5. If xboot does not work, use the fallback boot command:
proot -0 \
  -r ~/projectx-rootfs \
  -b /dev:/dev \
  -b /proc:/proc \
  -b /sys:/sys \
  -w / \
  --kill-on-exit \
  /sbin/init

# The Project X TUI will start automatically.
