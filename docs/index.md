# Distributed Multi-Vehicle AVP System (DMV-AVP) 
*Distributed Autonomous Valet Parking Across Multiple Hosts*

![Autoware](https://img.shields.io/badge/Autoware-2024.11-blue?logo=autoware)
![AWSIM Labs](https://img.shields.io/badge/AWSIM%20Labs-Unity-green?logo=unity)
![ROS 2 Humble](https://img.shields.io/badge/ROS2-Humble-purple?logo=ros)
![Zenoh](https://img.shields.io/badge/Zenoh-1.4.0-orange?logo=zenoh)
![YOLOv5](https://img.shields.io/badge/YOLO-v5-red?logo=github)
![AVP Node](https://img.shields.io/badge/AVP_Node-custom-black?logo=robotframework)
![License](https://img.shields.io/badge/License-Apache%202.0-blue?logo=apache)

The **DMV-AVP System** extends the [**Distributed Multi-AV Architecture (DMAVA)**](https://github.com/av-anon/dmava-anon) to support **coordinated autonomous parking across multiple vehicles and physical hosts** using **Autoware Universe**, **AWSIM Labs**, and **Zenoh**.  

It integrates the **Unity-Integrated YOLOv5 Parking Spot Detection Module (U-YOLO)** for parking-spot detection and the **Multi-Vehicle AVP Node** for orchestration, queuing, and reservation management. Together, these components enable **real-time distributed coordination**, **synchronized planning**, and **conflict-free multi-vehicle parking behavior**.

---

## Features

- Multi-host, multi-vehicle AVP simulation
- Zenoh-based distributed ROS 2 topic bridging for synchronized operation
- Parking spot detection and reservation mechanisms
- Namespace-aware orchestration for individual Autoware stacks
- Custom RViz panel for streamlined AVP testing and monitoring
- Scalable to larger fleets and more complex simulation scenarios

---

## Getting Started

To get started with running the DMV-AVP System, see the [System Architecture](GettingStarted/SystemArchitecture/index.md) page.

For a condensed list of frequently used commands, refer to the [Developer Quick Commands](DeveloperGuide/QuickCommands/index.md) page.  