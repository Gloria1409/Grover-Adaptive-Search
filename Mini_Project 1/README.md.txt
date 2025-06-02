# Grover Adaptive Search

This project implements a quantum oracle circuit for Grover Adaptive Search, tailored for constrained pseudo-Boolean optimization, as described in:

**"Grover Adaptive Search for Constrained Polynomial Binary Optimization"**

## Problem Definition

Construct a unitary oracle $ U_{f,t,C} $ such that:

$
U_{f,t,C} \ket{x}_n \ket{y}_1 =
\begin{cases}
\ket{x}_n \ket{y \oplus 1}_1, & \text{if } f(x) > t \text{ and } C(x) \geq 0 \\
\ket{x}_n \ket{y}_1, & \text{otherwise}
\end{cases}
$

Where:
- \( f(x): \{0,1\}^n \to \mathbb{Z} \) is a pseudo-Boolean function
- \( C(x): \{0,1\}^n \to \mathbb{Z} \) is a constraint function
- \( t \in \mathbb{Z} \) is a classical threshold


## Features

- Accepts arbitrary pseudo-Boolean expressions for \( f(x) \) and \( C(x) \)
- Implements QFT-based arithmetic to support general nonlinear terms
- Marker qubit flips only if \( f(x) > t \) **and** \( C(x) \geq 0 \)
- Fully unitary oracle: no classical bits or measurements inside
- Clean uncomputation of all ancillas
- Compatible with arbitrary input sizes \( n \)
- Integrated with full Grover search loop
- Includes complexity analysis (gate count, depth, ancillas)

---

## 🧪 Test Case

The oracle was tested on the example:

- \( f(x) = 3x_0x_1 + 2x_1x_2 + x_3 \)
- \( C(x) = x_0 + x_2x_3 \geq 1 \)
- \( t = 3 \)
- \( n = 4 \)


