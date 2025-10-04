Services in Windows are programs that run in the background, performing specific tasks. These tasks can include system startup, network connections, printing, or updates. Services start and stop automatically without requiring user intervention.

Processes are instances of programs or tasks initiated by the system. Each process uses a certain amount of CPU, memory, and other system resources. Processes can be viewed and terminated in Task Manager.


## Managing services and process
There are multiple application you can use to manage services and process like:
- Task Manager
- Sysinternals
- Process Explorer
- Autoruns
- DiskMon

### Task Manager
Task Manager is a tool in the Windows operating system that allows users to monitor and manage running applications, processes, services, and performance. Task Manager is used to check the computer's performance, terminate applications, monitor processes, and track system resource usage (CPU, memory, disk, network).

Task Manager can typically be accessed by right-clicking the Taskbar or the Start Menu or quickly opened by pressing `Ctrl + Shift + Esc` on the keyboard.

![](https://storage.hackviser.com/file/hackviser-prod/trainings/sections/images/e1be5281-62bc-43a6-afbe-08f19de70f1b/taskmgr-1cef05598.webp)

You will find multiple tabs in it:
- **Processes**: Lists all processes running on your computer. Each process represents a program or service being executed in the computer's memory. This tab allows you to terminate a process or view more information about it.
- **Performance**: Provides graphs and statistics showing the performance of your computer. It is used to monitor CPU, memory, disk, and network usage. This tab can help identify how system resources are being used and diagnose performance issues.
- **App History**: Shows the history of applications used and their resource consumption. It can be used to see how much resources specific applications have used and which applications are used the most.
- **Startup**: Lists programs that automatically start when your computer boots up. This tab can be used to manage startup programs and prevent unwanted programs from starting automatically.
- **Users**: Lists currently logged-in users. This information is displayed when multiple users are logged in or when a user leaves their session open.
- **Details**: Provides a more detailed view of the Processes tab. It shows additional information, including username, CPU usage, memory usage, etc., for each process.
- **Services**: Lists services. Each service is a background program performing a specific function. This tab allows you to stop, start, or configure services.
- **Resource Monitor**: it is a handy tool for identifying and resolving performance issues on a computer. For example, if you notice an application consuming excess CPU or memory, you can identify and terminate it using Resource Monitor if necessary. It can also be used to identify and resolve disk or network performance issues.

### Sysinternals
Sysinternals was founded in 1996 by Mark Russinovich and Bryce Cogswell as a website offering free utilities. then Microsoft acquired the entire project in 2006. Today, Sysinternals remains a free resource offered by Microsoft, providing a powerful suite of tools for IT professionals and developers.
Sysinternals offers numerous free tools that can help you diagnose issues, optimize performance, and gain deeper insights into how your system operates.

### Process Explorer
it shows you information about which handles and DLLs processes have opened or loaded.

The display consists of two sub-windows. The top window always shows a list of the currently active processes, including the names of their owning accounts.

Information displayed in the bottom window depends on Process Explorer's mode: when in handle mode, you will see the handles that the process selected in the top window has opened; when in DLL mode, you will see the DLLs and memory-mapped files that the process has loaded.

### Autoruns
Autoruns is used to view and manage applications, services, codecs, and other startup items that start automatically.

## DiskMon
DiskMon is a tool designed to monitor and display all disk activity on your Windows system. It shows detailed information about the disk, such as read/write operations, sector, length, etc.

