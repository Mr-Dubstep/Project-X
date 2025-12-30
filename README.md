# Project X 0.1 Prototype

Project X 0.1 is the first functional prototype of the system.  
It provides the foundational structure for future development and serves as an archival reference for the early state of the project.

## Features
- Core TUI menu with basic system tools  
- Experimental GUI launcher  
- Minimal filesystem layout  
- BusyBox-based command environment

- ## Setup Instructions

### Requirements
- Android device  
- Termux installed  
- Storage permission enabled (`termux-setup-storage`)

### Setup
# 1. Navigate to the folder where you placed the archive
cd ~/storage/shared/Your-Folder-Name (Replace with the folder name you chose)

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

## Purpose
This release captures the initial working state of Project X before further development.  
It is intended for testing, exploration, and historical preservation.

## Notes
- This prototype is not feature-complete  
- Some components are experimental or placeholder  
- Future releases will expand functionality and improve stability

## License
This prototype is provided as-is for testing and development purposes.
