## Overview

This project explains Shor's algorithm for factorization, the mathematics principle, link to quantum mechanics and implementation the algorithm with qiskit.  There are 4 chapters where first 3 explain the concept and last chapter are executable jupyter notebook using qiskit.  https://qiskit.org/documentation/getting_started.html provides qiskit installation instruction.

## Content

1. [Chapter 1](01_shors_algorithm.ipynb) describes the steps of Shor's algorithm.
2. [Chapter 2](02_maths.ipynb) explains the mathematics principle of transforming factorization problem to period finding.
3. [Chapter 3](03_find_period.ipynb) shows that given unitary operator to calculate $f_N(x)=a^x \mod N$ and QFT, one can find the period of $f_N(x)$
4. [Chapter 4](04_implement.ipynb) implements QFT and unitary operator $f_N$ with qiskit. 

## Benchmark

| Qubits (n, nx) | N   | a | M1      | Pixelbook | i7-4790 |
|----------------|-----|---|---------|-----------|---------|
| 4,8            | 15  | 7 |         |           |         |
| 5,8            | 15  | 7 | 23s     |           | 36s     | 
| 6,12           | 55  | 7 | 1m49s   |           | 2m13s   |
| 8,16           | 221 | 7 | 36m31s  |           | 25m20s  |
| 9,18           | 437 | 7 | 264m45s |           | 181m54s |
| 10,20          | 851 | 7 |         |           |         |