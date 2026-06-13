# Teaching Guide

## Suggested Use

This project can be used as an introductory demonstration after students have learned:

- classical bits and binary numbers;
- qubits;
- basic quantum gates;
- measurement;
- the idea of superposition.

Estimated classroom duration: **45 to 60 minutes**.

## Suggested Teaching Flow

| Time | Topic | Teaching focus |
|---:|---|---|
| 5 min | Castle-room analogy | Introduce the search problem |
| 5 min | Classical linear search | Explain worst-case checking |
| 10 min | Two-qubit representation | Map four rooms to four basis states |
| 10 min | Superposition | Explain equal probabilities before search |
| 10 min | Oracle | Emphasize phase marking, not immediate discovery |
| 10 min | Diffusion | Explain inversion around the average |
| 5 min | Measurement | Interpret `11` as the treasure room |
| 5 min | Scaling chart | Discuss `O(N)` vs. `O(√N)` query complexity |

## Recommended Explanation

Use this sequence:

> Superposition prepares the possibilities.  
> The oracle marks the correct state.  
> Diffusion uses interference to amplify the marked state.  
> Measurement converts the final quantum state into a classical result.

## Important Classroom Questions

### 1. Does superposition mean that the answer has already been found?

No. Immediately after creating the equal superposition, every room has the same probability. Measurement at that stage would return a random room.

### 2. Does the oracle directly increase the probability of the treasure room?

No. The oracle changes the phase of the target state's amplitude. The probability remains unchanged immediately after the oracle.

### 3. Why is the negative sign useful?

The diffusion operator uses interference. It reflects amplitudes around their average value and amplifies the marked state.

### 4. Why is the pipeline called hybrid?

Classical Python code defines the problem and interprets the measured output. Quantum gates perform the state preparation, phase marking, amplitude amplification and measurement.

### 5. Is the local simulation automatically faster than classical search?

No. The simulator itself runs on classical hardware. The notebook explains Grover's search-query scaling rather than real runtime performance.

## Common Misconceptions to Address

| Misconception | Clarification |
|---|---|
| A quantum computer opens every room and shows every answer | Measurement returns a classical outcome; the circuit must amplify useful states before measurement |
| The oracle reveals the answer immediately | It marks the target through a phase change |
| Negative amplitude means negative probability | Probability is obtained from the squared magnitude of amplitude |
| A simulator proves hardware speedup | A simulator reproduces circuit behaviour using classical hardware |
| Grover's algorithm gives exponential speedup | It provides a quadratic improvement for suitable unstructured-search problems |

## Classroom Activity

Ask students to calculate the post-oracle average amplitude:

```text
(+0.50 + 0.50 + 0.50 − 0.50) ÷ 4 = +0.25
```

Then apply:

```text
new amplitude = 2 × average amplitude − old amplitude
```

Expected result:

| Room state | Old amplitude | New amplitude |
|---|---:|---:|
| `|00⟩` | `+0.50` | `0.00` |
| `|01⟩` | `+0.50` | `0.00` |
| `|10⟩` | `+0.50` | `0.00` |
| `|11⟩` | `−0.50` | `+1.00` |

## Optional Follow-Up Exercise

Ask students to explore how the oracle changes when the treasure is hidden in another state:

- `|00⟩`
- `|01⟩`
- `|10⟩`

Students should verify the result using the statevector before moving to measurement.

## Teaching Reflection

The castle-room analogy is helpful because it keeps the search problem concrete while gradually introducing amplitudes, phase marking and interference. The notebook should be taught step by step rather than executed all at once.
