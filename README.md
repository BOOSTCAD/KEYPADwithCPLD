# KEYPADwithCPLD
This a project about the setup of keypad on CPLD and the implementation on Password Lock System.

![NEW-UTM-LOGO-copy](https://user-images.githubusercontent.com/87567016/126034256-73a81f2b-0cd6-4e57-a9a4-7f39ac7daefa.jpg)

# Milestone 5 & 6 Report

SKEE 4273 CAD WITH HDL 

Group Name: Boost CAD

Section: 01

Group Members : 	

1. ONG SUEY LI	(A18KE0247)

2. LIM RUE YIE	(A18KE0100)

3. TAN WEI FANG	(A18KE0277)

Lecturer Name : PM. Muhammad Mun’im bin Ahmad Zabidi

# INTRODUCTION

Keypad Theory
A keypad is a block or pad of buttons set with an arrangement of digits, symbols, or alphabetical letters.  Keypads are found on devices which require mainly numeric input such as combination locks, safe deposit box lock and digital door locks. In a standard keypad wired as an X-Y switch matrix, normally-open switches connect a row to a column when pressed. A 4×4 keypad is a 16-button keypad consisting of a combination of four rows and four columns indicated as R1, R2, R3, R4 for rows and C1, C2, C3, C4 for columns. Whereas a 4×3 is a 12-button keypad with 4 rows and 3 columns. The number of keypad buttons are Rn x Cn and the number of pin connections is Rn + Cn; Rn – n number of rows, Cn – n number of columns. Hence the 4×4 keypad has 8 pins and 4×3 has 7 pins. 
How Does It Works?
Connect power to rows, so they are High level. Then set all the rows R1-R4 as Low and then detect the status of the columns. Any column of Low indicates there is key pressing and that the key is among the 4 keys of the column. If all columns are High, it means no key is pressed down.
Next, locate the key. Since the column in which the pressed key lies is identified, knowing the line would finalize the testing. Thus, set the rows as Low in turns until any is unveiled accordingly – other rows will still be High.
Now the row can be identified. Detect the status of each column in turns. The column tested Low is the one intersecting with the line – their cross point is just the key pressed.
  
# Flowchart
![projectcad](https://user-images.githubusercontent.com/87567016/126034267-19e82923-f773-4aa9-8aee-6ac2c4e826dd.jpg)

The global clock for CPLD is 50MHz, a prescaler is required to read the data with slower speed. Therefore, the keypad is scanned at a slow clock of 10Hz as. At every positive edge, the loop of scans keypad happens horizontally, each line in every cycle. The row pins should be connected to the input port and then the column pins are connected to the output port. Each line scan is divided into 3 parts:
  1) Set current line output to 0 (ground).
  2) Read inputs row by row and column by column.
  3) Set current line output to 1 (VCC).
# Software
Altera QuartusII

# Hardware
1. Altera MaxII EPM240T100C5N CPLD Development Board 5V
2. USB Blaster
3. Common Cathode BCD 7-segment
4. 4x4 Matrix Keypad
5. Breadboard
6. Male-Male Jumper wire

# Verilog Code for Keypad 
1. Prescaler
![slowclock](https://user-images.githubusercontent.com/87567016/126034512-e9173371-ce41-4e92-89e8-7798fd8dd77f.PNG)

2. Keypad Scanner
![keypad1](https://user-images.githubusercontent.com/87567016/126034544-11353b28-e390-49cb-a1ac-6f23bb1bcb2c.PNG)
![keypad2](https://user-images.githubusercontent.com/87567016/126034551-50585ee9-f9a9-43c6-9e2f-bd1cc096a22c.PNG)
![keypad3](https://user-images.githubusercontent.com/87567016/126034555-40e11002-0ec9-415e-9133-e1e87a779fc9.PNG)

3. Binary to BCD Converter
![binary2BCD](https://user-images.githubusercontent.com/87567016/126034563-dce9bf45-ccaf-4312-9c6c-f463c19b9198.PNG)

4. BCD to 7 segment 
![bcd2sevenseg](https://user-images.githubusercontent.com/87567016/126034572-22ba6378-5662-4a21-b0d9-d0b5d297b2ee.PNG)
