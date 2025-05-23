## **Objectives / Goals**

### **Project Goals:**

1. **Migration of Hardware and Software:**
    - Upgrade PLC CPUs from **Siemens S7-300** to **S7-1500** in all three production lines:
        - Front Wall Line
        - Sub-Structure Line
        - Main Framing Line
    - Migrate the control software from **Simatic Manager SP5.6** to **TIA Portal V19**.
2. **Communication Module Replacement:**
    - Replace the legacy **CP Lean** communication modules with **CM PTP** modules to ensure compatibility with the new S7-1500 CPUs.
3. **Model Addition:**
    - Integrate the **AC Cowl model** functionality across all three lines (Front Wall, Sub-Structure, and Main Framing) to enhance production capabilities.

### **Challenges Faced:**

1. **Communication Module Incompatibility:**
    
    The existing communication module used for the Andon board was not compatible with the new S7-1500 CPU, requiring a change to a supported module.
    
2. **Loss of Drive Configuration:**
    
    During the migration of the Front Wall Line, drive parameter values were lost. To prevent this in future migrations, special attention was given to saving and restoring home position values.
    
3. **Limited Testing Time:**
    
    There was insufficient downtime allocated for thorough testing, which created constraints in validating the complete system functionality post-migration.
