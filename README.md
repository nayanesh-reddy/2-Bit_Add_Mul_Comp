- Just Trying out TinyTapeout - Go to https://tinytapeout.com for instructions!
</br>

# 2-Bit Adder, Multiplier and Comparator

- This Logic Design mainly contains an 2-bit Adder and a 2-bit Mutliplier.
- The Adder can also perform subtraction using 2's complement and the subtraction results are used to compare two 2-bit numbers (whether they are equal, greater or lesser than other). 
- This design does not contain a 2-bit comparator.

- The results from adder and multiplier are muxed and stored in D-Flip Flops (only when load is enable or logic-1 because the clk of DFF is clock gated) 
- Inputs
   - in[1] = clk
   - in[2] = load
   - in[3] = A[0]
   - in[4] = A[1]
   - in[5] = B[0]
   - in[6] = B[1]
   - in[7] = sel[0]
   - in[8] = sel[1]
- Select Lines
   - sel[1] &nbsp; sel[0]
   - 0 &emsp;&emsp; 0  &emsp;&emsp; -> ADD (A+B) 
   - 0 &emsp;&emsp; 1  &emsp;&emsp; -> MUL (A*B) 
   - 1 &emsp;&emsp; 0  &emsp;&emsp; -> SUB (A-B)
   - 1 &emsp;&emsp; 1  &emsp;&emsp; -> MUL (A*B) 
- Outputs
   - 	                         ADD        SUB         MUL
   - 	 out[1] = 7_seg-a  =    Add[0]     Sub[0]     Mul[0]
   - 	 out[2] = 7_seg-b  =    Add[1]     Sub[1]     Mul[1]
   - 	 out[3] = 7_seg-c  =    Carry      Borrow     Mul[2]
   - 	 out[4] = 7_seg-d  =    0          1          Mul[3]
   - 	 out[5] = 7_seg-e  =    0          (A==B)     0
   - 	 out[6] = 7_seg-f  =    in[2]      in[2]      in[2]
   - 	 out[7] = 7_seg-g  =    0          (A>B)      0
   - 	 out[8] = 7_seg-dp =    0          0          1

   
### Logic Design in Wokwi - https://wokwi.com/projects/341524192738411090
![image](https://user-images.githubusercontent.com/84563214/188326522-5c286e24-babc-43f0-8070-86adcc182a46.png)

### GDSII of the Logic Design (Openlane, Skywater 130nm PDK used)
![gds_render](https://user-images.githubusercontent.com/84563214/188326515-eec373c3-b434-4543-a390-9b3675d59678.svg)
 

