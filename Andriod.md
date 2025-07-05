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

For any General OS stack for Embedded System

+-----------------------------+
|   Your Custom Layers        |  ← Your own apps, configs, and board support  
|   (meta-myproject, etc.)    |
+-----------------------------+
| Community/Third-Party Layers|  ← meta-raspberrypi, meta-qt5, etc.
+-----------------------------+
|           Poky              |  ← Reference distro (includes BitBake + metadata)
+-----------------------------+
|       BitBake Engine        |  ← Executes tasks using recipes
+-----------------------------+
|     OpenEmbedded Core       |  ← Shared base recipes, classes, configs
+-----------------------------+
|   Source Code / Packages    |  ← Kernel, BusyBox, toolchain, libraries
+-----------------------------+


