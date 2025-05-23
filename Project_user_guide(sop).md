## **User Guide / How to Use**

This section provides step-by-step instructions for installing, configuring, and using the migrated PLC system. It is intended for automation engineers and maintenance teams responsible for system startup and operation.

### **Installation Steps**

- **Hardware Installation**
    - Power off all existing control panels before replacement.
    - Replace Siemens **S7-300 CPUs** with corresponding **S7-1500 CPUs** in each line’s PLC cabinet.
    - Install **CM PTP communication modules** to replace legacy CP Lean modules for external communication.
    - Reconnect all I/O wiring to the new S7-1500-compatible I/O modules.
    - Ensure grounding and shielding are correctly maintained to avoid electrical noise.

- **Software Installation**
    - Install **TIA Portal V19** on your engineering workstation.
    - Import the project file for the respective production line.
    - Configure device settings and hardware configuration for the new S7-1500 CPUs and communication modules.
    - Download the program to the PLC using Ethernet/Profinet connection.

### **Setup / Configuration Instructions**

- **Drive Configuration (If Applicable)**
    - Restore saved **drive parameter backups**, especially home position and tuning values.
    - Test axis movements manually before enabling full automation.

- **Model Selection (AC Cowl)**
    - Open the HMI or PLC control panel (if HMI is available).
    - Select **Model Type** (AC Cowl or Standard) via a selection input or toggle switch.
    - The PLC will automatically execute the model-specific logic for clamping and transfer sequences.

- **Communication Setup**
    - Ensure all **CM PTP modules** are configured with correct communication parameters.
    - Confirm handshake signals are properly exchanged between lines using diagnostics or LED indicators.

- **System Start-Up**
    1. Power ON the control panel and PLC system.
    2. Verify the PLC enters **RUN mode** and no diagnostic errors are shown.
    3. On each line:
        - Confirm **Auto Mode** is selected.
        - Reset any active alarms or faults using the reset button or HMI.
        - Press the **Authentication Push Button** to initiate the line (Main Framing Line only).
    4. Monitor station status via HMI or Andon board indicators:
        - **Work Complete** – Operation completed at station
        - **Safety OK** – All safety checks passed
        - **Auto Mode ON** – Line is ready for automatic operation

- **Usage Example – Front Wall Line**
    - Select Auto Mode via toggle or HMI.
    - Load part at Station 1 and initiate the sequence.
    - Observe clamping, operation, and shuttle movement to the next station.
    - After all 8 stations are completed, the part is automatically transferred to the Sub-Structure Line.

- **Safety Notes**
    - Always ensure **E-stop circuits** and safety sensors are functioning before operation.
    - Perform periodic testing of clamp sensors and robot handshake signals.
    - In case of PLC fault, review error codes on TIA Portal or use onboard diagnostics display.
