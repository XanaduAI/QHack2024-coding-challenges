## Challenge statement

The classiest way for travellers to arrive at the Boson Beach, a home to quantum fun and games, is Gray's Cruise. But only the most curious and cunning passengers are allowed into the first class suites. To access them, the door asks you to decrypt some code by programming a quantum device. 

After a few hints (namely in the Cruise's name) and trial-and-error, it has become widely known that the decryption scheme is to transform binary code into the so-called Gray code. But not everyone knows how to program a quantum device to do this. Can you do it?

Quantum computers require clever ways to encode information. For example, suppose that we want to encode a list with $N$ integer numbers. Using the computational basis, the list can be represented using $\lceil \log_2N \rceil$ qubits. For example, the number 3 can be represented as the bitstring $011$, which is mapped into the quantum state $\vert 011\rangle$. 

However, this is not the end of the story! We can use different encodings that suit different problems better. For example, let's take a look at the reflected binary code or Gray Code.

A way to construct the Gray code from the binary code is as follows. Suppose that at some point in the binary string we have a $1$. Then, to obtain the Gray code, the bit $x$ following the $1$ must take the value $1-x$ in Gray code. For instance

$$ 
10011 \ \text{(binary)} \mapsto 11010 \ \text{(Gray)}.
$$

Here, the second digit from the left changed from a $0$ to a $1$ since it's preceded by a $1$. For the same reason, the fifth digit changed from a $1$ to a $0.$

The Gray code is usually applied in classical processing for error correction. On the quantum side, it is used as a resource-efficient representation for Hamiltonian simulation for many-body problems. 

Let's try to build a simple quantum function that converts a set of qubits states from binary to Gray encoding, and get access to those sweet first-class suites!


### Challenge Code

Complete the `binary_to_gray` quantum function for changing a qubit-encoded binary string, to Gray representation. The circuit takes an initial state encoded as a binary string and converts it to a Gray encoding representation. For example, this function should map

$$ 
\vert 10011 \rangle  \mapsto \vert 11010 \rangle.
$$

This quantum function takes the number of bits encoded in the quantum state `num_wires` (`int`). Since this function is a subcircuit, it does not return anything.

### Input

As an input to this problem, you are given a binary input (`list(int)`) corresponding to the binary string that is input into your subcircuit.

### Output

We will check your output by calculating the probabilities of measuring each of the computational basis states. The probability of measuring the Gray-encoded basis state should be equal to 1.


### Test cases

The following **public test cases** are available to you. Note that there are additional **hidden test cases** that we use to verify that your code is valid in full generality.

```python
test_input: [0,1,0]
sample_output:, [0., 0., 0., 1., 0., 0., 0., 0.], 
test_input: [0,1,1]
sample_output:, [0., 0., 1., 0., 0., 0., 0., 0.],
```

If your answer matches the correct one within the `1e-3` relative error tolerance, the output will be `"Success!"`. Otherwise, you will receive an `"Incorrect"` prompt.

Good luck!