## **Features**

The project delivered several critical features to enhance the performance, reliability, and maintainability of the three production lines. Below are the key features implemented as part of the hardware and software migration:

- **Complete PLC Hardware Upgrade**
    - Migration from Siemens **S7-300 CPUs to S7-1500 CPUs** across all production lines.
    - Improved processing speed, integrated system diagnostics, and enhanced memory handling.
    - Increased support for modern communication protocols and advanced instruction sets.

- **Software Environment Modernization**
    - Transition from **Simatic Manager SP5.6** to **TIA Portal V19**, consolidating hardware configuration, logic development, and diagnostics in a single engineering framework.
    - Better user interface for engineering, faster development, and streamlined commissioning.

- **Model Addition Across Lines**
    - Integration of the **AC Cowl model functionality** into all three production lines.
    - Synchronized logic development ensuring accurate part tracking and process flow across lines.

- **Enhanced Communication Capabilities**
    - Replacement of legacy **CP Lean modules** with **CM PTP modules**, enabling reliable point-to-point communication with external systems such as the Andon board.

- **Line Synchronization and Inter-Line Transfer Logic**
    - Seamless part handoff between:
        - Front Wall Line → Sub-Structure Line
        - Sub-Structure Line → Main Framing Line
    - Inter-line communication logic implemented in TIA Portal to coordinate production flow.

- **Real-Time Status Indication via Andon Board**
    - Visual feedback system integrated through lamps on the Andon board to indicate:
        - Work completion
        - Safety OK / Not OK
        - Home position reached
        - Auto mode ON/OFF
    - Enhances operator awareness and quick decision-making on the shop floor.

- **Fail-Safe Integration for Critical Safety Applications**
    - Implementation of **S7-1500F CPU** in the Sub-Structure Line for safety-related operations.
    - Integration of safety inputs and interlocks to comply with industrial safety standards.

- **Drive Configuration Preservation**
    - Special handling during migration to **retain and restore drive parameters** and home position settings.
    - Reduced commissioning time and minimized risk of misalignment or motor tuning errors.

- **Minimal Downtime During Migration**
    - Careful planning and phased implementation minimized production disruption.
    - Use of modular design and pre-tested configurations enabled faster deployment and validation.

- **Implementation Details**
    
    This section outlines how each hardware and software component was implemented during the PLC and software migration project.
    

- **PLC Program Development**
    - The control logic was recreated in **TIA Portal V19** after analyzing the existing Simatic Manager (S7-300) programs.
    - Modular programming was used with **OBs**, **FBs**, and **DBs** for each station and subsystem.
    - Function blocks were structured for key operations like clamping, conveyor control, robot handshakes, and interlocks.

- **Clamping Sequence Implementation**
    - A standard clamping sequence was developed for every station using ladder logic.
    - The sequence involved part detection, clamp activation, sensor feedback verification, and fault handling if conditions were not met.
    - Status and interlocks were managed through Data Blocks for consistency and monitoring.

- **Conveyor and Shuttle Control**
    - Shuttle conveyors (Front Wall and Sub-Structure Lines) were controlled using directional bit logic and position sensors.
    - The slat conveyor (Main Framing Line) was controlled using authentication push buttons with logic to enable/disable motion based on E-stop and safety conditions.

- **Robot Interface Logic**
    - Robot interaction (Sub-Structure Line) was managed through digital handshakes using dedicated input/output signals.
    - Signals included: Robot Ready, Part Present, Cycle Complete, Fault Status.
    - These signals were mapped to Data Blocks for logic control and HMI interfacing.

- **Inter-Line Transfer Logic**
    - Communication between lines was established using **CM PTP communication modules**.
    - A handshake logic was created to manage part transfers between Front Wall → Sub-Structure and Sub-Structure → Main Framing lines.
    - Signals like Part Ready, Request Transfer, and Transfer Complete were exchanged between CPUs.

- **Model Addition Logic (AC Cowl)**
    - A model flag was introduced in the PLC logic to identify AC Cowl parts.
    - Conditional logic was added to enable additional clamps, sequences, or station-specific actions when the AC Cowl model was active.
    - Model-specific logic was organized into reusable blocks.

- **Error and Safety Handling**
    - Integrated diagnostic logic was implemented for sensor faults, clamp errors, and sequence mismatches.
    - Faults triggered visual indicators and system halts until resolved.
    - The Sub-Structure Line, with a fail-safe CPU, included safety interlocks and emergency logic in compliance with safety standards.

- **Andon Board Integration**
    - The Andon board was interfaced using output bits connected to indicator lamps.
    - Signals included:
        - **Work Complete**
        - **Safety OK / Not OK**
        - **Home Position Reached**
        - **Auto Mode ON/OFF**
    - The logic was designed to update the board in real-time for operator awareness.
