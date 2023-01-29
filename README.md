# EXPERIMENT-06 
# SYNCHRONOUS COUNNTERS

## AIM : 
To implement 4 bit up and down counters and validate  functionality.
## HARDWARE REQUIRED :
- PC
- Cyclone II 
- USB flasher
## SOFTWARE REQUIRED : 
- Quartus prime
## THEORY : 

### UP COUNTER  :

The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

### 4-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



### DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.


### 4-bit Count Down Counter

![DOCO](https://user-images.githubusercontent.com/118054670/215304666-d754970d-9995-458c-a612-0da68ce9147a.png)



## PROCEDURE :

1. Create a new project in QuartusII software.

2. Name the project as uc for upcounter and dc for down counter.

3. Create a new verilog hdl file in the project file.

4. Name the module as dc and uc for down counter and up counter.

5. Within the module declare input and output variables.

6. Create a loop using if-else with condition parameter as reset value.

7. End the loop.

8. End the module.

## PROGRAM :
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by : MIDHUN AZHAHU RAJA P 
RegisterNumber :  22008311
```
### UP COUNTER :
```python
module upcounter(input clk,input reset,output[0:3]counter);
reg[0:3] counter_up;
always@(posedge clk or posedge reset)
begin
if(reset)
counter_up<=4'd0;
else
counter_up<=counter_up+4'd1;
end
assign counter=counter_up;
endmodule
```
### DOWN COUNTER :

```python
module downcounter(input clk,input reset,output[0:3]counter);
reg[0:3] counter_down;
always@(posedge clk or posedge reset)
begin
if(reset)
counter_down<=4'd0;
else
counter_down<=counter_down-4'd1;
end
assign counter=counter_down;
endmodule
```


## RTL LOGIC :

### RTL LOGIC FOR UP COUNTER :



![uprtl](https://user-images.githubusercontent.com/118054670/215304931-86b6106d-41c4-4be3-aaa4-7e30afbb7407.png)


### RTL LOGIC FOR DOWN COUNTER :


![downrtl](https://user-images.githubusercontent.com/118054670/215304939-51b1b4a7-39e4-4cc0-b8e9-63855d894a2e.png)



## TIMING DIAGRAM :

### TIMING DIAGRAM FOR UP COUNTER :

![uptime](https://user-images.githubusercontent.com/118054670/215304995-152fe369-2f4c-47da-8fdf-c1bb6ec630c7.png)


### TIMING DIAGRAM FOR DOWN COUNTER :


![downtimre](https://user-images.githubusercontent.com/118054670/215304997-eb4174ac-c1dd-4c13-b9e7-5e915970c263.png)



## TRUTH TABLE :

### TRUTH TABLE FOR UP COUNTER :

![uptable](https://user-images.githubusercontent.com/118054670/215305000-405fb23f-5d69-4da3-9446-8e040e19f0a7.png)


### TRUTH TABLE FOR UP COUNTER :

![downtable](https://user-images.githubusercontent.com/118054670/215305005-52b191af-1ecb-4690-b899-1ae7a4c70a40.png)

## RESULTS :

Thus, the Synchornous counters of up counter and down counter circuit are studied and the truth table for different logic gates are Successfully verified.


