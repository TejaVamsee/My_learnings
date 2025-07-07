# Andriod
## Indroduction about Embedded System

An embedded system is a combination of hardware and software designed to perform a specific task or function.

```
 Why Embedded System?
 - Embedded systems will use only the necessary components for the task.By this it will improve efficiency and cost efficient.
 - It typically small and compact devices.Making ideal for any industry.
 - Embedded Systems consumes less power compared to General purpose systems. 
```

```
Is phone a completely embedded system?
- No, Phone is not a purely embedded system, but a complex computing device that integrates multiple embedded systems.
- Multiple Embedded sytems means Camera Module,Display Module,Fingerprint sensor...
```
## Classification of Embedded systems in terms of Safety

| Feature            | Safety-Critical (Non-Complex)      | Non-Safety-Critical (Complex)    |
|--------------------|------------------------------------|----------------------------------|
| **Risk**           | Failure may harm human life        | Failure causes no harm           |
| **Functionality**  | Performs essential tasks           | Non-critical tasks               |
| **Scheduling**     | Needs deterministic timing         | Not time-sensitive               |
| **User Input**     | Minimal interaction                | User-driven actions              |
| **Complexity**     | Internally simple logic            | More complex but safe            |
| **OS Type**        | FreeRTOS / Baremetal               | Linux / Android                  |
| **CPU Need**       | Simple processor                   | No high-end CPU required         |

## For any General OS stack for Embedded System
```
+-----------------------------+
|                             |  ← It is user interface(provides functionality to the user) 
|      Applications           |
|                             |         
+-----------------------------+
|                             |
|        Services             |   ← What services/options does the mmodule provides
|                             |   ← Ex: Camera module is used for photo and recording.
+-----------------------------+
|                             |
|        Libraries            |  ← It is a programs responsible for the task you want to perform 
|                             |   
+-----------------------------+
|                             |
|    System Call Interface    |  ← Bridge between the userspace and kernal space
+-----------------------------+
|                             |
|        Drivers              |  ← It is a software code in kernal space used to interact with the hardware 
|                             | 
+-----------------------------+
|                             |
|       Linux Kernal          |  ← It is the OS which manages everything like memory,device files and it interacts with hardware
|                             | 
+-----------------------------+

```
## Note:
<img src="/Andriod/1.png" alt="Embedded System" width="400"/>

A embedded system means we should not only customize the hardware but also to customize the software of user interface.

## Building of Android OS


### Build System
A build system is a set of tools, configuration files, and rules used to automate the process of transforming source code into a final executable program.

### Build Engine
A build engine is the part of the system that actually executes the build instructions with the help of tootal chain.

Ex: lets us assume a Function, function declaration will be Build engine and function defination will be Build Engine
```
         ## Inputs                                                                                ## Outputs 
+-----------------------------+            +-------------+                                    
|                             |            |             |                                    --> RoofFs Images
|      Andriod Source code    |            |             |            +-------------+         --> Kernal Images
|                             |            |  Build      |            |             |
+-----------------------------+            |  Engine     |            |             |          
|                             |            |( Bitbake/task |          |             |         --> Bootloader Images
|    BootLoader Source Code   |    ------> |  Executer)  | ------->   |  Toolchain  |         
|                             |            |  Build      |            |  ( gcc )    |
+-----------------------------+            |  System     |            |             |
|                             |            |(Yocto/Make) |            +-------------+         
|       BootROM Firmware      |            |             |                                    --> BootRAM firmware
|     ( Executable file )     |            |             |
+-----------------------------+            +-------------+             
|                             |                                   
|    Additional Chip Firware  |                                                               --> Additional Chip
|    ( Bluuetooth,WIFI)       |                                                                     Firmware
+-----------------------------+                      
```
- The build system converts the source file/code to executable or Images or Firmware.
- After generating the images or firmware it will be flashed into development board.
- BootRom firmware is flased to BootROM
- Additional Firmware is flased to Additional Chip Firmware.

## Difference between the Andriod and Linux Operating System.

### 1. Bionic C
- In andriod we use Bionic C .(It is a customized C standard library developed by Google)
- It is light weight.Glibc is large Bionic is lean, smaller in size & faster to load.
- It is designed for limited CPU memory & power usage.

### 2. Completely Fair Scheduling (CFS)
    - In linux we generally se Round Rbbin or Priority based Scheduling.
    - In CFS the task will be run on Virtual runtime.
    - It follows red-black tree Algorithm.
       - Leftmost node always has smaller vruntime.
#### Step:1
  - Cpu based on the priority or critical code of the process it will assigned the nice value to the processes.
  - Nice value (-20 to 19) - it is not fixed
     - (-20) -> Higher Priorty
     - 19 -> lowest priority
#### Step:2
 - CFS depends on Vruntime manner.
 - Vruntime = CPU_time * weight
 - Lowest Vruntime will have more CPU time.
 - Based on Nice value there will be a weight to it.
   
#### Step:3 
 Lets take an Example 

 |            |   Nice Value  |     Weight |
 |------------|---------------|------------|
 | **Task A** |        0      |     1.0    |
 | **Task B** |       -5      |     0.8    |
 | **Task C** |       +5      |     1.25   |

- Whenever a new process will created initially it will have lesser runtime.The cpu will run until it will match with other process.
- Until then it will always be a left most in the tree.

### 3.Low Memory Killer
- When Andriod system detects that available RAM is running Low.It will trigger LOW MEMORY KILLER(LMK)
- It checks the enough memory for important operations based on priority score.
- The lower priority tasks will be terminated.

#### Out of Memory Score(priority Score)
- Foreground process
- Background process
- Cached process

Linux uses OOM killer(Out of Memory)
- It comes into picture where the system runs when it is completely out of memory.
- It free up the memory

### 4.Sleep prone Kernal
- When you click the lock button the phone will be off.The kernal will enter into Sleep Mode/you can even suspend it.
- It will also happen in linux but it is less utilized.

### 5. WakeLocks
- You can wake the process/task from Suspended to perform the critical code.
- It is mechanism that allows an app/service to keep the device awake- either keeping CPU running, screen on when the user is not interacting.
Ex: 
   - playing music when screen turn off
   - Tracking GPS in fitness app.

### 6.Binder IPC
- linux uses the System V IPC like message queues,named pipes...
- It is a Remote procedure call based communication.It creates the server-client mechanism between the process.

### 7. Hardware Abstraction Layer
- Proper usage of hardware Abstraction is done in Andriod i.e. usage of kernal resources.
- Whereas in Linux you dont have much access/Much usage of hardware Layer.

 ### 8. Loging Mechanism
 - In Linux we use dmseg to see the kernal logs, journalctl for service logs.
 - In andriod we use dmesg to see the kernal logs, logcat for service logs.It uses circular buffer for writing the logs.

# Example of Linux Archietecture
