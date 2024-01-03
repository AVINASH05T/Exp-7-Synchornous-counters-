## NAME : AVINASH T
## ROLL NO : 23014109


# Exp-6 Synchornous counters up counter and down counter 

### AIM: 
To implement 3 bit up and down counters and validate  functionality.

## EQUIPMENTS REQUIRED:

 HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
 SOFTWARE REQUIRED:   Quartus prime
 
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 3 bit counter, which simply means it can count from 0 to 7 and vice versa based upon the direction of counting (up/down).

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle. The Counter will be set to Zero when “reset” input is at logic high. The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down. The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output. The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence. Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1: Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, three-bit count:
Three-bit “Up” Counter
![Sync  3 bit upcounters](https://github.com/amal-2006/Exp-7-Synchornous-counters-/assets/148410730/9c466098-f46e-428d-b8d1-89a995aec230)



## DOWN COUNTER 
As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 3-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.

![Sync  3 bit downcounters](https://github.com/amal-2006/Exp-7-Synchornous-counters-/assets/148410730/2002a343-de4a-4282-9f92-cb17b4076a9b)




3-bit Count Down Counter



### Procedure
1. Create a new project in Quartus II software.
2. Name the project as uc for upcounter and dc for downcounter.
3. Create a new Verilog HDL file in the project file.
4. Name the module as dc and uc for downcounter and upcounter.
5. Within the module declare input and output variables.
6. Complete the program.
7. End the module.




### PROGRAM 

## UP COUNTER 

module upCounters(clk, A);

input clk;

output reg [2:0]A;

always @(posedge clk)

begin

	A[2]=(((A[0])&(A[1]))^A[2]);
 
	A[1]=(A[0])^A[1];
 
	A[0]=A[0]^1;
 
end

endmodule


## DOWN COUNTER

module downCounters(clk,A);

input clk;

output reg [2:0]A;

always @(posedge clk)

begin

	A[2]=(((~A[0])&(~A[1]))^A[2]);
 
	A[1]=(~A[0])^A[1];
 
	A[0]=1^A[0];
 
end 

endmodule



### RTL REALIZATION

## UP COUNTER
![image](https://github.com/AVINASH05T/Exp-7-Synchornous-counters-/assets/151514286/766ed2b0-9b9e-4dae-b7c6-c60a1c0c3d15)




## DOWN COUNTER
![image](https://github.com/AVINASH05T/Exp-7-Synchornous-counters-/assets/151514286/f0b3b1ff-47b6-4588-a62e-b54d3c68e7c6)



## TRUTH TABLE


## UP COUNTER
![image](https://github.com/AVINASH05T/Exp-7-Synchornous-counters-/assets/151514286/24f45aee-edf1-4668-8f32-4c958ee1f82b)

## DOWN COUNTER

![image](https://github.com/AVINASH05T/Exp-7-Synchornous-counters-/assets/151514286/f63d70e0-67df-4fdf-9df7-85cdbbe258c1)


### TIMING DIGRAMS  

## UP COUNTER
![image](https://github.com/AVINASH05T/Exp-7-Synchornous-counters-/assets/151514286/77e02461-84e0-491c-9abc-46c8008bd8b5)



## DOWN COUNTER
![image](https://github.com/AVINASH05T/Exp-7-Synchornous-counters-/assets/151514286/5a676e23-0fc0-482e-bd58-1b62b837728e)





### RESULTS 
Thus, the flipflops are implemented using verilog
