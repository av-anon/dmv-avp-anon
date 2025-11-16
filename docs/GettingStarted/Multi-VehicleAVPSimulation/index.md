# Multi-Vehicle AVP Simulation

## Prerequisites
Ensure the following components are set up on each host:

- **Host 1**:

    - AWSIM Labs simulation (Unity-based)
    - YOLOv5-based parking spot detection server
    - Autoware (vehicle 1 stack)
    - AVP orchestration node (with **manager nodes** enabled)
    - Zenoh Bridge (in router mode)

- **Host 2**:

    - Autoware (vehicle 2 stack, with `/vehicle2` namespace)
    - A second AVP orchestration node (**no managers**, namespace-aware)
    - Zenoh Bridge (in client mode)

---

## Launch Sequence
Follow the steps below to launch all components required for the simulation.

1. **Launching the DMAVA**

    Follow the [Multi-Vehicle Simulation](https://av-anon.github.io/dmv-avp-anon/GettingStarted/Multi-VehicleSimulation) section in the DMAVA docs.

2. **Start U-YOLO**

    **Host 1**

    Go to Tab 1, split the terminal horizontally, and run the following commands in the bottom pane:

    ```bash
    source ~/dmv-avp-anon/yolo_detection_server/venv/bin/activate
    python3 yolo_server.py
    ```
    
3. **Start the AVP Module**

    **Host 1**

    ```bash
    source /opt/ros/humble/setup.bash
    source ~/autoware/install/setup.bash
    source ~/dmv-avp-anon/multi_vehicle_avp/install/setup.bash
    ros2 launch avp_node multi_avp_launch.py vehicle_id:=1 enable_managers:=true namespaces:="['vehicle2']"
    ```
    > See [] for explanation of arguments.

    **Host 2**

    ```bash
    source /opt/ros/humble/setup.bash
    source ~/autoware/install/setup.bash
    source ~/dmv-avp-anon/multi_vehicle_avp/install/setup.bash
    ros2 launch avp_node multi_avp_launch.py vehicle_id:=2
    ```

## Multi-Vehicle AVP Demonstration

[Demo](https://drive.google.com/file/d/1N4-syknWXr84Mb6QjW1Psg_lEWWAnxMf/view?usp=drive_link)

---

**Next Steps:** To scale this setup beyond two vehicles, see [Scaling to More Vehicles](../../Scalability/ScalingToMoreVehicles/index.md). 