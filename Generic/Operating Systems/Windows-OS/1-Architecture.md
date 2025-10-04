The **Windows OS architecture** is layered and modular. It is designed to balance performance, security, portability, and compatibility. At a high level, it can be broken into **user mode** and **kernel mode**, with subsystems and components inside each.
## 1. **Modes of Operation**
- **User Mode**
	- Runs applications and some system services.
    - Has restricted access to hardware and system resources.
    - If a program crashes, it usually doesn’t affect the whole system.
- **Kernel Mode**
    - Core of the OS.
    - Has unrestricted access to hardware and memory.
    - Drivers, the kernel, and executive services run here.
    - A failure here usually crashes the system (BSOD).

## 2. **Architecture Layers**

### **User Mode Components**
- **Applications** – Software like browsers, editors, etc.
- **Environment Subsystems** – Provide APIs for applications:
    - Win32 subsystem (main one).
    - POSIX / OS/2 (older versions).
- **System Processes** – e.g., `smss.exe`, `csrss.exe`, `winlogon.exe`.
- **User-Mode DLLs** – Expose system APIs (e.g., `kernel32.dll`, `user32.dll`, `gdi32.dll`).

### **Kernel Mode Components**
- **Executive** – High-level kernel services, including:
    - Process & thread manager
    - Memory manager (virtual memory, paging)
    - I/O manager (handles I/O requests through IRPs)
    - Object manager (unified namespace for system resources)
    - Security reference monitor (enforces security)
    - Cache manager (file system cache)

- **Kernel** – Low-level code for thread scheduling, interrupts, synchronization.
- **HAL (Hardware Abstraction Layer)** – Abstracts hardware differences so Windows can run on different processors/platforms.
- **Device Drivers** – Software interface to hardware. Includes file system drivers, display drivers, network drivers, etc.
## 3. **I/O System**

- Based on a layered driver model.
- All I/O requests use **I/O Request Packets (IRPs)**.
- Supports Plug and Play (PnP) and Power Management.

## 4. **File Systems**

- Commonly **NTFS** (default).
- Others supported: FAT, exFAT, ReFS, etc.

---

## 5. **Security**

- Built around **Access Tokens**, **ACLs (Access Control Lists)**, and the **Security Reference Monitor**.
- Supports User Account Control (UAC), Kerberos, BitLocker, etc.

---

## 6. **Diagram (Simplified)**

``` md
+-------------------------------+
|       User Applications       | 
+-------------------------------+
|   User Mode Subsystems (Win32)|
+-------------------------------+ 
|    System DLLs (kernel32, …)  | 
+-------------------------------+ 
|          Executive            | 
|   - I/O Manager               | 
|   - Memory Manager            | 
|   - Process Manager           | 
|   - Object Manager            | 
|   - Security Reference Monitor| 
+-------------------------------+ 
|           Kernel              | 
|   (Scheduling, Interrupts)    | 
+-------------------------------+ 
|   Hardware Abstraction Layer  | 
+-------------------------------+ 
|         Hardware              | 
+-------------------------------+
```

