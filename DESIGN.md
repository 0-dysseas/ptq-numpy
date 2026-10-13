# Design Notes

Design rationale per phase, updated as decisions are made.

## Phase 1: Forward pass foundations — perceptrons

A perceptron is the simplest kind of artificial neuron. It takes a handful of binary inputs and produces a single binary output, 0 or 1.

The output comes from a weighted sum. Each input gets a weight, a number saying how much that input should count, and all the weighted inputs get added together. If the total crosses a threshold, the output is 1. If it doesn't, the output is 0. The weights say how important each input is, and the threshold says how much evidence is needed before the neuron fires.

Rewriting the threshold as a bias, b = -threshold, gives a cleaner rule: output 1 if the weighted sum plus the bias is greater than 0, output 0 otherwise. The bias measures how easy it is to get the neuron to fire. A large positive bias fires almost no matter what the inputs are. A strongly negative bias stays off almost no matter what.

One perceptron on its own can only split its inputs one way, based on whether the weighted sum clears a single threshold. Layering them is what makes them useful. The first layer decides directly on the raw inputs, and each layer after that decides based on the outputs of the layer before it. A single perceptron is a plain yes or no filter. A network of them stacked in layers can judge something more complicated, since each later layer reacts to conclusions the earlier layers already made, not to the raw inputs themselves.

Perceptrons can also compute ordinary logic gates. Two inputs, weights of -2 each, and a bias of 3 gives NAND: both inputs on pushes the sum below zero, so the output is 0, and any other combination keeps it positive, so the output is 1. NAND gates alone are enough to build any computation a digital computer can do, so this is more than a toy example. It means a network of perceptrons can, in principle, compute anything a computer can.

Read so far: Nielsen, "Neural Networks and Deep Learning," chapter 1, the perceptron section up through the NAND gate example. Sigmoid neurons and the rest of the chapter are next.
