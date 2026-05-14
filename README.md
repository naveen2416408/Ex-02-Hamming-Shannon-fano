# Ex: 02 - Huffman - Shannon_fano
## AIM: 
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average codeword length, Entropy, Variance, Redundancy, Efficiency.

## TOOLS REQUIRED:
```
Python IDE with Numpy and Scipy.

## PROGRAM:
#Huffman and Shannon-Fano coding
import numpy as np
import math
L=0
hs =0
p=[]
lk =[] # Renamed from 1k
n =int(input("Enter the number of Samples :"))
for i in range (n):
    pr = float(input(f"Enter the probability of sample values {i + 1}:")) # Added closing parenthesis
    p.append(pr)
for j in range (n):
    l_val = float(input(f"Enter the length of the sample values {j + 1}:")) # Renamed from 1
    lk.append(l_val)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k]*lk[k]
    L=L+Avg1
# Entropy
for k in range(n):
    e =p[k]*math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff = hs /L
eff = round(eff,3)
# Redundancy
red = round(1 - eff,3)
# Variance
var = 0
for k in range(n):
    var1 = p[k]*(lk[k]-L)**2 # Corrected from 1k[K]
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is :{L}")
print(f"Entropy is :{hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is :{red}")
print(f"Variance is :{var}")
```

## CALCULATION:
<img width="542" height="813" alt="Screenshot 2026-05-11 104816" src="https://github.com/user-attachments/assets/2a820094-073b-4f9b-8a34-ab9969e83fdb" />
<img width="540" height="60" alt="Screenshot 2026-05-11 104834" src="https://github.com/user-attachments/assets/8905454f-e0f9-42c6-a371-8847f1bb82b3" />

## OUTPUT:
```
Enter the number of Samples :5
Enter the probability of sample values 1:0.4
Enter the probability of sample values 2:0.2
Enter the probability of sample values 3:0.2
Enter the probability of sample values 4:0.1
Enter the probability of sample values 5:0.1
Enter the length of the sample values 1:2
Enter the length of the sample values 2:2
Enter the length of the sample values 3:2
Enter the length of the sample values 4:3
Enter the length of the sample values 5:3
Average Codeword Length is :2.2
Entropy is :2.122
Efficiency is : 0.965
Redudancy is :0.035
Variance is :0.16
```
## RESULT:
The Huffman and Shannon-Fano of the given statistics {} using python are verified.
