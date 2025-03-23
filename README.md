
### **Concept Overview**  
A **Priority Encoder** is a combinational circuit that assigns a binary code to the highest-priority active input. It resolves conflicts when multiple inputs are high by encoding only the most significant (highest-priority) input.  

**Example Use Cases:**  
- Interrupt handling in microprocessors  
- Data compression  
- Addressing schemes in memory units  

---

### **Detailed Explanation**  

#### ✅ **4-to-2 Priority Encoder**  
- **Inputs:** `I3, I2, I1, I0` (where `I3` has the highest priority and `I0` has the lowest).  
- **Outputs:** `Y1, Y0` (binary representation of the highest-priority input).  
- **Valid Output (`V`):** Indicates if at least one input is active.  

- **Boolean Expressions:**  
  - `Y1 = I3 + I2`  
  - `Y0 = I3 + (I2' I1)`  
  - `V = I3 + I2 + I1 + I0`  

- **Truth Table:**  

| I3 | I2 | I1 | I0 | Y1 | Y0 | V |
|----|----|----|----|----|----|---|
|  0 |  0 |  0 |  0 |  0 |  0 | 0 |
|  0 |  0 |  0 |  1 |  0 |  0 | 1 |
|  0 |  0 |  1 |  X |  0 |  1 | 1 |
|  0 |  1 | X  |  X |  1 |  0 | 1 |
|  1 | X  | X  |  X |  1 |  1 | 1 |

**Example Application:**  
Used in **CPU interrupt systems**, where multiple interrupt requests are prioritized.

---

### **Code Explanation**  
- **`assign` Statements:** Implements logic equations for priority encoding.  
- **`$monitor` Task:** Displays real-time changes in inputs and outputs.  
- **Test Cases:** Verifies different priority conditions.  

---

### **Execution Steps**  
1. Copy the Verilog code into a simulator (**ModelSim, Xilinx Vivado**).  
2. Compile and run the code.  
3. Observe the priority encoding output behavior.  

---

### **Real-World Example for Practice**  
- **Implement an 8-to-3 Priority Encoder** that can handle 8 interrupt signals and outputs a 3-bit encoded value.  

