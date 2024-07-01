# In-band control and command and VLAN management

CP9000 implements in-band C\&C management on both streaming interfaces Eth1 and Eth2. VLAN management is possible on one of the streaming interfaces Eth1 and Eth2 if in-band C\&C is enabled.

These features are available via commands under user TST shell and allow to :

* Use the same network interface for the service streams and the management contol streams.
* Use VLAN tagging to tag the streaming and management traffic with different VLANs .
* Use simultaneously the default management port for local and remote control access as GUI, RestAPI and SNMP

**Restriction:** When in-band C\&C is enabled Geo Redundancy and Internal redundancy are not possible.

* **List of commands**
* **In-band C\&C Management**
* **VLAN Management**
* **Use cases summary**

**Parent topic:**Servicing
