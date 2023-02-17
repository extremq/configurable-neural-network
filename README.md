# Configurable neural network
This is an example of a configurable neural network.

The dataset I've tested is the popular MNIST digits dataset.

By configurable I mean that you can set how many hidden layers the model should have
and specify the amount of nodes on each layer.

You can also choose whether to use ReLU or Sigmoid as the activation function.

# Shape of neural net
Right now, I haven't found that much of an improvement by incorporating more than one hidden layer.

I also observed that the number of layers should thin out, otherwise it wont train that well.

For a `784 - 50 - 20 - 10` neural net I've got **95.13%** accuracy at 7 epochs, while a `784 - 500 - 10` gets a **97.32%** at 5 epochs (the `700 - 300 - 10` neural network [here](https://github.com/extremq/neural-network-number-recognizer) has better performance).

Both used the sigmoid.

![](https://i.imgur.com/axWu9WU.png)

Performance of the `784 - 50 - 20 - 10, lr = 0.01` neural network by epochs.

![](https://i.imgur.com/s1A0lwT.png)

Performance of the `784 - 500 - 10, lr = 0.12` neural network by epochs.

# GPU vs CPU
I've also included a pytorch version which starts to gain significant speed as we increase the number of weights.

For a 784 - 500 - 10 neural network, one epoch:
- CPU time 1m 7s (AMD Ryzen 5 3600G)
- GPU time 40s (RTX 3060)

Considering scaling on larger datasets, a GPU definitely is worth using.