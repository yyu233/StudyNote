## Shield State in MegaRAID Management Software ##

Physical devices in MegaRAID firmware transit between different states. If the firmware detects defects on the physcial devices, it transitions the physical device into a FAILURE or UNCONFIGURED BAD state.

The shield state is an intermediate state before the firmware transition the physical device into a bad state. It allows for diagnostics operations. If any tests fails, the physical device will transit into a bad state.
