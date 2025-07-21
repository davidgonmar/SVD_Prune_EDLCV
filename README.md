# SVD_Pruning
This is a repertory for source codes of Rank Pruning with SVD



To run CIFAR, please use command lines in [CNN/cifar10/Start up code](https://github.com/yanghr/SVD_Pruning/blob/master/CNN/cifar10/Start%20up%20code.md)

To run ImageNet, please use command lines in [CNN/imagenet/Start up](https://github.com/yanghr/SVD_Pruning/blob/master/CNN/imagenet/start_up.txt)

To run with RNN, please use command lines in [RNN/Start up](https://github.com/yanghr/SVD_Pruning/blob/master/RNN/world-language-model/start_up.txt)

# Notes (by davidgonmar)

I ran the scripts for ResNet-20 Hoyer-regularized training/factorization. I fixed small errors (probably due to changes in PyTorch) in the scripts. Added a requirements.txt file with the versions I used. Please note that other scripts might still be broken.

- Pretrain final accuracy: 91.00%.

- Regularized train resnet20 final accuracy: 90.63%. For both of these I used the commands that appear on the respective .md file.

- For pruning the model, I used the command that was in the .md file, but I modified the path with the saved model to the correct one. Obtained 80.82% acc with compression factor 2.175783x.

- For finetuning the pruned model, I used the command in the .md file. Final acc: 91.17%.


The model structure obtained is as follows:

```
SVD_Conv2d0:    inchannel:3     outchannel:16   kernel_size:3   stride:1        Rank:8
SVD_Conv2d1:    inchannel:16    outchannel:16   kernel_size:3   stride:1        Rank:8
SVD_Conv2d2:    inchannel:16    outchannel:16   kernel_size:3   stride:1        Rank:8
SVD_Conv2d3:    inchannel:16    outchannel:16   kernel_size:3   stride:1        Rank:8
SVD_Conv2d4:    inchannel:16    outchannel:16   kernel_size:3   stride:1        Rank:4
SVD_Conv2d5:    inchannel:16    outchannel:16   kernel_size:3   stride:1        Rank:4
SVD_Conv2d6:    inchannel:16    outchannel:16   kernel_size:3   stride:1        Rank:3
SVD_Conv2d7:    inchannel:16    outchannel:32   kernel_size:3   stride:2        Rank:14
SVD_Conv2d8:    inchannel:32    outchannel:32   kernel_size:3   stride:1        Rank:20
SVD_Conv2d9:    inchannel:16    outchannel:32   kernel_size:1   stride:2        Rank:7
SVD_Conv2d10:   inchannel:32    outchannel:32   kernel_size:3   stride:1        Rank:15
SVD_Conv2d11:   inchannel:32    outchannel:32   kernel_size:3   stride:1        Rank:16
SVD_Conv2d12:   inchannel:32    outchannel:32   kernel_size:3   stride:1        Rank:1
SVD_Conv2d13:   inchannel:32    outchannel:32   kernel_size:3   stride:1        Rank:1
SVD_Conv2d14:   inchannel:32    outchannel:64   kernel_size:3   stride:2        Rank:30
SVD_Conv2d15:   inchannel:64    outchannel:64   kernel_size:3   stride:1        Rank:56
SVD_Conv2d16:   inchannel:32    outchannel:64   kernel_size:1   stride:2        Rank:9
SVD_Conv2d17:   inchannel:64    outchannel:64   kernel_size:3   stride:1        Rank:50
SVD_Conv2d18:   inchannel:64    outchannel:64   kernel_size:3   stride:1        Rank:30
SVD_Conv2d19:   inchannel:64    outchannel:64   kernel_size:3   stride:1        Rank:21
SVD_Conv2d20:   inchannel:64    outchannel:64   kernel_size:3   stride:1        Rank:11
```