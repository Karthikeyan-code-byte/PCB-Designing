# PCB-Designing
This is my custom pcb design for my smart helmet project where i am using ESP32 as a microcontroller as a brain of the system, MPU6050 accerlerometer + gyroscope monitors real time vibration values, gps module get the real time coordinates of the accident place, alcohol sensor get the alcohol values if the value exceeds the threshold it turns off the engine ignition.
<img width="1401" height="791" alt="Screenshot 2026-05-17 122418" src="https://github.com/user-attachments/assets/c9b80628-d399-490d-b05b-b0bf2207444d" />

as shown in this image we will first do the pcb schematic 

| Component           | Search in KiCad                        |
| ------------------- | -------------------------------------- |
| MPU6050 Connector   | `Conn_01x04`                           |
| LCD (I2C) Connector | `Conn_01x04`                           |
| GPS Connector       | `Conn_01x04`                           |
| MQ3 Connector       | `Conn_01x03`                           |
| Buzzer              | `Buzzer` or `Speaker`                  |
| Relay               | `Conn_01x03` (if using a relay module) |
| USB/Power Input     | `Conn_01x02`                           |
| GND                 | `GND`                                  |
| +5V                 | `+5V`                                  |
| +3.3V               | `+3V3`                                 |

place these in kicad schematic window as shown in the figure below

<img width="876" height="672" alt="Screenshot 2026-06-30 123509" src="https://github.com/user-attachments/assets/10ecd2e6-08f8-40a3-8725-7a08298a5611" />

I used netlabels to link the componenets rather than the traditional circuit line to connect ( press L to open net label), connect the components as shown 
in the figure and for the not connected pins we have to add No connection flag ( press Q or search in componenets box) 
After these step, the next step is assigning the footprints. Assign these footprints as shown in the table below
| Schematic Symbol   | Footprint                                                                      |
| ------------------ | ------------------------------------------------------------------------------ |
| ESP32 Left Header  | `Connector_PinSocket_2.54mm:PinSocket_1x15_P2.54mm_Vertical`                   |
| ESP32 Right Header | `Connector_PinSocket_2.54mm:PinSocket_1x15_P2.54mm_Vertical`                   |
| GPS                | `Connector_PinHeader_2.54mm:PinHeader_1x04_P2.54mm_Vertical`                   |
| MPU6050            | `Connector_PinHeader_2.54mm:PinHeader_1x04_P2.54mm_Vertical`                   |
| LCD                | `Connector_PinHeader_2.54mm:PinHeader_1x04_P2.54mm_Vertical`                   |
| MQ3                | `Connector_PinHeader_2.54mm:PinHeader_1x03_P2.54mm_Vertical`                   |
| Relay              | `Connector_PinHeader_2.54mm:PinHeader_1x03_P2.54mm_Vertical`                   |
| Power Connector    | `Connector_PinHeader_2.54mm:PinHeader_1x02_P2.54mm_Vertical`                   |
| Buzzer             | Choose the footprint that matches your actual buzzer (through-hole or module). |

Then go to pcb editor and update pcb from schematic. Arrange as you wish, i arranged like in the figure below

<img width="332" height="531" alt="image" src="https://github.com/user-attachments/assets/34b16065-f07c-4281-8e64-706e89549d91" />

Then do the routing such that following rules of routing and prefer the 45 degree angle routing. Then add the Ground Plane
look on the right toolbar.Click -> Add Filled Zone (It looks like a small filled polygon). It asks Layer -> Choose F.Cu, Then -> Net Choose GND -> Click OK.

Now draw a rectangle around the entire PCB.

Like this:

┌───────────────────────┐
│                       │
│                       │
│      Whole PCB        │
│                       │
└───────────────────────┘

Double-click to finish.

Nothing may happen immediately.

Press

B

This fills the copper.

Suddenly you'll see almost the whole board become copper.

All GND pads are connected automatically.

<img width="1915" height="981" alt="Screenshot 2026-06-30 123414" src="https://github.com/user-attachments/assets/e334a225-4f1b-4447-a522-5cf4adfa1fbd" />
This is the final design of the custome pcb for smart helmet system

<img width="1567" height="877" alt="Screenshot 2026-06-30 123447" src="https://github.com/user-attachments/assets/961c3d20-26f6-4f80-9242-c30ac4381a17" />

This is the 3D view of the created custome pcb for smart helemt system



