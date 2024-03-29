## Challenge statement

The Grand Hideaway Zone is an inn which prides itself in the privacy it offers to its clients. It boasts private dining rooms and a secret meeting lounge in the basement. It even accepts IDs that are known to be fake. It is no surprise that it tends to attract all kinds of suspicious characters, so watch out if you're staying here!

In one of its latest efforts to give even more privacy to its clients, it now offers quantum communication services. It means that its telephone and internet lines use quantum communication  protocols. Messages can no longer be eavesdropped on, to the police's dismay. 

However, the communication protocols rely on Greenberger–Horne–Zeilinger states, or GHZ states for short, which are entangled qubit states of the form

$$

\vert GHZ \rangle = \frac{1}{\sqrt{2}}\vert 00\ldots 0\rangle + \frac{1}{\sqrt{2}}\vert11\ldots 1\rangle. 

$$

Generating these states uses two-qubit gates, which can be noisy. While the inn uses a state-of-the-art neutral-atom quantum computer to generate them, the communication is not foolproof and several misunderstandings have been known to happen, one of which led to the capture of a mafia boss.

In this challenge, we have access to the inn's neutral-atom quantum computer. Using laser pulses and carefully controlling the weak van der Waals interactions between atoms, this device can implement the single qubit rotations $RX$ and $RY,$ and the $CZ$ (Control-$Z$) gate.

Your task is to generate a GHZ state for a given number of qubits $n_{qubits}$ using only rotations and the $CZ$ gate. However, as is the case with most real-life quantum devices, two-qubit gates are a source of noise. We model the noise by adding a depolarizing gate on the target qubit after each $CZ$ gate, with noise parameter $\gamma.$ Therefore, the GHZ state that the neutral-atom device generates will be noisy. You must quantify how good the produced GHZ state is by calculating the fidelity between the noisy state and the ideal GHZ state.

You will now be able to tell how error-prone the inn's messaging services actually are!

## Challenge Code

In the challenge template, you must complete the following functions.

- `GHZ_circuit`: A quantum function that, given the noise parameter (`noise_param` (`float`)) $\gamma$ and the number of qubits `n_qubits` (`int`), generates the GHZ state in $n_{qubits}$ dimensions. This circuit may only use the $RX$ (`qml.RX`), $RY$ (`qml.RY`), and $CZ$ (`qml.CZ`) gates and the depolarizing channel (`qml.DepolarizingChannel`).

- `GHZ_fidelity`: Given $\gamma$ (`noise_param` (`float`)) and the number of qubits `n_qubits` (`int`), calculates the fidelity between the $GHZ$ state generated by `GHZ_circuit` and the ideal $GHZ$ state. 

You are also given some space to write some helper functions. 

### Input

As an input to this challenge, you are given $\gamma$ (`float`) and $n_{qubits}$ (`int`) in this order.

### Output

The expected output is the fidelity (`float`) as calculated by the `GHZ_fidelity` function.

### Test cases

The following **public test cases** are available for you to check your work. There are also some **hidden test cases** which we will use to check that your solution works in full generality.

```python
test_input: 0.05, 3
expected_ouput: 0.902778

test_input: 0.01, 5
expected_output: 0.9606615
```

If your solution matches the correct one up to a relative tolerance of $1\times 10^{-4}$, the output will be `"Success!"`. Otherwise, you will receive an `"Incorrect"` prompt.

Good luck!