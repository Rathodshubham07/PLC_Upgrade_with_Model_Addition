## **Scope**

- **In Scope**
    1. **Hardware Migration:**
        - Replacement of existing Siemens **S7-300 CPUs** with **S7-1500 CPUs** across three production lines:
            - Front Wall Line
            - Sub-Structure Line
            - Main Framing Line
    2. **Software Migration:**
        - Transition of the control logic and programs from **Simatic Manager SP5.6** to **TIA Portal V19**.
        - Re-creation or adaptation of all existing PLC logic, including clamping sequences, conveyor control, robot interfaces, and interlocks.
    3. **Communication Module Upgrade:**
        - Replacement of obsolete **CP Lean** modules with compatible **CM PTP** modules to support communication between PLCs and external devices (e.g., Andon board).
    4. **Model Addition:**
        - Integration of the **AC Cowl model** in all three lines, involving necessary PLC logic updates and synchronization between lines.
    5. **System Validation and Testing:**
        - Functional testing of all stations and processes after migration to ensure proper operation.
        - Verification of inter-line communication and synchronization, especially the part transfer between lines.
- **Out of Scope:**
    1. **HMI/SCADA Upgrades:**
        - No changes or upgrades were performed on any existing HMI or SCADA systems, unless directly related to PLC migration.
    2. **Mechanical Modifications:**
        - Mechanical structure or tooling modifications at stations were not part of this project scope.
    3. **Network Infrastructure:**
        - No major rework of the plant’s overall network infrastructure was included, apart from the communication module changes.
    4. **Operator Training:**
        - Operator or production staff training on the new system was not formally included in this phase of the project.

### **Tools & Technologies Used**

The execution of this migration project involved a robust combination of Siemens hardware and software platforms, supported by essential automation technologies to ensure seamless system integration and performance.

- **Hardware:**
    - **Siemens S7-1500 PLCs**Deployed across all production lines to replace legacy S7-300 CPUs, offering enhanced processing capabilities, advanced diagnostics, and integrated communication features.
    - **Siemens S7-300 PLCs** *(Legacy – Replaced)*Phased out during the upgrade. These were originally used to control each production line.
    - **Siemens CM PTP Communication Modules**Installed in place of outdated CP Lean modules to facilitate reliable point-to-point communication between the PLCs and external systems like the Andon board.
    - **Standard and Fail-Safe I/O Modules**Utilized for interfacing with sensors, actuators, safety devices, and field components across all stations.
    - **Drive Systems**Used for shuttle and conveyor movement; configurations were carefully backed up and restored to retain critical motion parameters, including home positions.
- **Software:**
    - **TIA Portal V19**Siemens’ Totally Integrated Automation Portal was used as the central engineering platform for programming, configuring, and commissioning the upgraded S7-1500 CPUs.
    - **Simatic Manager SP5.6** *(Legacy – Replaced)*Previously used for developing and maintaining the S7-300 PLC programs.
- **Other Technologies:**
    - **Clamping Sequence Control**Implemented in all three lines to ensure proper part positioning and secure holding during operations.
    - **Robot Integration**Especially in the Sub-Structure Line, six industrial robots were integrated with the PLC system for coordinated assembly tasks.
    - **Shuttle and Slat Conveyors**Used for part transfer between stations and lines. Conveyor movement was synchronized with PLC logic and safeguarded by interlocks and E-stop systems.
    - **Authentication-Based Push Button Controls**Deployed in the Main Framing Line for secure control of conveyor operations, allowing only authorized personnel to initiate or stop movement.
    - **Andon Board Indication System**Visual feedback system used for real-time monitoring of line status. Lamps on the Andon board indicate:
        - **Work Complete** status
        - **Safety OK** status
        - **Home Position** status
        - **Auto Mode** status

Integration with the new CM PTP modules ensured continued communication with the updated PLC hardware.

### **System Architecture / Design**

- **Overview**
    
    This project involved the migration of PLC hardware and software across three production lines—Front Wall Line, Sub-Structure Line, and Main Framing Line. The migration transitioned from Siemens S7-300 CPUs programmed with Simatic Manager SP5.6 to Siemens S7-1500 CPUs utilizing TIA Portal V19. The system architecture was designed to ensure seamless integration, enhanced performance, and improved diagnostics.
    

- **System Architecture Diagram***.*
    - **Central Components:**
    - **Engineering Station:** A PC running TIA Portal V19 used for programming, configuration, and diagnostics.
    - **PLC Units:**
    - **Front Wall Line:** Standard Siemens S7-1500 CPU.
    - **Sub-Structure Line:** Fail-safe Siemens S7-1500F CPU to handle safety-related tasks.
    - **Main Framing Line:** Standard Siemens S7-1500 CPU.
    - **Communication Modules:** Siemens CM PTP modules replacing legacy CP Lean modules to facilitate communication with external devices like the Andon board.
    - **I/O Modules:** Digital and analog I/O modules connected to sensors, actuators, and other field devices.
    - **Drives and Conveyors:** Integrated drive systems controlling shuttle and slat conveyors for part movement between stations.
    - **Robots:** Six-axis industrial robots integrated into the Sub-Structure Line for assembly tasks.
    - **Andon Board:** Visual display system indicating work completion, safety status, home position, and auto mode status using lamps.
    - **Network Topology:**
    - All PLCs and devices are interconnected via an Industrial Ethernet network, ensuring real-time communication and synchronization across the production lines.

- **Module/Component Explanation**
    - **Siemens S7-1500 CPUs:** Offer enhanced processing capabilities, integrated system diagnostics, and improved communication features compared to the legacy S7-300 CPUs.
    - **TIA Portal V19:** Provides a unified engineering framework for programming, configuring, and diagnosing all automation components within the system.
    - **CM PTP Communication Modules:** Enable point-to-point communication between PLCs and external devices, ensuring compatibility and reliable data exchange.
    - **I/O Modules:** Interface with field devices such as sensors and actuators, facilitating data acquisition and control actions.
    - **Drive Systems:** Control the movement of shuttle and slat conveyors, ensuring precise part positioning and transfer between stations.
    - **Robots:** Perform automated assembly tasks, synchronized with PLC logic for efficient operation.
    - **Andon Board:** Provides real-time visual feedback on production status, safety conditions, and operational modes, enhancing operator awareness and response.
- **Database Schema**
    
    This project did not involve the implementation of a centralized database system. All data handling, including process variables, status indicators, and control logic, is managed within the PLCs and the TIA Portal environment.
    

- **Hardware used**
![image.png](attachment:829649fd-917a-431f-89ab-45b5775356c6:image.png)
