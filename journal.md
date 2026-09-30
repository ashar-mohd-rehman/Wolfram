title: Wolfram
author: Ashar Mohd Rehman
description: A 67 key Mechanical Keyboard with a volume knob and a display
created_at: 2026-9-30

# September 30 : Started and Finished Schematic 

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
