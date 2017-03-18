# SO Topic for Digital Systems course

## How to design combinatorial and sequential processes in VHDL

## Differences between combinatorial and sequential logic circuits:


* In general there are two kind of logic circuits:

 
  
 > Combinatorial circuits in which the outputs depend only on the input values through a boolean function. In other words a combinatorial circuit is such that it has not inferred memory elements.
   
![combinatorial](images/comb.png)
 
 > Sequential circuits in which the outputs depend on the input values and the story of the circuit. In these kind of circuits are needed memory elements.

![sequential](images/seq.png)

## VHDL code for combinatorial circuits
Combinatorial circuits can be described in vhdl using normal concurrent signal assignments or using a process. Since there are not memory elements, all assigned signals in a process are always explicitly assigned in all paths of the process statements.

Combinatorial processes have a sensitivity list after the sintax element "process". The sensitivity list specifies the set of signals, events on which may resume a process. 

The process is activated if a value change appears on one of the sensitivity list signals. 

Combinatorial processes' sensitivity list must contain all signals which appear in conditions such as if and any signal appearing on the right hand side of a assignment.

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
