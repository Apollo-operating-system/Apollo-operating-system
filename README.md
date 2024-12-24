# apollo-OS Architecture Overview

## Architecture

- **CPU Architecture:** X86_64 and ARM64
- **Tasking:** Multi-tasking
- **Cored:** Multi-cored
- **Memory Map:** Single-address-map (identity-mapped)
- **Networking:** Networked
- **Type:** PC operating system

## Ring 0: Adam (Kernel)

1. System Bootstraps
2. Starts scheduler
3. Starts memory manager
4. Starts I/O manager
5. Initializing Device Drivers
6. Starts Network Stack
7. Mounting Filesystems
8. Start Security Services
9. Initializes Interrupt Handling
10. Configure System Calls
11. Initializes Resource Management
12. Starts Error Handling & Logging

## Ring 1: Device Drivers

- Some kernel bypass for efficiency

## Ring 2: Built-in Applications and GUI

- Apps that are part of the OS and user input handling

## Ring 2.5: Third-Party Code

- Any third-party applications and code

## Ring 3: Untrusted Mode

- Apps running in an untrusted environment