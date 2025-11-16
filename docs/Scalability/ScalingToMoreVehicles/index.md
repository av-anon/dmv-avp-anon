# Scaling to More Vehicles

The DMV-AVP System can be extended beyond two vehicles by adding more hosts and namespaces. However, during testing with the available machines, certain issues were encountered that impacted performance.  

Despite these constraints, the DMV-AVP System remained fully operational. Instructions are given below, as well as an example using a third host.

See the [Third Host Example](https://av-anon.github.io/dmv-avp-anon/Scalability/ScalingToMoreVehicles/#third-host-example) in the DMAVA to add another vehicle.

## General Scaling Procedure for AVP

To extend the DMV-AVP System,replicate the following for each additional vehicle/host:

1. **Install the Multi-Vehicle AVP Node** on the new host.  
2. **Assign a unique vehicle ID** for the new vehicle as an argument when launching the node.
3. **Add an extra namespace argument** corresponding to that vehicle ID on the host running the AVP managers.  


---

### Multi-Vehicle AVP Simulation (3 Hosts)

> Removed for anonymity

---

## Discussion

Similarly to the [discussion](https://av-anon.github.io/dmava-anon/Scalability/ScalingToMoreVehicles/#discussion) about the three host simulation of the DMAVA, an issue was observed with the **Victus Laptop**, where the third vehicle did not begin moving immediately. At 3:55 in the video above, when the first vehicle had already parked and the second was close to finishing its parking, the third vehicle finally started driving to the drop-off zone.

Further analysis of memory usage and host performance can be found in the [Benchmarks](../Benchmarks/index.md) section.

