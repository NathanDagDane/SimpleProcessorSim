<div align="center">
  <h2>Instruction-Set Architecture Simulation</h2>
  <a href="">
    <img src="https://github.com/user-attachments/assets/e21f2d45-6775-48d8-bf8b-9b1cb99d22e5" alt="Logo" height="80">
  </a>
  <h3>For DTU Cyber Systems Intro</h3>
</div>

This is an implementation of a simple ISA processor in python.  
It is limited to 8-bit unsigned integers and implements the following instruction set:  

<div align="center">
  
| Instruction      |     Description     |
|:-----------------|:-------------------:|
| `ADD R1, R2, R3` |    R1 = R2 + R3     |
| `SUB R1, R2, R3` |    R1 = R2 - R3     |
| `OR R1, R2, R3`  |    R1 = R2 ⏐ R3     |
| `AND R1, R2, R3` |    R1 = R2 & R3     |
| `NOT R1, R2`     |      R1 = ~R2       |
| `LI R1, n`       |       R1 = n        |
| `LD R1, R2`      |   R1 = memory(R2)   |
| `SD R1, R2`      |   memory(R2) = R1   |
| `JR R1`          |      go to R1       |
| `JEQ R1, R2, R3` | if(R2==R3) go to R1 |
| `JLT R1, R2, R3` | if(R2<R3) go to R1  |
| `NOP`            |    no operation     |
| `END`            | end of instructions |
</div>

It works with 16 registers `R0-R15` and 256 memory addresses `0-255`.  
Some test programs are provided written in a simplified assembly language.

## Prerequisites
### VENV:
This does not use any external packages.  
It will work for `python 3.10` and above.

## Usage
### Test 1: 
Run the following command in the base folder of the repository:  
```python3 isa-sim.py 1000 test_1/program.txt test_1/data_mem.txt```  

This is an arbitrary test of all instructions. 

### Test 2 - Bubble sort:
Run the following command in the base folder of the repository:  
```python3 isa-sim.py 1000 test_2/program.txt test_2/data_mem.txt```  

This will sort all the numbers in memory 0 to 9 and write them in memory 10-19.

### Test 3 - Biased Fibonacci random number generator:
Run the following command in the base folder of the repository:  
```python3 isa-sim.py 1000 test_3/program.txt test_3/seed_1.txt``` (change `seed_1` for other tests)  

This will generate a random number using the Fibonacci sequence based on values in memory.  
Check the seed file for the specific purpose of each value.

---
In any test, replace `1000` with your desired maximum cycles before simulation termination.  
