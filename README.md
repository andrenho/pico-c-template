# Pico C template
A template for new Raspberry Pi Pico projects using the C SDK.

# Features
- A skeleton CMake project containing some usefult targets
- A skeleton Kicad template for the circuit
- Build the firmware locally and install it remotely (for example, use a PC to edit and compile the firmware, and a Raspberry Pi to upload it via SWD)

# Included targets
- `make`: the base target also prints the firmware size after building it
- `make upload-usb`: upload firmware using the PC USB port (requires restarting the Pico with BOOTSEL)
- `make upload-swd`: upload firmware using SWD pins on a Raspberry Pi (doesn't require rebooting the Pico)
- `make upload-remote`: building locally and send the file to a remote Raspberry Pi. It the remote Raspberry Pi is running `tools/upload_server.py`, it'll receive the firmware file and upload it to the Pico using SWD. Requires setting the environment variable `$REMOTE_IP` on the client.
- `make talk`: open a serial terminal to talk to the Pi. Requires `screen` installed.
