---
cssclasses: []
---

> [!NOTE] Finite automaton
> #### A finite automaton is a collection of 5-tuple 
> (Q, ∑, δ, q0, F),
>
> where:
> 	Q: finite set of states  
> 	∑: finite set of the input symbol  
> 	q0: initial state   
> 	F: final state  
> 	δ: Transition function


## Types of Automata

> [!multi-column] 
>
>> [!info]	### DFA (Deterministic Finite Automata)
>> 	DFA refers to deterministic finite automata. Deterministic refers to the uniqueness of the computation. In the DFA, the machine goes to one state only for a particular input character. DFA does not accept the null move.
>
>> [!info] ### NFA (Non deterministic Finite Automata)
>> 	NFA stands for non-deterministic finite automata. It is used to transmit any number of states for a particular input. It can accept the null move.


> [!important] #### Some important points about DFA and NFA:
> 1. Every DFA is NFA, but NFA is not DFA.
> 2. There can be multiple final states in both NFA and DFA
> 3. DFA is used in Lexical Analysis in Compiler. 
> 4. NFA is more of a theoretical concept.
### Example 1:
DFA with ∑ = {0, 1} accepts all strings starting with 1.

![[Pasted image 20250202170037.png]]

The finite automata can be represented using a transition graph. In the above diagram, the machine initially is in start state q0 then on receiving input 1 the machine changes its state to q1. From q0 on receiving 0, the machine changes its state to q2, which is the dead state. From q1 on receiving input 0, 1 the machine changes its state to q1, which is the final state. The possible input strings that can be generated are ***10, 11, 110, 101, 111.......,*** that means all string starts with 1.


## Transition Table

#### Example 1

![[Pasted image 20250202170708.png]]

| Present State | Next state for Input 0 | Next State of Input 1 |
| ------------- | ---------------------- | --------------------- |
| →q0           | q1                     | q2                    |
| q1            | q0                     | q2                    |
| *q2           | q2                     | q2                    |


#### Example 2
![[Pasted image 20250202170832.png]]

| Present State | Next state for Input 0 | Next State of Input 1 |
| ------------- | ---------------------- | --------------------- |
| →q0           | q0                     | q1                    |
| q1            | q1, q2                 | q2                    |
| q2            | q1                     | q3                    |
| *q3           | q2                     | q2                    |


### Coffee Machine as a Finite Automaton

**Purpose**: To model the operation of a basic coffee machine using the 5-tuple formalism.

**Components**:

1. **Q (Finite Set of States)**:
    
    - States represent the machine's different stages:  
        Q={Off,Ready to Brew,Brewing}.
        
    - **Description**:
        
        - `Off`: The machine is powered off.
            
        - `Ready to Brew`: The machine is on but not brewing.
            
        - `Brewing`: Coffee is being made.
            
2. **∑ (Input Alphabet)**:
    
    - Inputs are actions the user can perform:  
        ∑={Power On,Power Off,Start Brew,Cancel Brew}.
        
    - **Examples**:
        
        - `Power On` can be pressing the power button.
            
        - `Start Brew` is pressing the brew button.
            
3. **δ (Transition Function)**:
    
    - The transition function defines what happens when an input is applied in each state.  
        Here's the transition table:
        

|Current State|Input|Next State|
|---|---|---|
|Off|Power On|Ready to Brew|
|Off|Power Off|Off|
|Ready to Brew|Start Brew|Brewing|
|Ready to Brew|Power Off|Off|
|Brewing|Cancel Brew|Ready to Brew|
|Brewing|Power Off|Off|

4. **q0 (Initial State)**:
    
    - The machine starts in the **Off** state.
        
    - **Formal Notation**: q0​=Off.
        
5. **F (Final/Accepting States)**:
    
    - In this case, an "accepting state" could be when the machine returns to a stable waiting state.
        
    - **Formal Notation**: F={Ready to Brew,Off}.


___
FA with ∑ = {0, 1} accepts those string which starts with 1 and ends with 0.
![[Pasted image 20250202175345.png]]

___
FA with ∑ = {0, 1} accepts the only input 101.
![[Pasted image 20250202175405.png]]

___
FA with ∑ = {0, 1} accepts even number of 0's and even number of 1's.
![[Pasted image 20250202175429.png]]
___

FA with ∑ = {0, 1} accepts the set of all strings with three consecutive 0's.
![[Pasted image 20250202175942.png]]

___
FA with ∑ = {0, 1} accepts the strings with an even number of 0's followed by single 1.
![[Pasted image 20250202182600.png]]

___
# NFA (Non-Deterministic finite automata)
## Formal definition of NFA:

NFA also has five states same as DFA, but with different transition function, as shown follows:

```

δ: Q x ∑ →2Q

where,

1. Q: finite set of states  
2. ∑: finite set of the input symbol  
3. q0: initial state   
4. F: final state  
5. δ: Transition function


```

#### NFA with ∑ = {0, 1} accepts all strings with 01
![[Pasted image 20250202185128.png]]

| Present State | Next state for Input 0 | Next State of Input 1 |
| ------------- | ---------------------- | --------------------- |
| →q0           | q1                     | ε                     |
| q1            | ε                      | q2                    |
| *q2           | q2                     | q2                    |

#### NFA with ∑ = {0, 1} and accept all string of length atleast 2.
![[Pasted image 20250202185401.png]]


___

# EXAMPLES of NFA
Design a NFA for the transition table as given below:

| Present State | 0      | 1      |
| ------------- | ------ | ------ |
| →q0           | q0, q1 | q0, q2 |
| q1            | q3     | ε      |
| q2            | q2, q3 | q3     |
| →q3           | q3     | q3     |

**Solution:**

The transition diagram can be drawn by using the mapping function as given in the table.
![[Pasted image 20250202185459.png]]

___
#### Design an NFA with ∑ = {0, 1} accepts all string ending with 01
solution:
![[Pasted image 20250202185847.png]]

___

#### Design an NFA with ∑ = {0, 1} in which double '1' is followed by double '0'.

**Solution:**

The FA with double 1 is as follows:

![Examples of NFA](https://images.javatpoint.com/tutorial/automata/images/examples-of-nfa4.png)  

It should be immediately followed by double 0.

Then,

![Examples of NFA](https://images.javatpoint.com/tutorial/automata/images/examples-of-nfa5.png)  

Now before double 1, there can be any string of 0 and 1. Similarly, after double 0, there can be any string of 0 and 1.

Hence the NFA becomes:

![Examples of NFA](https://images.javatpoint.com/tutorial/automata/images/examples-of-nfa6.png)  

Now considering the string 01100011

 q0 → q1 → q2  → q3 → q4 → q4 → q4 → q4



Design an NFA in which all the string contain a substring 1110.

**Solution:**

The language consists of all the string containing substring 1010. The partial transition diagram can be:

![Examples of NFA](https://images.javatpoint.com/tutorial/automata/images/examples-of-nfa7.png)  

Now as 1010 could be the substring. Hence we will add the inputs 0's and 1's so that the substring 1010 of the language can be maintained. Hence the NFA becomes:

![Examples of NFA](https://images.javatpoint.com/tutorial/automata/images/examples-of-nfa8.png)  

Transition table for the above transition diagram can be given below:

|Present State|0|1|
|---|---|---|
|→q1|q1|q1, q2|
|q2||q3|
|q3||q4|
|q4|q5||
|*q5|q5|q5|

Consider a string 111010,

δ(q1, 111010) = δ(q1, 1100)  
			  = δ(q1, 100)  
			  = δ(q2, 00)  

Got stuck! As there is no path from q2 for input symbol 0. We can process string 111010 in another way.

δ(q1, 111010) = δ(q2, 1100)  
			  = δ(q3, 100)  
              = δ(q4, 00)  
              = δ(q5, 0)  
              = δ(q5, ε)  

As state q5 is the accept state. We get the complete scanned, and we reached to the final state.


___

Design an NFA with ∑ = {0, 1} accepts all string in which the third symbol from the right end is always 0.

**Solution:**

![Examples of NFA](https://images.javatpoint.com/tutorial/automata/images/examples-of-nfa9.png)  

Thus we get the third symbol from the right end as '0' always. The NFA can be:

![Examples of NFA](https://images.javatpoint.com/tutorial/automata/images/examples-of-nfa10.png)  

The above image is an NFA because in state q0 with input 0, we can either go to state q0 or q1.