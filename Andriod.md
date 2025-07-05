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

| Feature                                 | Safety-Critical, Non-Complex Application           | Non-Safety-Critical, Complex Application        |
|-----------------------------------------|----------------------------------------------------|--------------------------------------------------|
| **Risk Level**                          | Failure can be dangerous to human life             | Failure does not cause harm                      |
| **Functionality Requirement**           | Performs critical jobs                             | Can tolerate delay or failure                    |
| **Scheduling**                          | Requires deterministic scheduling                  | No need for deterministic scheduling             |
| **User Interaction**                    | Minimal user interaction                           | User needs to interact with the system           |
| **System Complexity**                   | Internally handles tasks with simple logic         | Can involve more complex behavior, but not critical |
| **Operating System**                    | Runs on FreeRTOS or Baremetal                      | Runs on Linux, Android, etc.                     |
| **CPU Requirements**                    | Simple, efficient processor                        | No need for high-end CPU                         |


