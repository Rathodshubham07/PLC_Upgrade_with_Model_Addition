This section outlines the systematic approach used to test the hardware migration, software logic, communication interfaces, and model functionality after implementing the upgraded PLC systems.

- **Test Cases**
    
    
    | **Test Case** | **Description** | **Expected Result** | **Status** |
    | --- | --- | --- | --- |
    | TC01 | Power-up & CPU Initialization | All CPUs boot without errors and enter RUN mode | ✅ Passed |
    | TC02 | Station-wise Clamping Sequence | Each station performs correct clamp/unclamp operations | ✅ Passed |
    | TC03 | Shuttle Conveyor Movement | Shuttle moves accurately to the next station on signal | ✅ Passed |
    | TC04 | Inter-line Transfer | Proper handshake between Front Wall → Sub-Structure and Sub-Structure → Main Framing | ✅ Passed |
    | TC05 | Robot Interface | Robots respond correctly to signals (Ready, Done, Fault) | ✅ Passed |
    | TC06 | Emergency Stop | E-stop triggers stop conveyor/robot and disables Auto mode | ✅ Passed |
    | TC07 | Model Identification Logic | AC Cowl model triggers correct conditional logic | ✅ Passed |
    | TC08 | Andon Board Signals | Indicators update status in real-time (Work Complete, Safety OK, etc.) | ✅ Passed |
    | TC09 | Fault Handling | System enters safe state on sensor or sequence failure | ✅ Passed |
    | TC10 | Communication Modules | CM PTP modules send/receive data between CPUs | ✅ Passed |

- **Tools Used for Testing**
    - **TIA Portal V19**: For live monitoring, force-testing I/O, and observing program execution.
    - **Multimeter**: To verify signal continuity and voltage levels at I/O terminals.
    - **Drive Commissioning Tool (if applicable)**: Used to verify restored drive parameters and homing functions.
    - **Simulation Mode (TIA Portal)**: Used for pre-deployment testing of logic sequences before physical download.
    - **Manual Test Jig / Station Simulation**: Used to simulate input conditions and trigger station-wise logic manually.

- **Testing Process**
    1. **Dry Run Testing**: Performed with mechanical systems disabled. Input signals were forced to test the logic flow, interlocks, and output responses.
    2. **Live Commissioning**: Gradually enabled motors, clamps, and robots one by one while observing safety and logic behavior.
    3. **Line Synchronization**: Verified the timing and coordination of handshakes between lines to ensure seamless part transfer.
    4. **Safety Validation**: Tested E-stop circuits, safety sensors, and fail-safe PLC behavior (Sub-Structure Line).
    5. **Model-based Testing**: Switched between standard and AC Cowl models and validated station-level changes.

- **Results**
    - **All test cases passed successfully** with expected results.
    - **Drive configuration issue** encountered during the Front Wall Line migration was resolved by restoring saved parameters.
    - Communication issues due to incompatible modules were eliminated after replacing CP Lean with CM PTP.
    - Final validation confirmed stable operation across all three lines, including model handling and inter-line coordination.
