# Project Summary

## Title

**Hybrid Classical–Quantum Search Demo: Understanding Grover's Algorithm Through a Castle-Room Example**

## Objective

This project demonstrates a small hybrid classical–quantum search pipeline using Qiskit. It is designed as an introductory teaching example and as a clear portfolio project for learners exploring quantum computing.

## Problem Statement

A prince wants to find a treasure hidden in one of four castle rooms. A classical linear search may open the rooms one by one. The quantum workflow represents the rooms using two qubits, marks the treasure room with an oracle, amplifies its probability through interference and interprets the measured result using classical Python code.

## Technical Components

| Component | Purpose |
|---|---|
| Python | Classical search logic and interpretation of measurement results |
| Qiskit | Construction of quantum circuits |
| Qiskit Aer | Local ideal simulation |
| Statevector | Inspection of amplitudes before measurement |
| Matplotlib | Scaling-comparison visualization |
| Jupyter Notebook | Step-by-step teaching and experimentation |

## Hybrid Workflow

| Stage | Computing type | Role |
|---|---|---|
| Define room labels | Classical | Prepare the search problem |
| Select treasure room | Classical | Define the target |
| Create superposition | Quantum | Represent all possible rooms |
| Apply oracle | Quantum | Mark `|11⟩` through a phase flip |
| Apply diffusion operator | Quantum | Amplify the marked state |
| Measure circuit | Quantum | Produce classical bits |
| Interpret result | Classical | Convert `11` to `Room 3 — Treasure Room` |
| Visualize result | Classical | Display counts and charts |

## Result

Using an ideal local simulator with `1024` shots:

```text
{'11': 1024}
```

The target room is identified as:

```text
Room 3 — Treasure Room
```

## Key Learning Point

Quantum search is not simply about representing multiple possibilities. The essential idea is to manipulate amplitudes so that useful answers become more likely during measurement.

## Limitations

This is an educational two-qubit demonstration. It does not claim a real-hardware runtime advantage. The comparison focuses on search-query complexity.

## Possible Extensions

- alternative treasure rooms;
- larger search spaces;
- multiple marked states;
- noisy simulation;
- quantum-hardware execution;
- reusable Grover-operator utilities.
