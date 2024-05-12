# MOORE_1011
# State Diagram
![image](https://github.com/RESMIRNAIR/MOORE_1011/assets/154305926/4c056127-254f-4b9a-88d1-5486b2577ba3)
# Program:
```
module sd1011_moore(input bit clk,input logic reset,input logic din,output logic dout);

typedef enum logic [2:0] {S0, S1, S2, S3, S4} state_t;

state_t state;

always @(posedge clk or posedge reset) begin

if(reset) begin

dout <= 1'b0;

state <= S0;

end

else begin

case(state)

S0: begin

dout <=1'b0;

if(din)

state <= S1;

end

S1: begin

dout <= 1'b0;

if(~din)

state <= S2;

end

S2: begin

dout <= 1'b0;

if(din)

state <= S3;

else

state <= S0;

end

S3: begin

dout <= 1'b0;

if(din)

state <= S4;

else

state <= S2;

end

S4: begin

dout <= 1'b1;

if(din)

state <= S1;

else

state <= S0;

end

endcase

end

end

endmodule
```
# Output:
![WhatsApp Image 2024-05-12 at 19 07 18_a8249204](https://github.com/kannanAnanth/MOORE_1011/assets/160721190/2029979f-184b-448c-9d18-29885050c65f)
# Result:
Thus the verilog program for MOORE Sequence Detector for 1011 has been simulated and verified successfully.
