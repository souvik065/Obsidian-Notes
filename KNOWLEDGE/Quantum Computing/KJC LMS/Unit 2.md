

# What is a Hadamard gate? [¶](https://pennylane.ai/qml/glossary/what-is-a-hadamard-gate#what-is-a-hadamard-gate)

The **Hadamard gate** is a gate in quantum computing that turns a state of |0⟩|0⟩ or |1⟩|1⟩ into an equal superposition of |0⟩|0⟩ and |1⟩.|1⟩.

---

Learn about [Hadamard gates in the PennyLane Codebook](https://pennylane.ai/codebook/02-single-qubit-gates/01-x-and-h/).

In a circuit diagram, a Hadamard gate is represented by a square with the letter ‘H’ in it, as shown below.

![hadamard-gate-symbol](https://pennylane.ai/static/20c9f3022898d5b867e7e4295c6f92d3/f058b/hadamard-gate-symbol.png "hadamard-gate-symbol")

A Hadamard gate can be represented in matrix form as

H≡1√2[111−1].H≡12[111−1].

If the input state is |0⟩|0⟩, the Hadamard gate turns it into (|0⟩+|1⟩)/√2(|0⟩+|1⟩)/2. If the input state is |1⟩|1⟩, the Hadamard gate turns it into a state of (|0⟩−|1⟩)/√2(|0⟩−|1⟩)/2.

The square of the Hadamard gate is just the identity gate: H2=IH2=I. Thus, applying the Hadamard gate to the same qubit twice in a row has no effect on it.




## Pauli-X Gate

### **Pauli-X Gate in Quantum Computing**

The **Pauli-X gate (X gate)** is a fundamental quantum gate that acts as the quantum equivalent of the **classical NOT gate**. It flips a qubit’s state from **|0⟩ to |1⟩** and vice versa.

---

### **1. Mathematical Representation**

The **Pauli-X gate** is represented by the matrix:

X=[0110]

---

### **2. Effect on Basis States**

1. **Flipping |0⟩ to |1⟩:**
    
    X∣0⟩=[0110][10]=[01]=∣1⟩
2. **Flipping |1⟩ to |0⟩:**
    
    X∣1⟩=[0110][01]=[10]=∣0⟩

---



## Pauli-Y Gate

### **Pauli-Y Gate in Quantum Computing**

The **Pauli-Y gate (Y gate)** is one of the three fundamental **Pauli gates** (**X, Y, Z**) in quantum computing. It performs a **π (180°) rotation around the Y-axis** of the Bloch Sphere and introduces a phase shift.

---

### **1. Mathematical Representation**

The **Pauli-Y gate** is represented by the matrix:

Y=[0−ii0]

where **i** is the imaginary unit (**i² = -1**).

---

### **2. Effect on Basis States**

1. **Flipping |0⟩ to -i|1⟩**
    
    Y∣0⟩=[0−ii0][10]=[0i]=i∣1⟩
2. **Flipping |1⟩ to i|0⟩**
    
    Y∣1⟩=[0−ii0][01]=[−i0]=−i∣0⟩

Unlike the **[Pauli-X gate](https://www.kristujayantiexamlms.com/mod/lesson/view.php?id=223792 "Pauli-X Gate")**, which simply swaps |0⟩ and |1⟩, the **Pauli-Y gate introduces a phase factor of ±i**.

---

###   

---

### **3. Key Properties**

1. **Self-Inverse**:
    
    - Applying **Y twice** returns the qubit to its original state:YY=Iwhere **I** is the identity matrix.
2. **Relation to Other Pauli Gates**:
    
    - **Pauli-X:** Swaps |0⟩ and |1⟩ without a phase shift.
    - **Pauli-Z:** Keeps |0⟩ unchanged but flips the phase of **|1⟩**.
    - **Y = iXZ**, meaning it is a combination of **X and Z** gates with an imaginary factor.
      
      



## Pauli-Z Gate

### **Pauli-Z Gate in Quantum Computing**

The **Pauli-Z gate (Z gate)** is one of the fundamental **Pauli matrices** used in quantum computing. It is also known as the **phase-flip gate** because it affects the phase of the qubit without changing its probability distribution.

---

### **1. Mathematical Representation**

The **Pauli-Z gate** is represented by the matrix:

Z=[100−1]

---

### **2. Effect on Basis States**

1. **|0⟩ remains unchanged:**
    
    Z∣0⟩=[100−1][10]=[10]=∣0⟩
2. **|1⟩ gets a phase flip (-1 factor):**
    
    Z∣1⟩=[100−1][01]=[0−1]=−∣1⟩

Unlike **Pauli-X (which swaps |0⟩ and |1⟩)**, the **Pauli-Z gate keeps the states in place but flips the sign of |1⟩**.

---

### **3. Key Properties**2

1. **Self-Inverse**:
	 Applying **Z twice** returns the qubit to its original state:ZZ=Iwhere **I** is the identity matrix.
	 
2. **Relation to Other Pauli Gates**:
    
    - **Pauli-X:** Swaps |0⟩ and |1⟩ (bit-flip).
    - **Pauli-Y:** Combines both X and Z with an imaginary factor.
    - **Z = iYX**, meaning it can be expressed as a combination of the other two Pauli matrices.
      
      
      


## Quantum Circuit

![](https://www.kristujayantiexamlms.com/pluginfile.php/483047/mod_lesson/intro/H%20gate%20and%20CNOT%20gate.JPG)