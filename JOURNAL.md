title: Wolfram

github: "Wolfram"

author: Ashar Mohd Rehman

description: A 67 key Mechanical Keyboard with a volume knob and a display

created_at: 2026-9-30

total_time: "3h"

 # September 30, 2026: Started and Finished Schematic
<!-- fabricate:entry -->

I started by installing useful Libraries to my Kicad Project Named "Wolfram" (FUNFACT - Wolfram is german for Tungsten)
<img width="1328" height="805" alt="Screenshot 2026-09-29 202338" src="https://github.com/user-attachments/assets/239b789a-2ae7-4c1a-9ef2-0abf270b8ea5" />
The Libraries I added all server a purpose
1) Keyboard Footprints Placer helps me to place all my keys based on a json file
2) Keyswitch Kicad has various symbols and footprints for switches
3) Marbastlib the all time famous library of high quality switches

After that I went on  https://www.keyboard-layout-editor.com/   to finalise the layout of my keyboard so I can start creating the schematic 
<img width="2087" height="1186" alt="Screenshot 2026-09-30 185523" src="https://github.com/user-attachments/assets/4dec4d9d-1bce-40d5-8a6d-eaccfaea2973" />

After that I added the hotswap symbols for cherry mx switches and diodes to create a matrix and started routing it, Then I gave each column and row labels <img width="1389" height="980" alt="Screenshot 2026-09-30 190944" src="https://github.com/user-attachments/assets/ec5ccacf-eed8-4276-b53c-f2f55b849818" />

All rows of my matrix had 14 keys besided the second one and the last one, My second row had 15 keys and my last had 10, So I placed my switch 29(15th key) into last row as its 11th key, Doing this I saved myself from creating another column hence saving me a gpio pin which will serve a greater purpose 

<img width="267" height="796" alt="Screenshot 2026-09-30 191514" src="https://github.com/user-attachments/assets/5dd805c7-d14e-4352-8de5-0107f3936bbb" />


Then I went On and connected all my rows and columns to my raspberry pi pico <img width="610" height="659" alt="Screenshot 2026-09-30 192158" src="https://github.com/user-attachments/assets/7fac7535-2c97-45bd-8b75-80423825003e" />


And then I decided to add neopixel perkey rgb leds <img width="1408" height="677" alt="Screenshot 2026-09-30 195446" src="https://github.com/user-attachments/assets/8b6fcfa0-3f83-448f-b01b-0be64186402a" />
After wasting a good 15 minutes trying to understand how they work I decided to skip them because apparently if they are too bright they can shut down my laptop also each led has teeny tiny 4 legs that I have to solder(I am bad at it) and I had to add a decoupling capacitor to each one aswell so that meant 67 x 6 = 402 
teeny tiny points I had to solder so I decided to skip the neopixels all together 


After that to maintain the glamour of my keyboard I decided to add a rotary encoder and a very tiny oled display which I found while scrolling Robu.in <img width="666" height="526" alt="Screenshot 2026-09-30 200027" src="https://github.com/user-attachments/assets/90c4a645-d7a8-4e16-80f4-633f961f5739" /> this I^2C Display is perfect for me as it is rlly smol and takes only 2 of my gpio pins 


After that I added both of these symbols and connected them to their respectable GPIO pins <img width="808" height="1207" alt="Screenshot 2026-09-30 200851" src="https://github.com/user-attachments/assets/f7d453f6-31fd-48e0-8c78-1ca6429c928d" />


Heres how my final schematic is looking lol <img width="2066" height="894" alt="Screenshot 2026-09-30 201226" src="https://github.com/user-attachments/assets/e2a3c066-cc83-4721-bd14-84660b5a2ecd" />

**Total Time Spent: 2 Hours**

 # October 5, 2026: Assigned Footprints and Fixed schematic
<!-- fabricate:entry -->

 So basically I realized that my keyboard needs stablizers and I decided to add em <img width="1142" height="374" alt="Screenshot 2026-10-01 204524" src="https://github.com/user-attachments/assets/9529c5b9-6b38-44c0-a158-6704537d6226" />

After trying to understand what keys need what size stablizers I realized that they all have same symbol lol :/ 

Then I went on and ran ERC( Electrical rules checker) <img width="1142" height="374" alt="Screenshot 2026-10-01 204524" src="https://github.com/user-attachments/assets/645db952-5437-4dd3-a16d-62dbf241b693" />

 and fixed each one of em one by one with the help of google and gemini
 <img width="1109" height="624" alt="Screenshot 2026-10-01 204817" src="https://github.com/user-attachments/assets/73219aa7-37f5-4a02-9ef6-7d5233276aa3" />

 Bro then I realized instead of connecting rows to my diodes I connected them to switch legs lol and I wouldnt even realize it coz I was ignoring warnings but then I somehow did notice <img width="588" height="1186" alt="Screenshot 2026-10-01 205015" src="https://github.com/user-attachments/assets/587e9290-0188-402b-b631-0d802beae521" />

 and fixed it aswell lol 
<img width="430" height="1165" alt="Screenshot 2026-10-01 205100" src="https://github.com/user-attachments/assets/7d624551-baca-45a4-9003-06885ec2d064" />

Heres how my final schematic be lookin now :0 

<img width="1956" height="899" alt="Screenshot 2026-10-01 205648" src="https://github.com/user-attachments/assets/d8d27357-5cea-4972-a3f5-628dfb489318" />

After that I went on to assign my footprints which most of em were already assigned but I had a hard time understanding what keys were what size until A quick google search told me that the sizes do not matter as the placer plugin I installed earlier takes care of that ( I was lowk sad couldnt find 2U size for backspace loll)
<img width="603" height="220" alt="Screenshot 2026-10-01 210404" src="https://github.com/user-attachments/assets/e48bde71-c0c6-4e95-a2b8-dd58d7d12fd3" />

and well after that I changed diodes from 532 to SOD 123 and gave a rotary encoder footprint  (ec11) <img width="1218" height="234" alt="Screenshot 2026-10-01 210956" src="https://github.com/user-attachments/assets/35834be6-46ed-46e5-ad79-999e164251f3" />

**Total Time Spent: 1 Hours**







