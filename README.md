# AC-GANS For Image Classification
These are the architectures for the AC-GAN and baseline models that we constructed for the manuscript "Investigating the Potential of Auxiliary-Classifier GANs for Image Classification in Low Data Regimes".
AlexNet was used for the CIFAR10 experiments, and another standard CNN model was used for the Fashion-MNIST and COVID-19 tests. The discriminators of the AC-GANs are based off these corresponding classifier networks. 


Almost all the hyperparameters were shared between the trained CNNs and AC-GANs for all experiments. All convolutional and transpose convolutional parameters were initialized from a normal distribution $\mathcal{N}(0, 0.02 )$. Batch normalization layers were initialized with <img src="https://render.githubusercontent.com/render/math?math=\gamma, \beta"> from <img src="https://render.githubusercontent.com/render/math?math=\mathcal{N}(1, 0.02)"> and biases as a constant 0. All other weight parameters were initialized as per default PyTorch initialization.

During training, images were fed in with batch size 100. All parameters were optimized using ADAM (https://arxiv.org/abs/1412.6980) with learning rate 0.0002 and <img src="https://render.githubusercontent.com/render/math?math=(\beta_1, \beta_2) = (0.5, 0.999)">. We trained for every model for 1000 epochs, which is well past convergence, and use the model with best validation performance. We employed the same optimization and weight initialization schemes for all networks. Additionally, with our proposed modifications for the AC-GAN set the gradient penalty coefficient $\lambda = 10$, and used a truncation threshold of $1$. 
