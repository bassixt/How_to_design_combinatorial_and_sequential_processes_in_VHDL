# SO Topic for Digital Systems course

## How to design combinatorial and sequential processes in VHDL

## Differences between combinatorial and sequential logic circuits:


* In general there are two kind of logic circuits:

 
  
 > Combinatorial circuits in which the outputs depend only on the input values through a boolean function. In other words a combinatorial circuit is such that it has not inferred memory elements.
   
![combinatorial](images/comb.png)
 
 > Sequential circuits in which the outputs depend on the input values and the story of the circuit. In these kind of circuits are needed memory elements.

![sequential](images/seq.png)
In the images are shown... (to add images that shows sequential circuits vs combinatorial)

```vhdl
entity H_A is
port(
    A: in bit;
    B: in bit;
    S: out bit;
    C: out bit
    );
end H_A;

architecture beh of H_A is
begin
    process(A,B)
    begin
        S <= A xor B;
        C <= A and B;
    end process;
end beh;

```
