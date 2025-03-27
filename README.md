# Hamming-Shannon Coding 
### Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.
## Aim:
The aim is to apply Huffman and Shannon-Fano coding to a discrete memoryless source, calculate key metrics like entropy and efficiency, and compare the results. This demonstrates the effectiveness of these coding techniques for data compression.

## Tools Required:
+ personal Computer with Scilab
+ Python IDE(Numpy)
## Program:
~~~
import numpy as np
import math 

L  = 0
hs = 0
p = []
lk = []

n = int(input("Enter the number of Samples : "))

for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
~~~
## Calculation:


## Results:
The Huffman and Shannon-Fano coding methods were applied, with Huffman achieving better efficiency and code lengths closer to the entropy. The entropy of the source was calculated, revealing the theoretical limit. Shannon-Fano showed slightly higher redundancy, indicating less optimal performance.
