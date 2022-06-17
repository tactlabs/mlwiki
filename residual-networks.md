/ [Home](index.md)

# residual networks

very deep NNs are difficult to train because of vanishing and explodinggradients problems.
●In this section we will learn about skip connection which makes you take theactivation from one layer and suddenly feed it to another layer even muchdeeper in NN which allows you to train large NNs even with layers greater than100.
●Residual block○ResNets are built out of some Residual blocks.○They add a shortcut/skip connection before the second activation.
○The authors of this block find that you can train a deeper NNs usingstacking this block.●Residual Network
●Are a NN that consists of some Residual blocks.
●These networks can go deeper without hurting the performance. In thenormal NN - Plain networks - the theory tell us that if we go deeper we willget a better solution to our problem

<br>

**Created by kishore**

---

<br>