# Bernstein-Vazirani Algorithm

## Overview  
The **Bernstein-Vazirani algorithm** is a quantum algorithm that efficiently determines a hidden binary string by querying an oracle only **once**, whereas a classical algorithm would require multiple queries.

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
