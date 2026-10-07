---
title: "Wolfram"
github: "https://github.com/ashar-mohd-rehman/Wolfram"
description: "A 67 Key Hotswappable Keyboard , With a tiny 0.49 inch display and a rotary encoder to control volume, Building this because I really like the keyboard universe the fact that even if you change one component your keboard will turn out completely different lol"
created_at: "2026-9-30"
total_time: "0m"
---

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

**Total Time Spent: 1.5 Hours**

# October 7, 2026: Started Pcb Finished Matrix 

 Using The Plugin I had installed earliear I Arranged my switches and diodes with the help of json file downloaded from keyboard layout manager 

 ![Screenshot 2026-10-06 192348](https://github.com/user-attachments/assets/738ba8e5-223f-45fa-9687-e413ef357a20)

 After much trial and error I found these settings which worked best 

 But then I saw my bottom row was a complete mess ![Screenshot 2026-10-05 204240](https://github.com/user-attachments/assets/0f820835-f708-4e10-9ace-88a121701ce5)

This was because the space bar was too long so I decided to change my schematic so that I can easily wire up the matrix ![Screenshot 2026-10-05 210016](https://github.com/user-attachments/assets/fba70022-02c1-4a47-bcf4-5101fd6d9e07)

 I wanted to hide the pico on the backside of the board so I decided to place it on top ![Screenshot 2026-10-05 210718](https://github.com/user-attachments/assets/d40b8f8d-d06f-4aeb-b493-0989a4c419bb)

But while wiring up the rows It woudlnt let me in a area ![Screenshot 2026-10-05 211753](https://github.com/user-attachments/assets/5d0d1a9d-f054-4814-b846-5165311e73ba)
This was because kiCad thought their was an antenna here but in real pico their is no antenna besides the W module which I am not gonna use so I edited the footprint to my needs after that I was able to wire it up 

![Screenshot 2026-10-05 211819](https://github.com/user-attachments/assets/1f8b4a67-c026-4b24-8a33-1af364b2ee18)

I had wired my columns with blue so I needed to use read for rows but the diodes were smd and on the blue side so I decided to connect them with via ![Screenshot 2026-10-06 200306](https://github.com/user-attachments/assets/c0c06988-8f10-486f-87e6-9b316cd24755)

But according to pcb making rules its a bad idea because the via can suck solder because of capilarry effect and create weak joints so after much more headache I found the best way to wire up the matrix 
![Screenshot 2026-10-06 200306](https://github.com/user-attachments/assets/d64dc094-04f9-4f0b-a1f1-e6bc0cfe1ac4)

I am still wonderin if I should place the pico on the backside of switches or seperatly
**Total Time Spent: 1 Hours**
