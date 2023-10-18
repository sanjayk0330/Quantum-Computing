# Find the prime numbers

The task was to decompose a given positive integer into a sum of two prime numbers from a given list. For example,

```
Example_1 = find_primes_numbers (18,[2,3,5,7,11,13,17])
18=5+13

Example_2 = find_prime_numbers(32, [2,3,5,7,11,13,17,19])
32=13+19
```
In the file find_prime_numbers.ipynb, we constructed a circuit which is able to accomplish the task. Additionally, the circuit is written 
such that the list is not restricted to only prime numbers. For example,

```
Example_3 = find_primes_numbers (10,[2,3,4,6])
10=4+6
```
The circuit is constructed by using the well-known Grover's Algorithm. The algorithm consists of multiple parts:
1. We apply Hadamard gates to the all 0 states which creates a state of equal superpositions.
2. We use a constructed oracle to mark the solution states.
3. We use a constructed diffusion operator to amplify the correct states determined from the oracle.
4. We repeat Steps 2 and 3 sufficiently many times and measure the result.
From Grover's Algorithm, there is a high probability that we measure the correct state. One of the main difficulties of implementing Grover's Algorithm comes from the construction of the oracle. In order to resolve this, we include 2 ancilla qubits in the register where one ancilla marks whether a state is in the correct set and the other marks whether a state has the correct sum. 
