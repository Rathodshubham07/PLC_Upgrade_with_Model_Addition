## **Challenges Faced**

During the hardware and software migration project, several challenges were encountered. These required careful analysis and solutions to ensure a successful upgrade without disrupting production.

- **Communication Module Incompatibility**
    - **Problem:** The existing CP Lean communication modules used for interfacing with the Andon board were not supported by the new Siemens S7-1500 CPUs.
    - **Solution:** The legacy communication modules were replaced with **CM PTP modules**, which are compatible with the S7-1500 platform. This required reconfiguration of communication parameters and validation of data exchange between PLCs and external devices.

- **Loss of Drive Configuration**
    - **Problem:** During the migration of the Front Wall Line, drive parameter values, including home positions, were lost, leading to incorrect motion behavior.
    - **Solution:** A robust backup and restore procedure for drive parameters was implemented. Special attention was given to saving and reapplying home position values before the final commissioning.

- **Limited Testing Time**
    - **Problem:** The production lines had restricted downtime windows, limiting the time available for thorough testing and validation after migration.
    - **Solution:** Testing was meticulously planned in stages, with offline simulation and dry runs conducted prior to live commissioning. Critical tests were prioritized, and after-hours shifts were used to maximize test coverage.

- **Synchronization Between Lines**
    - **Problem:** Ensuring seamless communication and synchronization between three upgraded production lines posed a challenge due to timing and protocol differences.
    - **Solution:** Handshake logic was carefully designed and extensively tested using the CM PTP communication modules. Additional diagnostics were implemented to monitor inter-line status in real time.

- **Integration of Model Addition**
    - **Problem:** Incorporating the new AC Cowl model into the existing PLC logic without impacting standard model operations required flexible and modular programming.
    - **Solution:** The logic was restructured using conditional blocks and reusable function blocks, allowing the system to dynamically switch between standard and AC Cowl model sequences.
