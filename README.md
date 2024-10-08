Design code:

//gate level modelling

module hs(a,b,d,bo);
input a,b;
output d,bo;
wire n1;
xor(d,a,b);    
not(n1,a);    
and(bo,n1,b);
endmodule

//data flow modelling

module halfadder(a,b,d,bo);
input a,b;
output d,bo;
assign d=a^b;
assign bo=~a&b;
endmodule


Test Bench:

module hs_tb();
reg a,b;
wire d,bo;
hs uut(a,b,d,bo);
initial begin
a=0;
b=0;
#10
a=0;
b=1;
#10
a=1;
b=0;
#10
a=1;
b=1;
#10
end
$finish();
endmodule
