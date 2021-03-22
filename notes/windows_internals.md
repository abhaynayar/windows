## Windows Internals
### COM

Windows API -> C -> Lack of logical grouping -> COM
DDE -> OLE -> COM (OLE2)

1. Clients <-> Objects
2. Component implementation is dynamic.

### WinRT

API aimed at metro apps.
Built on top of COM.
Classic apps can use WinRT APIs.
Windows apps can use Win32 and COM APIs.

### .NET

Components:
- CLR: JIT for CIL
- FCL: collection of types

## Services, functions, and routines

- Windows API functions
- Native system services (syscalls)
- Kernel support functions (routines)
- Windows services
- Dynamic link libraries (DLLs)

## Processes

- Virtual address space
- Executable program
- List of open handles
- Security context
- Process ID
- Thread[s]

## Threads

Context:
- Set of CPU registers for the state of the processor.
- Two stacks: user mode and kernel mode.
- Thread-local storage (TLS)

- Thread ID (doesn't overlap with process IDs).
- Security context / token.

## Fibers

- AKA Lightweight threads.
- Used to schedule threads on your own instead of priority-based builtin.
- Invisible to the kernel, implemented in user mode in Kernel32.dll

---

Chapter 2 - System architecture

User-mode processes:
- User processes
- Service processes
- System processes
- Environment subsystem server processes

Kernel-mode components:
- Executive
- The Windows kernel
- Device drivers
- The Hardware Abstraction Layer (HAL)
- The windowing and graphics system
- The hypervisor layer

Core Windows System Files:
- Ntoskrnl.exe
- Hal.dll
- Win32k.sys
- Hvix64.exe (Intel), Hvax64.exe (AMD)
- .sys files in \SystemRoot\System32\Drivers
- Ntdll.dll
- Kernel32.dll, Advapi32.dll, User32.dll, Gdi32.dll

Portability:
- Layered approach
- C instead of assembly

Symmertric multiprocessing:
- No master processor.
- All processor share memory.
- 