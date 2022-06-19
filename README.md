# Inspiration
Whether for study or work, more and more people leave their hometown and rely on phones to communicate with their parents, friends or lover. However, compared with the paper letters, this electronic messages seem less "warm". We are trying to combine the advantages of paper and letters and electronic messages to create a new way for people to express their love remotely.
# What it does
You can write a letter and share the photo you take to your lovers through MQTT net, and once people set before the printer, it will print what you send through website. The printer could print things locally and remotelly and it can also detect the local temperature of humidity.
# How we built it
1. Fill the BOM and draw related schematic through Altium. 【BOM.xlsx】
2. Design the related power strcuture: 5V to 7.4V boost-circuit and 5V to 3.3V buck-circuit. 【Power Structure.docx】
3. Draw the PCB through Altium. 【Printer_Altium.zip】
4. Write CLI, FreeRTOS driver and OTAFU(Bootloader) to SAMW25.
5. Design Node-Red schematic(MQTT). (https://ese-516-project.mybluemix.net/red/#flow/f85a4551db069a13)
6. Write MQTT, I2C, USART, DS-100, SHTC3, Thermal Printer driver.
# Challenges we ran into
1. The Thermal Printer we used only has library for Arduino, we need to convert it to C and make it fit into ATSAM. What's worse, there is even no datasheet for this printer.
2. The TFT touch screen we used communicate in SPI and there are few driver sources, we didn't finish it yet...
# What's next for it
We are trying to write the SPI driver and printer's driver by ourselves. Once we finished, the product gonna has a 2.4-inch touchscreen for users to write down texts like writing a letter or to draw a picture. The futher version may even add the handwriting recognition. (We may use DL to analyze it in cloud.)
# Build with
C, ASF, FreeROTS, MQTT
# Related Work
## System Diagram
<img width="900" alt="system" src="https://user-images.githubusercontent.com/87698138/172967498-daf9b1bb-4347-4bd5-9206-6517738d9def.png">

## PCB Schematic (main)
<img width="1300" alt="schematic" src="https://user-images.githubusercontent.com/87698138/172967515-283adf82-e996-4b68-80e3-355ecba3c7c1.png">

## PCB Layout (Top view)
<img width="1200" alt="layout" src="https://user-images.githubusercontent.com/87698138/172968140-431ca936-dd69-440e-bb9d-5f9cd7ea8dda.png">

## 3D Model
<img width="900" alt="layout" src="https://user-images.githubusercontent.com/87698138/174491477-3676e104-b962-43da-91b9-0635a4ecf42c.jpg">

# File Description
【**BOM.xlsx**】: The BOM of our PCB.

【**Componets information.docx**】: The information of componets we used in this project.

【**Power Structure.docx**】: The Power strcuture of PCB.

【**Pinter_Documentation.PDF**】: The manufacturing information of PCB

【**SAMW25_PinAssignments.xlsx**】: The Pin assignments of SAMW25 in PCB

【**Printer_Altium.zip**】: Schematic we draw

【**Printer_Microchip.zip**】: C code for Microchip Studio
# Partner
Xinyang Tan (@jasonxytan)
