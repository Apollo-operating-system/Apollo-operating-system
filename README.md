# Apollo-OS Architecture


## Architecture
- **CPU Support**: x86_64 and ARM64
- **Tasking**: Preemptive multi-tasking
- **Memory**: Identity-mapped single address space
- **Networking**: networked 
- **Kernel Model**: Dual-core synchronized kernels ("Stolas" & "Blitzø")



## Kernel Workflow


### **Ring 0: Stolas** (Core 0 | Primary Kernel)

**Ring 0A:**

1. System bootstrap & hardware enumeration
2. Scheduler initialization
3. Physical memory manager bring-up
4. I/O abstraction layer

**Ring 0B:**

5. Network stack initialization
6. Filesystem mounting
7. Security subsystem 
8. Interrupt controller configuration

**Ring 0C:**

9. Syscall interface design
10. Resource monitoring daemon
11. Distributed error logging system
12. Blitzø kernel handoff protocol


### **Ring 0: Blitzø** (Core 1 | Hardware Kernel)

**Ring 0A:**

1. GAIOIR (Graphics/Audio I/O IR) driver JIT compilation
2. Dynamic hardware configuration profiling
3. Priority-driven driver activation sequence

**Ring 0B:**

4. Software-defined I/O pipelines
5. Interrupt-driven event system
6. Kernel-level hardware telemetry


## Driver Model

Apollo drivers utilize just-in-time compilation of our GAIOIR intermediate representation - a unified abstraction layer that transpiles to vendor-specific GPU, audio, and I/O instructions. This enables hardware-agnostic driver development.