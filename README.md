# 4x4 KEYPAD with CPLD
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
Altera Quartus II

# Hardware
1. Altera Max II EPM240T100C5N CPLD Development Board 5V
2. USB Blaster
3. Common Cathode BCD 7-segment
4. 4x4 Matrix Keypad
5. Breadboard
6. Male-Male Jumper wire

# Verilog Code for Keypad 
[finalKeypad.zip](https://github.com/BOOSTCAD/KEYPADwithCPLD/files/6834611/finalKeypad.zip)

![pin planner 1](https://user-images.githubusercontent.com/87567016/126037687-47eb1786-3a43-48a0-abee-fbace357c03b.jpeg)
![pin planner 2](https://user-images.githubusercontent.com/87567016/126037691-82ac7ce8-5517-4ade-ab35-25584cdcb8bc.jpeg)

# Implementation of Keypad on Password Lock System
# 1. Flowchart 
![Flowchart-ASM chart](https://user-images.githubusercontent.com/87567016/126037876-7f08659b-248e-44fe-b690-0dc56a99466d.png)


# 2. CU
![CU1](https://user-images.githubusercontent.com/87567016/126038207-591f4950-888a-435c-a10e-fd48e0f0091a.PNG)
![CU2](https://user-images.githubusercontent.com/87567016/126038181-7f86b80b-cf7a-44b6-90f0-8ee005480afd.PNG)



# 3. DU 
![shift_reg1](https://user-images.githubusercontent.com/87567016/126037888-42bca0ed-d314-4233-8009-f84f25f7edba.PNG)
![shift_reg2](https://user-images.githubusercontent.com/87567016/126037893-db9b3f6b-3cd0-4903-a990-96202143b9aa.PNG)
![comparator](https://user-images.githubusercontent.com/87567016/126038020-9550fb96-077c-466f-b02d-b7729e6de156.PNG)
![counter](https://user-images.githubusercontent.com/87567016/126038066-54b01b11-fd76-462c-966d-e7d46643edbe.PNG)
![Timer](https://user-images.githubusercontent.com/87567016/126038027-be1778df-cffe-48e1-99c7-7dd643713ec1.PNG)
![DU](https://user-images.githubusercontent.com/87567016/126038033-5e72fe09-4abf-4900-a12a-3c19ab3cdf27.PNG)



# 4. CU + DU Top Level
![CDU](https://user-images.githubusercontent.com/87567016/126037626-06fbf6f0-1e89-4390-b55d-7bad3224dcde.PNG)

# 5. Result 
![WhatsApp Image 2021-07-17 at 20 56 28](https://user-images.githubusercontent.com/87567016/126037660-6ec100b0-1242-4b46-9163-fb54b50e6e08.jpeg)

