# Bernstein-Vazirani Algorithm

## Overview  
The **Bernstein-Vazirani algorithm** is a quantum algorithm that efficiently determines a hidden binary string by querying an oracle only **once**, whereas a classical algorithm would require multiple queries. It showcases quantum speedup by leveraging **superposition** and **interference**.

## Problem Statement  
Given a function \( f: \{0, 1\}^n \to \{0, 1\} \), defined as:

\[
f(x) = s \cdot x \mod 2
\]

where \( s \) is an unknown **n-bit hidden string**, and \( x \) is an \( n \)-bit input. The dot product \( s \cdot x \) is computed modulo 2 as:

\[
s \cdot x = s_0 x_0 \oplus s_1 x_1 \oplus \dots \oplus s_{n-1} x_{n-1}
\]

The task is to determine \( s \) using the fewest queries to \( f \).

## Classical Approach  
A classical algorithm determines \( s \) by querying \( f \) for different values of \( x \):

- Query \( f(100...0) \) to determine \( s_0 \)  
- Query \( f(010...0) \) to determine \( s_1 \)  
- Continue until \( s \) is fully determined  

Thus, the classical approach requires **\( n \) queries**.

## Quantum Approach  
The **Bernstein-Vazirani algorithm** finds \( s \) in **one query** using **Hadamard transforms** and **quantum interference**.

### Steps:
1. **Initialize qubits**:  
   - Start with \( n+1 \) qubits, all initialized to \( |0\rangle \), except the last qubit, which is set to \( |1\rangle \).
   
2. **Apply Hadamard Transform**:  
   - Apply the Hadamard gate to all qubits, putting them into a **superposition of all possible inputs**.

3. **Oracle Query**:  
   - The oracle implements the function \( f(x) \), encoding the hidden string \( s \) into the phase of the quantum state.

4. **Apply Second Hadamard Transform**:  
   - Another Hadamard transform on the first \( n \) qubits **extracts the hidden string \( s \) into the measurement outcome**.

5. **Measure the First \( n \) Qubits**:  
   - The result directly reveals \( s \).

## Quantum Query Complexity  
The **Bernstein-Vazirani algorithm** requires only **one query**, offering an **exponential speedup** over the classical method, which requires \( n \) queries.

## Conclusion  
The **Bernstein-Vazirani algorithm** demonstrates how quantum computers can efficiently extract hidden patterns in a function with a significant speedup over classical methods. Instead of making \( n \) queries, the quantum approach finds the hidden string in just **one query**.
