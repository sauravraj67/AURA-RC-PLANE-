### So I am making an Custom RC Plane with custom Flight Controller


 ##  Schematics for Flight Controller
Hours - 6.1 hr

So I started with the schematics for my flight controller . I initially started with adding the USB-C ,12V battery connector and a 3 pin switch to switch between power from battery and USB-C as per the need them I made the circuit and added the labels then the STM32 and other sensores work on a constant 3.3V . So I added a 3.3V Voltage regulator (AMS1117-3.3) and made circuit for ir and added the required labels then the battery gives 12V but servos need 5V . So for that I added a 5V Voltage regulator (L7805) and made circuit for it and added the labels to them them as well after which  then I added the IMU (MPU5060) and barometer (BMP280) and made the required circuit for them and then I added the MCU (STM32F401CBUx) added the crystal oscillator circuit then I added the decoupling capacitors  added the boot button and attached all the labels from sensors , ESC ,Servos and USB to it as per it's pin outlet and this is the final look of the schematics  <img width="1186" height="682" alt="Screenshot 2026-07-13 002129" src="https://github.com/user-attachments/assets/07b41a0f-ec9f-4464-bfaa-c051b880c6cd" />

## Making the PCB Layout 
hours :- 3.25 hr

So Now I started with the components placement . I First updated the PCB editor with all the components then I started arranging all the Component SET . I first made the USB-C circuit cluster arranged the required resistors around it then I started arranging the main chips in a very simple manner after that I started placing the Oscillator near to the MCU then I started arranging the IMU and barometer circuit . then I placed all the other components near to there connection and then I started forming a basic layout of the Board. IT is for a RC flight controller SO I would need to use a rectangular dimension instead of square for drones. then I placed the pins for batter ,servos and ESC made sure that they are near to there connection ,so that It is easy to rout . and after few alteration for ,I ended up with a final design. then I  added the boundary and added few holes on the PCB for connection ,Also I made sure that there is enough space for me to rout around the components. PCB (without rout)

<img width="707" height="348" alt="Screenshot 2026-07-13 001244" src="https://github.com/user-attachments/assets/f135681a-0f09-4d28-a03d-fdfc956c85ac" />

## Routing the Fligh Controller 
hours :- 5.75 hr 

So I started with routing I initiated with the Data line connections , A connection hole was coming onto the path so for now I deleted it then I didn't specifically named the connection with _D+ and _D- without it kicad would do a differential pair , So I update the schematics then I made the differential pair for data lines. then I left the GND and 3.3V connections as I will use fil-zone on top layer for power and GND for bottom layer for stability. I used thicj traces for the 5V and 12V connections and I started making routs for the whole board one by one first I made the components circuit for sensors , routed the oscillator  to MCU then I started routing the 5v and 12v lines started routing the decoupling capacitors . I used vias where it was needed , made sure that the routs are clean and simple . I also had to made few changes on the PCB rout So that I can easily rout then I added 3.3V fillzone on top layer and GND fill zone to bottom layer and there were few miss connections , So I started solving them and then I used the Rules checker for any errors . I solved the major issues like  miss-Connections and rout near vias and holes  and left the basic the silkscreen ones. Then I added a text logo for the PCB and stared adding text for the naming the outpins and there connections . And this is the final looks of the Flight Controller PCB 

TOP Layer 

<img width="1092" height="538" alt="Screenshot 2026-07-13 003331" src="https://github.com/user-attachments/assets/d845d9bf-0a2e-42b0-9c08-b509ff6b9717" />

Bottom Layer 

<img width="1120" height="557" alt="Screenshot 2026-07-13 003340" src="https://github.com/user-attachments/assets/03fa0a7d-afb5-4a6e-8514-33faf5ef87ce" />

3D View 

<img width="898" height="560" alt="Screenshot 2026-07-13 001310" src="https://github.com/user-attachments/assets/18c947ec-78c6-49ed-b4de-eecb539a39a4" />

## Finalizing The Concept Design
hours :-  2.8 hr 

So Now I went and finalized the concept design . As I already Said before It will be a Tailless Twin motor RC Plane. So I kept that in mind and went and researched about that concept . After considering multiple design . I ended up liking one design then I selected a air-foil that would suit it and generated a reference design with TOP , FRONT and SIDE View of the plane with dimensions also with the Air-Foil. The Air-Foil I selected was MH-45 reflex . It is a 9.85%-thick reflex airfoil designed by Martin Hepperle specifically for flying wings and tailless model aircraft. So I added it as per my Design requirements. The Body Base is heavily inspired by
* Blended Wing-Body
* Sweepback Stability
* Integrated Twin Nacelles
And this is the final look of it

<img width="1062" height="558" alt="Screenshot 2026-07-05 212102" src="https://github.com/user-attachments/assets/09ed9854-a8fc-49f2-9ee8-71e2f5378ad7" />




