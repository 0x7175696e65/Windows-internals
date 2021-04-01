One of the most important concepts in windows is the concept of a process, so it's essential to understand the internals of a process to get into a deeper understanding of windows architecture.

→ What is a process ?

A process is sort of a management object that contains the necessary resources to execute a program. A process doesn't actually run, a thread does.

A process is really a container of various data structures that provides threads the ability to execute code.

A process consists of the following:

- A private virtual address space - basically the address space where memory is allocated
- An executable file - referred to as an image file, which resides on disk and contains the initial code and data to be executed
- A private tables of handles to various kernel objects - For example:

    If we open a file, we use an API such as the Createfile function, and if successful it returns a handle. 

    A handle is simply a number that is  b stored in the private table of handles of the parent process. This means that this handle cannot be used automatically by another process, which kind of provides a boundary as it "prevents" at least it tries to prevent any bad stuff from happening to other processes. So if some process has a bad pointer or instruction code, and it causes it to crash, it won't crash other processes it will just affect it's own.

- Security context - Another thing a process contains is a security context AKA access token, which is used for security checks when accessing shared resources.
- Threads - This is the most important part of a process as it's actually the real part that executes code. For example, when creating a process in user mode, a thread is always created within the process.

→ Viewing processes basics:

- Task Manager

    In windows we have an app called Task Manager where we can check processes and CPU usage including time spent in kernel mode. 

- Process Explorer

    We also have process explorer which is a more advanced version of task manager. process explorer have a lot of interesting features, for example:

    We have colors that differentiate the processes through colors, the default colors are the following:

    - Green - New Objects
    - Red - Deleted Objects
    - Pink - Services
    - Light Purple - Own Processes
    - Purple -
    - Yellow - .Net Processes
    - Yellow - Relocated DLL's
    - Blue - Immersive Process
    - Silver - Graph background

    We can make changes to the colors, and it's recommended to change them to colors that we are comfortable with.
