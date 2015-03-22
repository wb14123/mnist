# MNIST Dataset for Torch #

Please see [Yann LeCun's page](http://yann.lecun.com/exdb/mnist/) for the original MNIST dataset.

Forked from https://github.com/andresy/mnist , and modified:

1. Change Lable 0 to 10, in order to use ClassNLLCriterio.
2. Chnage size to size(), in order to fit torch's dataset format.
3. Make the input a 3d tensor, in order to make it easier to use in a CNN.

## Installation ##

torch-rocks install https://raw.github.com/wb14123/mnist/master/rocks/mnist-scm-1.rockspec

## Usage ##

```lua
local mnist = require 'mnist'

local trainset = mnist.traindataset()
local testset = mnist.testdataset()

print(trainset:size()) -- to retrieve the size
print(testset:size()) -- to retrieve the size
```

Then, the i-th example is retrieved with:
```lua
local ex = trainset[i]
local x = ex[1] -- the input (a 1*28*28 ByteTensor)
local y = ex[2] -- the label (1--10, 0 is covert to 10)
```
