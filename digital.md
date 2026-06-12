# ASSIGNMENT 2 SOLUTIONS
## Digital Electronics - ETU 07425
**Date: 5 June 2026**

---

# QUESTION ONE: Adders and Subtractors Using NAND & NOR Gates

## i. Half Adder using NAND Gates

### Truth Table for Half Adder:
| A | B | Sum | Carry |
|---|---|-----|-------|
| 0 | 0 |  0  |   0   |
| 0 | 1 |  1  |   0   |
| 1 | 0 |  1  |   0   |
| 1 | 1 |  0  |   1   |

### Boolean Expressions:
- **Sum** = A ⊕ B = A'B + AB'
- **Carry** = A·B

### Implementation using NAND Gates:
- **Sum** = (A NAND A) NAND (B NAND B) NAND (A NAND B) 
  - This uses the NAND gate implementation of XOR
- **Carry** = (A NAND B) NAND (A NAND B) = A·B
  - The carry is directly obtained by NOR-ing the outputs of A and B through NAND gates

**Logic Circuit:** The circuit uses 5 NAND gates - three for the sum output and two for the carry output.

---

## ii. Full Adder using NAND Gates

### Truth Table for Full Adder:
| A | B | Cin | Sum | Cout |
|---|---|-----|-----|------|
| 0 | 0 |  0  |  0  |  0   |
| 0 | 0 |  1  |  1  |  0   |
| 0 | 1 |  0  |  1  |  0   |
| 0 | 1 |  1  |  0  |  1   |
| 1 | 0 |  0  |  1  |  0   |
| 1 | 0 |  1  |  0  |  1   |
| 1 | 1 |  0  |  0  |  1   |
| 1 | 1 |  1  |  1  |  1   |

### Boolean Expressions:
- **Sum** = A ⊕ B ⊕ Cin
- **Cout** = AB + BCin + ACin

### Implementation using NAND Gates:
The full adder can be implemented using two cascaded half adders with NAND gates:
- First Half Adder: inputs A and B
- Second Half Adder: inputs (A⊕B) and Cin
- Carry output uses NAND implementation of the carry expressions

**Logic Circuit:** The circuit uses multiple NAND gates to implement both the sum and carry-out functions.

---

## iii. Half Subtractor using NOR Gates

### Truth Table for Half Subtractor:
| A | B | Difference | Borrow |
|---|---|------------|--------|
| 0 | 0 |     0      |   0    |
| 0 | 1 |     1      |   1    |
| 1 | 0 |     1      |   0    |
| 1 | 1 |     0      |   0    |

### Boolean Expressions:
- **Difference (D)** = A ⊕ B = A'B + AB'
- **Borrow (Bout)** = A'B

### Implementation using NOR Gates:
The half subtractor uses NOR gate combinations to create:
- The difference output using a configuration equivalent to XNOR followed by NOT
- The borrow output directly from the NOR gate logic

**Logic Circuit:** The circuit uses NOR gates to implement both outputs.

---

## iv. Full Subtractor using NOR Gates

### Truth Table for Full Subtractor:
| A | B | Bin | Difference | Bout |
|---|---|-----|------------|------|
| 0 | 0 |  0  |     0      |  0   |
| 0 | 0 |  1  |     1      |  1   |
| 0 | 1 |  0  |     1      |  1   |
| 0 | 1 |  1  |     0      |  1   |
| 1 | 0 |  0  |     1      |  0   |
| 1 | 0 |  1  |     0      |  0   |
| 1 | 1 |  0  |     0      |  0   |
| 1 | 1 |  1  |     1      |  1   |

### Boolean Expressions:
- **Difference** = A ⊕ B ⊕ Bin
- **Bout** = A'B + Bin(A' + B) = A'B + A'Bin + BBin

### Implementation using NOR Gates:
Using DeMorgan's theorem and NOR gate combinations to implement the required Boolean expressions.

**Logic Circuit:** The circuit uses multiple NOR gates configured to produce both the difference and borrow outputs.

---

# QUESTION TWO: Adder/Subtractor and Propagation Delay

## i. Adder/Subtractor for Addition and Subtraction of 7 from 12

### Operation Requirements:
- **Addition:** 12 + 7 = 19
- **Subtraction:** 12 - 7 = 5

### Binary Representations:
- 12 in binary: 1100
- 7 in binary: 0111

### For Addition (12 + 7):
```
  1100 (12)
+ 0111 (7)
-------
 10011 (19)
```

### For Subtraction (12 - 7):
```
  1100 (12)
- 0111 (7)
-------
  0101 (5)
```

### Logic Circuit Design:
An **4-bit adder/subtractor** uses:
- A control signal **M** where:
  - M = 0 for addition
  - M = 1 for subtraction
- When M = 1, the B input is complemented (using XOR gates with M as one input)
- When M = 1 and adding 1 (two's complement), the Cin is set to 1
- The circuit uses cascaded Full Adders for each bit position

### Circuit Configuration:
```
For each bit position i:
  - XOR gate: B'i = Bi ⊕ M (inverts B when M=1)
  - Full Adder: Sumi = Ai ⊕ B'i ⊕ Cin_i
```

---

## ii. Propagation Delay in 4-bit Adder

### Given Data:
- EX-OR gate propagation delay = **10 ns**
- AND/OR gate propagation delay = **5 ns**

### Critical Path Analysis:

For a Full Adder, the critical path is through the carry chain:
- **Delay per stage** = AND gate (5 ns) + OR gate (5 ns) = 10 ns
- For carry generation: Ci = Gi + Pi·Ci-1

### 4-bit Ripple Adder Delay Calculation:

**Critical path includes:**
1. First bit: AND (5 ns) + OR (5 ns) = 10 ns
2. Second bit carry: AND (5 ns) + OR (5 ns) + (previous carry) = 10 ns
3. Third bit carry: Additional 10 ns propagation
4. Fourth bit carry: Additional 10 ns propagation

**Total propagation delay = 3 × 10 ns + 10 ns = 40 ns**

### More Detailed Analysis:
For each full adder stage:
- **Carry generation:** Gi = Ai·Bi (AND gate: 5 ns)
- **Propagate:** Pi = Ai ⊕ Bi (XOR gate: 10 ns)
- **Carry out:** Ci+1 = Gi + Pi·Ci (OR gate + AND gate in chain)

**Maximum delay through 4 stages = 10 ns (first AND) + 3×(5+5) ns + additional logic = approximately 40 ns**

---

## iii. 4-bit Comparator Design

### Purpose:
A 4-bit comparator compares two 4-bit numbers A = A3A2A1A0 and B = B3B2B1B0 to determine:
- A > B
- A = B
- A < B

### Design Method using XNOR Gates:

For each bit position i, define:
**Ei = Ai ⊙ Bi = A'iB'i + AiBi** (XNOR gate output - 1 when bits are equal)

### Boolean Expressions:

**For Equality (A = B):**
```
A = B if all bits are equal:
(A = B) = E3·E2·E1·E0
```

**For A > B (Priority: MSB first):**
```
A > B = A3B'3 + E3A2B'2 + E3E2A1B'1 + E3E2E1A0B'0
```

**For A < B:**
```
A < B = A'3B3 + E3A'2B2 + E3E2A'1B1 + E3E2E1A'0B0
```

### Logic Circuit Implementation:
1. **XNOR gates** for each bit to generate equality signals (E0, E1, E2, E3)
2. **AND gates** for each comparison term
3. **OR gates** to combine terms for final outputs

The circuit requires:
- 4 XNOR gates (for equality of each bit)
- Multiple AND gates (for comparison logic)
- 3 OR gates (for A>B, A=B, A<B outputs)

---

# QUESTION THREE: Code Converters

## i. Excess-3 to BCD Converter

### Truth Table (Excess-3 to BCD):

| Excess-3 | BCD  | E3 | E2 | E1 | E0 | B3 | B2 | B1 | B0 |
|----------|------|----|----|----|----|----|----|----|----|
| 0011     | 0000 | 0  | 0  | 1  | 1  | 0  | 0  | 0  | 0  |
| 0100     | 0001 | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 1  |
| 0101     | 0010 | 0  | 1  | 0  | 1  | 0  | 0  | 1  | 0  |
| 0110     | 0011 | 0  | 1  | 1  | 0  | 0  | 0  | 1  | 1  |
| 0111     | 0100 | 0  | 1  | 1  | 1  | 0  | 1  | 0  | 0  |
| 1000     | 0101 | 1  | 0  | 0  | 0  | 0  | 1  | 0  | 1  |
| 1001     | 0110 | 1  | 0  | 0  | 1  | 0  | 1  | 1  | 0  |
| 1010     | 0111 | 1  | 0  | 1  | 0  | 0  | 1  | 1  | 1  |
| 1011     | 1000 | 1  | 0  | 1  | 1  | 1  | 0  | 0  | 0  |
| 1100     | 1001 | 1  | 1  | 0  | 0  | 1  | 0  | 0  | 1  |

### Unused Combinations (Don't Care):
- 0000, 0001, 0010 (< 3)
- 1101, 1110, 1111 (> 12)
These are used as don't care conditions (X) in K-map simplification.

### Boolean Expressions (Simplified):
- **B3** = E3·E2 + E3·E1
- **B2** = E3'·E2'·E1 + E3·E2·E1'
- **B1** = E2 ⊕ E1
- **B0** = E0'

### Logic Circuit:
Uses 4 decoder outputs and logic gates to convert the Excess-3 code to standard BCD.

---

## ii. Gray to Binary Code Converter

### Truth Table (Gray Code to Binary):

| Gray Code | Binary | G3 | G2 | G1 | G0 | B3 | B2 | B1 | B0 |
|-----------|--------|----|----|----|----|----|----|----|----|
| 0000      | 0000   | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  |
| 0001      | 0001   | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 1  |
| 0011      | 0010   | 0  | 0  | 1  | 1  | 0  | 0  | 1  | 0  |
| 0010      | 0011   | 0  | 0  | 1  | 0  | 0  | 0  | 1  | 1  |
| 0110      | 0100   | 0  | 1  | 1  | 0  | 0  | 1  | 0  | 0  |
| 0111      | 0101   | 0  | 1  | 1  | 1  | 0  | 1  | 0  | 1  |
| 0101      | 0110   | 0  | 1  | 0  | 1  | 0  | 1  | 1  | 0  |
| 0100      | 0111   | 0  | 1  | 0  | 0  | 0  | 1  | 1  | 1  |
| 1100      | 1000   | 1  | 1  | 0  | 0  | 1  | 0  | 0  | 0  |
| 1101      | 1001   | 1  | 1  | 0  | 1  | 1  | 0  | 0  | 1  |
| 1111      | 1010   | 1  | 1  | 1  | 1  | 1  | 0  | 1  | 0  |
| 1110      | 1011   | 1  | 1  | 1  | 0  | 1  | 0  | 1  | 1  |
| 1010      | 1100   | 1  | 0  | 1  | 0  | 1  | 1  | 0  | 0  |
| 1011      | 1101   | 1  | 0  | 1  | 1  | 1  | 1  | 0  | 1  |
| 1001      | 1110   | 1  | 0  | 0  | 1  | 1  | 1  | 1  | 0  |
| 1000      | 1111   | 1  | 0  | 0  | 0  | 1  | 1  | 1  | 1  |

### Conversion Formula:
- **B3** = G3
- **B2** = B3 ⊕ G2
- **B1** = B2 ⊕ G1
- **B0** = B1 ⊕ G0

### Example: Convert Gray Code (1001101) to Binary

**Given:** Gray code = 1001101 (7-bit)

**Step-by-step conversion:**
- G6 = 1, G5 = 0, G4 = 0, G3 = 1, G2 = 1, G1 = 0, G0 = 1
- B6 = G6 = 1
- B5 = B6 ⊕ G5 = 1 ⊕ 0 = **1**
- B4 = B5 ⊕ G4 = 1 ⊕ 0 = **1**
- B3 = B4 ⊕ G3 = 1 ⊕ 1 = **0**
- B2 = B3 ⊕ G2 = 0 ⊕ 1 = **1**
- B1 = B2 ⊕ G1 = 1 ⊕ 0 = **1**
- B0 = B1 ⊕ G0 = 1 ⊕ 1 = **0**

**Binary Result:** 1110110

### Logic Circuit:
The circuit uses cascaded XOR gates in a serial arrangement, where each output depends on the previous stage's output and the next Gray code input.

---

## iii. Binary to Gray Code Converter

### Conversion Formula:
- **G3** = B3
- **G2** = B3 ⊕ B2
- **G1** = B2 ⊕ B1
- **G0** = B1 ⊕ B0

### Example: Convert Binary (1011) to Gray Code

**Given:** Binary = 1011

**Step-by-step conversion:**
- B3 = 1, B2 = 0, B1 = 1, B0 = 1
- G3 = B3 = **1**
- G2 = B3 ⊕ B2 = 1 ⊕ 0 = **1**
- G1 = B2 ⊕ B1 = 0 ⊕ 1 = **1**
- G0 = B1 ⊕ B0 = 1 ⊕ 1 = **0**

**Gray Code Result:** 1110

### Verification:
The result 1110 (Gray) converts back to 1011 (Binary) using the Gray-to-Binary conversion.

### Logic Circuit:
Uses cascaded XOR gates where:
- First XOR: B3 directly goes to G3
- Subsequent XORs: Each compares adjacent binary bits

---

# QUESTION FOUR: Multiplexer and Demultiplexer Design

## i. Implementation of (A EXNOR B EXOR C) using 8×1 MUX

### Truth Table:

| A | B | C | A EXNOR B | Result (EXNOR⊕C) |
|---|---|---|-----------|------------------|
| 0 | 0 | 0 |     1     |        1         |
| 0 | 0 | 1 |     1     |        0         |
| 0 | 1 | 0 |     0     |        0         |
| 0 | 1 | 1 |     0     |        1         |
| 1 | 0 | 0 |     0     |        0         |
| 1 | 0 | 1 |     0     |        1         |
| 1 | 1 | 0 |     1     |        1         |
| 1 | 1 | 1 |     1     |        0         |

### MUX Implementation:
Using an 8×1 multiplexer with A, B, C as select lines:

**Input Configuration:**
- I0 = 1 (for A=0, B=0, C=0)
- I1 = 0 (for A=0, B=0, C=1)
- I2 = 0 (for A=0, B=1, C=0)
- I3 = 1 (for A=0, B=1, C=1)
- I4 = 0 (for A=1, B=0, C=0)
- I5 = 1 (for A=1, B=0, C=1)
- I6 = 1 (for A=1, B=1, C=0)
- I7 = 0 (for A=1, B=1, C=1)

**MUX Output:** Y = S2'S1'S0'I0 + S2'S1'S0I1 + ... + S2S1S0I7

Where S2=C, S1=B, S0=A for proper encoding.

---

## ii. Implement F = Σ(1,2,3,6,7) using MUX

### Truth Table:

| A | B | C | F |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 1 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |
| 1 | 1 | 1 | 1 |

### MUX Implementation with Select Lines A, B, C:

**Input Configuration for 8×1 MUX:**
- I0 = 0 (for ABC=000)
- I1 = 1 (for ABC=001)
- I2 = 1 (for ABC=010)
- I3 = 1 (for ABC=011)
- I4 = 0 (for ABC=100)
- I5 = 0 (for ABC=101)
- I6 = 1 (for ABC=110)
- I7 = 1 (for ABC=111)

**Output Expression:**
F = A'B'C'·0 + A'B'C·1 + A'BC'·1 + A'BC·1 + AB'C'·0 + AB'C·0 + ABC'·1 + ABC·1

Simplified: F = A'B'C + A'BC' + A'BC + ABC' + ABC

---

## iii. Design a Demultiplexer using Full Adder

### 1×4 DEMUX using Full Adders:

**Inputs:**
- Data input: **D** (signal to be distributed)
- Select lines: **S1, S0** (2-bit select for 4 outputs)

**Outputs:** Y0, Y1, Y2, Y3

### Truth Table:

| S1 | S0 | Y0     | Y1     | Y2     | Y3     |
|----|----|----|----|----|----| 
| 0  | 0  | D  | 0  | 0  | 0  |
| 0  | 1  | 0  | D  | 0  | 0  |
| 1  | 0  | 0  | 0  | D  | 0  |
| 1  | 1  | 0  | 0  | 0  | D  |

### Boolean Expressions:
- **Y0** = D·S1'·S0'
- **Y1** = D·S1'·S0
- **Y2** = D·S1·S0'
- **Y3** = D·S1·S0

### Implementation using Full Adders:
Full Adders can be configured as logic elements by setting appropriate control inputs:
- The Carry-in and Sum outputs of Full Adders implement AND/OR logic
- Multiple Full Adders are cascaded to create the demultiplexer outputs
- Select lines control which Full Adder generates output for the data signal

### Logic Circuit:
The circuit uses Full Adders configured to function as combinatorial logic gates, with:
- Select lines feeding into the control inputs
- Data input feeding into all Full Adders
- OR-ing appropriate outputs to generate Y0-Y3

---

# QUESTION FIVE: Encoders and Decoders

## i. 8×3 Priority Encoder Design

### Truth Table:

| D7 | D6 | D5 | D4 | D3 | D2 | D1 | D0 | Y2 | Y1 | Y0 | V |
|----|----|----|----|----|----|----|----|----|----|----|---|
| 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 1 |
| 0  | 0  | 0  | 0  | 0  | 0  | 1  | X  | 0  | 0  | 1  | 1 |
| 0  | 0  | 0  | 0  | 0  | 1  | X  | X  | 0  | 1  | 0  | 1 |
| 0  | 0  | 0  | 0  | 1  | X  | X  | X  | 0  | 1  | 1  | 1 |
| 0  | 0  | 0  | 1  | X  | X  | X  | X  | 1  | 0  | 0  | 1 |
| 0  | 0  | 1  | X  | X  | X  | X  | X  | 1  | 0  | 1  | 1 |
| 0  | 1  | X  | X  | X  | X  | X  | X  | 1  | 1  | 0  | 1 |
| 1  | X  | X  | X  | X  | X  | X  | X  | 1  | 1  | 1  | 1 |

(Where V is the Valid output - 1 when at least one input is high)

### Boolean Expressions:
- **Y2** = D7 + D6 + D5 + D4
- **Y1** = D7 + D6 + D3 + D2
- **Y0** = D7 + D5 + D3 + D1
- **Valid (V)** = D7 + D6 + D5 + D4 + D3 + D2 + D1 + D0

### Logic Circuit:
Uses multiple OR gates:
- Three 8-input OR gates for Y2, Y1, Y0 respectively
- Each OR gate has specific input combinations
- Priority is highest for D7 (MSB) and lowest for D0 (LSB)

---

## ii. Decimal to BCD Encoder

### Circuit Purpose:
Converts one of 10 decimal inputs (D0-D9) into its 4-bit BCD representation.

### Truth Table:

| Digit | D9 | D8 | D7 | D6 | D5 | D4 | D3 | D2 | D1 | D0 | B3 | B2 | B1 | B0 |
|-------|----|----|----|----|----|----|----|----|----|----|----|----|----| 
| 0     | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  |
| 1     | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 1  |
| 2     | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 1  | 0  |
| 3     | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 1  | 1  |
| 4     | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  |
| 5     | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 1  |
| 6     | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 1  | 0  |
| 7     | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 1  | 1  |
| 8     | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  |
| 9     | 1  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 1  |

### Boolean Expressions:
- **B3** = D8 + D9
- **B2** = D4 + D5 + D6 + D7
- **B1** = D2 + D3 + D6 + D7
- **B0** = D1 + D3 + D5 + D7 + D9

### Logic Circuit:
Uses 4 OR gates where:
- B3 is a 2-input OR gate (OR of D8 and D9)
- B2, B1, B0 are 4 or 5-input OR gates with appropriate inputs

---

## iii. Full Adder using Decoder

### Principle:
A 3×8 decoder generates 8 minterms (one for each input combination). These minterms can be ORed appropriately to generate the Sum and Carry-out outputs of a Full Adder.

### Truth Table with Decoder Outputs:

| A | B | Cin | Decoder Output | Sum | Cout |
|---|---|-----|----------------|-----|------|
| 0 | 0 | 0   | Y0=1, others=0 | 0   | 0    |
| 0 | 0 | 1   | Y1=1, others=0 | 1   | 0    |
| 0 | 1 | 0   | Y2=1, others=0 | 1   | 0    |
| 0 | 1 | 1   | Y3=1, others=0 | 0   | 1    |
| 1 | 0 | 0   | Y4=1, others=0 | 1   | 0    |
| 1 | 0 | 1   | Y5=1, others=0 | 0   | 1    |
| 1 | 1 | 0   | Y6=1, others=0 | 0   | 1    |
| 1 | 1 | 1   | Y7=1, others=0 | 1   | 1    |

### Boolean Expressions from Decoder Outputs:
- **Sum** = Y1 + Y2 + Y4 + Y7
- **Cout** = Y3 + Y5 + Y6 + Y7

### Logic Circuit Implementation:
1. **3×8 Decoder:** Takes A, B, Cin as inputs and generates Y0-Y7
2. **OR Gates:**
   - 4-input OR gate for Sum (OR of Y1, Y2, Y4, Y7)
   - 4-input OR gate for Cout (OR of Y3, Y5, Y6, Y7)

---

## iv. BCD to 7-Segment Display Decoder for Number 5

### 7-Segment Display Labeling:
```
     a
   -----
  |     |
  f     b
  |     |
   -----
    g
  |     |
  e     c
  |     |
   -----
     d
```

### For Displaying Decimal Number 5:

**BCD Input:** 0101 (where A=0, B=1, C=0, D=1)

**Segments to Illuminate:**
- **a** = 1 (top horizontal)
- **b** = 0 (top-right vertical) - OFF
- **c** = 1 (bottom-right vertical)
- **d** = 1 (bottom horizontal)
- **e** = 0 (bottom-left vertical) - OFF
- **f** = 1 (top-left vertical)
- **g** = 1 (middle horizontal)

**Display Output:** The segments create the visual: **5**

### Complete Truth Table for BCD to 7-Segment (All Digits 0-9):

| Digit | A | B | C | D | a | b | c | d | e | f | g |
|-------|---|---|---|---|---|---|---|---|---|---|---|
| 0     | 0 | 0 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 |
| 1     | 0 | 0 | 0 | 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
| 2     | 0 | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
| 3     | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 1 |
| 4     | 0 | 1 | 0 | 0 | 0 | 1 | 1 | 0 | 0 | 1 | 1 |
| 5     | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 1 |
| 6     | 0 | 1 | 1 | 0 | 1 | 0 | 1 | 1 | 1 | 1 | 1 |
| 7     | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |
| 8     | 1 | 0 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 9     | 1 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 0 | 1 | 1 |

### Boolean Expressions for 7-Segment Outputs:

**Using Karnaugh Map Simplification:**

- **a** = A + C + B·D + B'·D'
- **b** = B' + C·D + C'·D'
- **c** = C + D + B
- **d** = B·D + B'·D' + C·D' + B·C
- **e** = B'·D' + C·D'
- **f** = A + C·D' + B·C + C'·D
- **g** = A + B·D + B'·C + B·C'

### Logic Circuit Design:
The decoder consists of:
1. **Input Stage:** Four BCD inputs (A, B, C, D)
2. **Logic Gates:** Multiple AND, OR, and NOT gates implementing the above expressions
3. **Output Stage:** Seven outputs (a-g) for LED segment control

Total gates required: approximately 25-30 logic gates depending on implementation.

---

## Summary of Key Formulas

### Adders/Subtractors:
- Half Adder Sum: A ⊕ B
- Full Adder Sum: A ⊕ B ⊕ Cin
- Full Adder Cout: AB + BCin + ACin
- Full Subtractor: Similar but with complemented inputs for subtraction

### Code Conversions:
- Gray to Binary: Bn = Gn XOR Bn+1
- Binary to Gray: Gn = Bn XOR Bn-1

### Propagation Delay:
- Ripple Adder (4-bit): ~40 ns with given gate delays
- Critical path through carry chain: 3 × (AND + OR) stages

### Encoder/Decoder Logic:
- Priority Encoder: OR gates combining appropriate inputs
- Decoder: Implements minterms, outputs ORed for final functions

---

**End of Solutions**
