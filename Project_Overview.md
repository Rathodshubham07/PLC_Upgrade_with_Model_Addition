# PLC_Upgrade_with_Model_Addition
Migration of Siemens PLCs from S7-300 to S7-1500 across three production lines (Front Wall, Sub-Structure, Main Framing). Upgraded software from Simatic Manager to TIA Portal, added model enhancements, and integrated fail-safe and robotic systems for improved performance. 

## **Project Title**

PLC Hardware (S7-300 CPU to S7-1500 CPU) and Software Migration (Simatic Manager SP5.6 to TIA Portal V19) with Model Addition

## **Overview / Abstract**

This project involved the migration of both hardware and software for three production lines over a duration of approximately two months. The migration included upgrading the PLC systems from Siemens S7-300 to S7-1500 CPUs and transitioning the programming environment from Simatic Manager to TIA Portal. Additionally, a model enhancement was implemented to improve system functionality and integration.

The three production lines involved in this project are:

Front Wall Line

Sub-Structure Line

Main Framing Line

- Front Wall Line:
    
    This line consists of 8 stations. Each station performs a specific operation on the part, and once the task is completed, the part is transferred to the next station via a shuttle conveyor. After all 8 operations are completed, the part is transferred to the Sub-Structure Line. A standard (non-failsafe) PLC is used in this line, and the process uses a clamping sequence for part positioning and holding.
    

- Sub-Structure Line:
    
    This line comprises 9 stations. The process begins with assembly of child parts. At Station 5, the completed part from the Front Wall Line is merged with the part in the Sub-Structure Line. The integration continues through the remaining stations, and the final part is then transferred to the Main Framing Line. This line is equipped with a fail-safe CPU, and uses 6 robots along with a clamping sequence similar to the Front Wall Line.
    

- Main Framing Line:
    
    This line contains 15 stations. Here, advanced operations such as welding and polishing are performed. A slat conveyor is used for part movement between stations. The conveyor is operated through authentication push buttons, and only emergency stop (E-stop) and authentication controls are present. This line also uses a standard PLC.
    

All hardware and software components used in the project are from Siemens. The migration ensured smooth integration of all three lines with improved reliability and updated control logic. The system was successfully validated after hardware upgrades, software porting, and testing of the new model functionalities.
