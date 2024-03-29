## Overview

This project explains Shor's algorithm for factorization, the mathematics principle, link to quantum mechanics and implementation the algorithm with qiskit.  There are 4 chapters where first 3 explain the concept and last chapter is executable jupyter notebook using qiskit.  https://qiskit.org/documentation/getting_started.html provides qiskit installation instruction.

## Content

1. [Chapter 1](01_shors_algorithm.ipynb) describes the steps of Shor's algorithm.
2. [Chapter 2](02_maths.ipynb) explains the mathematics principle of transforming factorization problem to period finding.
3. [Chapter 3](03_find_period.ipynb) shows that given unitary operator to calculate $f_N(x)=a^x \mod N$ and QFT, one can find the period of $f_N(x)$
4. [Chapter 4](04_implement.ipynb) implements QFT and unitary operator $f_N$ with qiskit. 

## Benchmark

Some examples were run with qiskit qasm_simulator on M1 Macbook, Pixelbook and i7-4790 ubuntu PC.  The CPU time grows exponentially with number of qubits.  In the test, N fits within $2^n$ and $x$ in $a^x \mod N$ run over a range of $2^{n_x}$.

Remark *: due to unknown reason, allocate (n, nx)=(4, 8) qubits caused M1 and i7-4790 run forever while (n, nx)=(5, 8) run normally.

| Qubits (n, nx) | N   | a | M1      | Pixelbook | i7-4790 |
|----------------|-----|---|---------|-----------|---------|
| 4,8 *          | 15  | 7 |         | 1m12s     |         |
| 5,8 *          | 15  | 7 | 22s     | 2m29s     | 36s     | 
| 6,12           | 55  | 7 | 1m52s   | 6m36s     | 2m13s   |
| 8,16           | 221 | 7 | 45m58s  | 82m09s    | 25m20s  |
| 9,18           | 437 | 7 | 252m26s | 465m24s   | 181m54s |
| 10,20          | 851 | 7 |         |           | 8080m   |

## References

N. David Mermin, Quantum Computer Science: An Introduction

[Vlatko Vedral, Adriano Barenco and Artur Ekert, Quantum Networks for Elementary Arithmetic Operations](https://arxiv.org/abs/quant-ph/9511018)

[Stackexchange, Is there a simple, formulaic way to construct a modular exponentiation circuit?](https://quantumcomputing.stackexchange.com/questions/6842/is-there-a-simple-formulaic-way-to-construct-a-modular-exponentiation-circuit)

[Qiskit get start](https://qiskit.org/documentation/getting_started.html)