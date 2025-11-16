# Software Setup


This section provides installation steps for each required component in the AVP system, including Autoware, Zenoh, Unity, and the YOLOv5 detection server.

> Refer to [Host Roles](../SystemArchitecture/index.md/#host-roles) to determine where each tool should be installed.

### DMAVA Installation
Follow the **Getting Started** sections in the [DMAVA](https://av-anon.github.io/dmv-avp-anon).

### Repository Cloning

Clone the main repository on **all hosts**.

```bash
cd ~
git clone https://github.com/av-anon/dmv-avp-anon
```

This repository contains:

- The AVP orchestration node
- YOLOv5-based detection server
- Parking Spot Detection Unity code

---


### Unity-Integrated YOLOv5 Parking Spot Detection Module (U-YOLO)

U-YOLO runs locally on the same machine as AWSIM Labs. Its workflow is as follows:

1. Captures frames from the overhead camera in the simulation.  
2. Performs vehicle detection using YOLOv5.  
3. Extracts the bounding box coordinates of detected vehicles.  
4. Sends results back to Unity to draw bounding boxes in the simulation.  
5. Publishes a ROS 2 topic with the list of **empty parking spots** (shown in the bottom-left corner of the image below).  

![image](https://github.com/user-attachments/assets/fd8fad9a-dfba-4936-b6e1-dfc06943eb2d)


#### YOLOv5 Server Installation

Run the following commands to create the virtual environment and install requirements:
```bash
cd ~/dmv-avp-anon/yolo_detection_server 
python3 -m venv venv
source ~/dmv-avp-anon/yolo_detection_server/venv/bin/activate
pip install -r requirements.txt
```

###  Multi-Vehicle AVP Node
The Multi-Vehicle AVP Node is the central control module that coordinates goal assignment, parking logic, and reservation handling across multiple vehicles. Each vehicle is assigned a dedicated AVP node instance, with only one host being assigned manager responsibilities.The node also interfaces with RViz for visualization and command input.

This node must be built and installed on every host running an Autoware stack.

    
#### Setup

Build the Multi-Vehicle AVP Node
```bash
cd ~/dmv-avp-anon/multi_vehicle_avp/
colcon build
```

---

**Next Steps:** Proceed to [Multi-Vehicle AVP Simulation](../Multi-VehicleAVPSimulation/index.md) to start the simulation.