## NMI ## 
In computing, a non-maskable interrupt (NMI) is a hardware interrupt that standard interrupt-masking techniques in the system cannot ignore. It typically occurs to signal attention for non-recoverable hardware errors. (Some NMIs may be masked, but only by using proprietary methods specific to the particular NMI.)

An NMI is often used when response time is critical or when an interrupt should never be disabled during normal system operation. Such uses include reporting non-recoverable hardware errors, system debugging and profiling, and handling of special cases like system resets.

Modern computer architectures typically use NMIs to handle non-recoverable errors which need immediate attention. Therefore, such interrupts should not be masked in the normal operation of the system. These errors include non-recoverable internal system chipset errors, corruption in system memory such as parity and ECC errors, and data corruption detected on system and peripheral buses
