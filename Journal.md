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

## Alligning the reference /Made the Fulelage 
hours :-  6.7 hr 

I loaded up the Fusion with the reference image then I Started aligning the reference to the exact size i wanted and then moved it to axis origin .I did it for all the 3 reference with as much precision as possible and this is how the 3D reference Canvas Lo<img width="1022" height="241" alt="Screenshot 2026-07-07 094033" src="https://github.com/user-attachments/assets/737ab11d-b1d8-4ba2-b0f1-7d3a5e144f81" />ssets/6c143896-3292-4962-8e3e-9c78ffbe8cfb" />

. Then I made the side view Sketch of the main body
<img width="797" height="322" alt="Screenshot 2026-07-07 055447" src="https://github.com/user-attachments/assets/f1bfb7d8-8f83-47cd-9a76-ac02a28dc1e6" />

then I made the top view of the body
<img width="725" height="293" alt="Screenshot 2026-07-07 055929" src="https://github.com/user-attachments/assets/f0ab89da-7118-472f-8c8f-c312f97decb4" />

there were few sketch allignment issue so I solved them 
<img width="538" height="321" alt="Screenshot 2026-07-07 060032" src="https://github.com/user-attachments/assets/84464578-d763-4a2e-9ae7-d0338d159bba" />

then after that I added offset plane for Rails . I  keeping in mind about the top/bottom sketch and the side sketches . In total I had to add about 19 of these offset planes and this is the look it looks

<img width="918" height="557" alt="Screenshot 2026-07-07 061135" src="https://github.com/user-attachments/assets/33886e00-05fd-42ba-98d0-0298cfac3e6d" />
then for every offset plane I had to make rail . For that I needed to project Intersect all the for guildlines then use Spline to make that rails . this is how the first rail looked liked<img width="402" height="370" alt="Screenshot 2026-07-07 061417" src="https://github.com/user-attachments/assets/49b698dd-173a-4e86-826e-b90d9ccad208" />

and this was the end look after  I did it for all of the rails 
<img width="956" height="460" alt="Screenshot 2026-07-07 082550" src="https://github.com/user-attachments/assets/69e01af7-617e-4a97-95d7-7439f5e9269b" />

. It took me some times to reach here then I went to make the 3D model of the body using LOFT Feature but errors started showing up<img width="1422" height="910" alt="Screenshot 2026-07-07 082920" src="https://github.com/user-attachments/assets/fcb5c53e-d7fc-4a5d-adc8-2f6847f53f5c" />


I Tried to fix the errors but nothing much happened So I took a decision to rebuild it again because there wasn't any outcome I am goint to receive out of this . So Again I made the skectches of top and Side view

<img width="1022" height="241" alt="Screenshot 2026-07-07 094033" src="https://github.com/user-attachments/assets/b948747d-727f-4039-8f36-9569fff40f0f" />

<img width="1015" height="283" alt="Screenshot 2026-07-07 094338" src="https://github.com/user-attachments/assets/91be72bb-f0f8-47ee-b984-c95571572118" />

then again I went to make the model and waala this time things worked perfectly

<img width="1427" height="1002" alt="Screenshot 2026-07-07 105446" src="https://github.com/user-attachments/assets/5d732a07-cd20-4f9d-9073-2a4be7d58433" />

Final Fuselage look 

<img width="1133" height="658" alt="Screenshot 2026-07-07 105613" src="https://github.com/user-attachments/assets/ab95ac76-b494-4611-815e-691fd704a7c2" />

## Made the Wings 
hours :-  3.4 hr 

So I made the airfoil first

<img width="1007" height="307" alt="Screenshot 2026-07-07 192831" src="https://github.com/user-attachments/assets/a50a1672-e8b5-4d22-888b-afec485f50d2" />
then I aligned it to the fuselage
<img width="851" height="192" alt="Screenshot 2026-07-07 193133" src="https://github.com/user-attachments/assets/ce8036d4-7e03-4cbc-af3e-8a530c977b39" />
fter that I made the guild sketch's of the wing<img width="711" height="530" alt="Screenshot 2026-07-07 194714" src="https://github.com/user-attachments/assets/bbc26dd9-f74a-4794-b1c6-3370bded8e89" />
hen I made the 3D model of the wing

then I extruded it and repeated the same for the other Side and this is how it looks 

<img width="838" height="635" alt="Screenshot 2026-07-07 202218" src="https://github.com/user-attachments/assets/41b11748-7813-4165-ac29-1dd15e63e4fb" />
<img width="888" height="732" alt="Screenshot 2026-07-07 202341" src="https://github.com/user-attachments/assets/232549b4-367a-40fc-99a1-4ea6636c9650" />

then I added stabalizers to the end of the wings and this is the final look 

<img width="513" height="431" alt="Screenshot 2026-07-07 221452" src="https://github.com/user-attachments/assets/1ca2eb3f-c3d2-4036-9ec6-ad7755bd53a4" />

then I made cuts for mobility and component fixing 

<img width="887" height="635" alt="Screenshot 2026-07-07 225535" src="https://github.com/user-attachments/assets/638331bf-bdd9-48e5-b5ff-26f8ad0b4f80" />
<img width="865" height="646" alt="Screenshot 2026-07-07 225521" src="https://github.com/user-attachments/assets/e234a617-b025-4918-9342-f69ecface59b" />

## Finilized the CAD
hours :-  4.2 hr 

First I made the Surface to which I will attach the motors<img width="743" height="765" alt="Screenshot 2026-07-08 154108" src="https://github.com/user-attachments/assets/d03b5d0e-c8e8-4205-a1d8-fcd1d8ce4d72" />


then I added the rest of the eternal components like the Flight controller , Battery ,Receiver and ESC

<img width="772" height="677" alt="Screenshot 2026-07-08 155047" src="https://github.com/user-attachments/assets/890d234c-f414-46f5-9a9c-37c8da878aeb" />

<img width="806" height="632" alt="Screenshot 2026-07-08 155057" src="https://github.com/user-attachments/assets/e337b517-80c9-4e9d-b468-65f25975fedb" />

that I added the servos to there respective position

Then I made respective cut's and fix for the servoes and the Brushless motors using sketch and offset plane tools 

<img width="820" height="342" alt="Screenshot 2026-07-08 155750" src="https://github.com/user-attachments/assets/90ee8bce-1a67-4f25-aef7-266e91ddb405" />
<img width="415" height="422" alt="Screenshot 2026-07-08 160148" src="https://github.com/user-attachments/assets/471994d0-6b9e-4a12-8c6b-946586127c62" />


<img width="697" height="697" alt="Screenshot 2026-07-08 160835" src="https://github.com/user-attachments/assets/a32399ae-bf4b-40f8-ace0-d0e714ff13f0" />
<img width="787" height="735" alt="Screenshot 2026-07-08 160402" src="https://github.com/user-attachments/assets/2aae05d4-cbcd-49be-a1ff-6886fa97bbdb" />
<img width="887" height="687" alt="Screenshot 2026-07-08 161004" src="https://github.com/user-attachments/assets/67ace7ea-8921-4b18-b5d9-dce8a3d79333" />


So this is the final polished LOOK


<img width="742" height="680" alt="Screenshot 2026-07-08 161159" src="https://github.com/user-attachments/assets/2c4b366f-94a3-48e2-9fac-514d196767ad" />



