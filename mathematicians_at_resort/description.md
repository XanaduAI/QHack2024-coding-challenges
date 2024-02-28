## Challenge statement

You find yourself in the Boson Beach resort, undoubtedly one of the favourite places for great minds to enjoy a day off and rest. 

Actually, this "rest" should be taken figuratively, because when great mathematicians get together, they always challenge each other with problems to solve. One of the most epic battles took place between Fourier and Bell. Everyone at the resort hears this story at least once, and you're not the exception. A youthful and excited receptionist can't contain himself and breaks into storytelling mode.

Bell loved to create very specific states. These states are nothing but the uniform superposition of all zeros and all ones. He had a 5-qubit device, so he wanted to create this state:

$$\frac{|00000\rangle + |11111\rangle}{\sqrt{2}}$$

However, poor Bell only had $T$ gates and Hadamard gates in storage. He knew that the state he wanted to build is entangled, and without the help of gates acting on more than one qubit, it would not be possible to build it!

For this reason, Bell decided to ask Fourier for help. Fourier was known to always have QFT operators to spare, so he borrowed a few operators from him. However, Fourier, who was a great expert in circuits, told Bell that by giving him QFTs acting on 3 qubits he could solve the problem.

Bell was very confused, but he was able to figure it out!

The receptionist claims that no guest has ever been able to figure this out since Bell did, and tells you that you'll get free access to the buffet if you submit your solution. With free food at stake, you get to work when you were supposed to be resting.

Your goal will be to create the requested state using only $H$ (`qml.Hadamard`), $T$ (`qml.T`), and QFT (`qml.QFT`) acting on 3 wires. Show us that you are at the same level as Bell and get that free buffet!

# Challenge code

In the code below you must complete the `circuit` QNode so that the circuit behaves as described in the statement. You may only use 3-qubit `QFT` operators and `H` and `T` gates.

### Input

There is no input to this problem.

### Output

The `circuit` QNode will output the probability of obtaining $|00000\rangle$ and $|11111\rangle$

### Test cases

There are no public test cases. To test your solution, we will measure the probabilities of obtaining $|00000\rangle$ and $ |11111\rangle$ and check if they are both $1/2.$ We will therefore consider solutions that include certain phases to be valid too.

Good luck!