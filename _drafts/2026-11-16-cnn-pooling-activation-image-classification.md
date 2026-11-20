---
layout: post
title: "Pooling and Activation Functions Comparison for Image Classification in Convolutional Neural Networks"
categories: [GenAI, AI]
category: AI Experiments
description: "We are comparing "
author: aalobaid
length: 10
cover: genai-for-managers/genai_for_managers_cover.png
toc: true
---

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<style>

.bar-canvas{
    max-height: 17rem;	
    
}


.chart-controls button {
    color: white;
    background-color: #64748b;
    margin: 4px;
    padding: 8px 14px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}


</style>


In the previous 


Applying LeNet-5 comparing different pooling and activation functions:

- Pooling: Max pooling vs Avg pooling
- Activation functions: ReLu vs Software vs




This implementation is using the [original LeNet architecture idea by LeCun et al. (1988)](https://doi.org/10.1109/5.726791) and relied on the simplification of [Andrew Ng](https://www.andrewng.org/) that he presented in his [CNN course](https://www.coursera.org/learn/convolutional-neural-networks/). 



We use 28x28, which is smaller than the original paper, as this is the dataset provided by TF in mnist.load_data method.



## Pooling Methods

Pooling is used primarly to reduce the size of the layers, while keeping some of the information, a downsampling method. Average pooling and maximum pooling are the among the most common pooling/downsampling techniques. 

<!--
The most common pooling techniques are the average pooling and the maximum pooling. 
-->

### Average Pooling

Average pooling was used by the famous [LeNet-5 article](https://doi.org/10.1109/5.726791). The filter performs a pair-wise multiplication (first element of the filter is multiplied by the first element on the window of the input matrix) and then the numbers on the resultant matrix is taken. 


### Max Pooling
It was adopted more often later as it seemed to outputform average pooling when used with Sigmoid and Tanh activation functions (see [Scherer et al. (2010)](https://doi.org/10.1007/978-3-642-15825-4_10)). Similar to the average pooling, pair-wise multiplication between the window of the input and the filter is performed, and then the maximum value is selected. (see [Ranzato et al. (2007)](https://doi.org/10.1109/CVPR.2007.383157)).

 

## Activation Functions

For the hidden layers, Sigmoid was the go to activation function, and Tanh, followed by ReLu. Then, many improvements, and proposal for activation functions was introduced. Here we introduce many of the common activation functions used for the hidden layers.

Important features to have in activation functions:
- Smoothness: 
- Non-linearity: to learn complex patters (more than linear ones). 
- Differentiability: see how back propagation works.
- Boundedness: .



### Sigmoid
It was historically the go to activation function for being non-linear (to learn complex patterns beyound the linear ones), smooth, and differentiable (fo)



### Tanh
This function, hyperbolic tangent, was used as a better alternative to Sigmoid. 



### ReLU

When ReLU came, it was the hot thing after Tanh, for the significant improvement. But in reality, it exited way long before that. 

The Japanese scientist, Kunihiko Fukushima used it in 1969, in his paper [Visual Feature Extraction by a Multilayered Network of Analog Threshold Elements](https://doi.org/10.1109/TSSC.1969.300225). But it was popularized as the go to activation function +40 years after that, [in 2010 by Nair & Hinton](https://dl.acm.org/doi/10.5555/3104322.3104425).




### Leaky ReLU

It was an update on the ReLu to solve the problem of dead neurons. Published in 2013 by [Mass et al.](https://www.awnihannun.com/papers/relu_hybrid_icml2013_final.pdf)

f(x) = x if x>0, alpha x otherwise. 



### ELU

Exponential Linear Unit (ELU)

f(x) = alpha (e ^x - 1)



### GELU


f(x) = x * CDF(x)


CDF is the commulative normal distribution. Here the CDF of the normal distribution.





### Swish

Swish is already known as SiLU

f(x) = x / (1+ e^-x)




## Related Work 

Mass et al. 2013 found that Leaky ReLU slightly outperformed ReLU in some cases, but significantly outperformed Tan. 



## Experiment Setup

We used the TensorFlow with [Adam](https://www.tensorflow.org/api_docs/python/tf/keras/optimizers/Adam) optimization and [Categorical Cross Entropy](https://www.tensorflow.org/api_docs/python/tf/keras/losses/sparse_categorical_crossentropy?version=stable) for the loss.



The MNIST dataset from TensorFlow was used, with the default training and testing set. For the validation, 0.1 was used (validation_split=0.1 is used for the fit function).

## Datasets
We used the following datasets directly from TensorFlow
- [MNIST](https://www.tensorflow.org/datasets/catalog/mnist): The is the famous dataset, the modified NIST
- [KMNIST](https://www.tensorflow.org/datasets/catalog/kmnist):
- [Fashion MNIST](https://www.tensorflow.org/datasets/catalog/fashion_mnist): 
- [EMNIST](https://www.tensorflow.org/datasets/catalog/emnist):




The source code of the [Pooling vs Activation Experiment in CNN](https://github.com/runzbuzz/labs/tree/main/cnn-pooling-vs-activation) is publicly available on GitHub.



## Results and Discussion


### Average Pooling vs Max Pooling
Consistantly in our experiments, the max pooling outperformed the average pooling, except some epochs:
- Tanh: epochs 7&8.
- ReLu: epochs 8&9.
- GELU: epoch 3.


### Activation Functions


####  For the average pooling case
GELU took the lead from the first epoch and then Swish caught up after a few epochs, leading to an almost identical performance at the 10th epoch. The rest scored slightly lower (< 0.3%), except for the sigmoid, which was lower by (0.7%) to the 2nd lowest. But that is pretty small. However, the sigmoid on the first epochs was significantly lower (~8% at the first epoch).  


#### For the max pooling case
Sigmoid stands out to score lower (~6% at the first epoch) and then significantly improved after that. The rest of the activation functions performance is pretty close after a few epochs, with the Swish leading, followed by the GELU (0.1 lower), with the Tanh having the 2nd lowest (0.2% from the one on top).





## Limitation
This experiment compares different pooling and activation functions for the hidden layers, on one CNN architecure, a modified version of LeNet-5. It is tested on identifying handwritten digits. 

We also used adam optimizer, so different settings and optimization might yield different results. 


## Conclusion

We found that Max pooling consistently outperformed the Avg pooling consistently on the recognition on hand written digits MNIST dataset. 

It is not a surprise that ReLu outperformed the classical/older activation functions like Sigmoid and Tanh, and yielded good results even in the first epochs (faster conversion?)





<!-- MNIST -->
<div class="chart-container">
    <div class="chart-controls" id="mnistControls"></div>
    <canvas id="mnistValChart"></canvas>
</div>

<div class="chart-container " >
    <canvas id="mnistTestChart" class="bar-canvas"></canvas>
</div>

<!-- Fashion-MNIST -->
<div class="chart-container">
    <div class="chart-controls" id="fashionMnistControls"></div>
    <canvas id="fashionMnistValChart" ></canvas>
</div>

<div class="chart-container">
    <canvas id="fashionMnistTestChart" class="bar-canvas"></canvas>
</div>


<!-- K-MNIST -->
<div class="chart-container">
    <div class="chart-controls" id="kMnistControls"></div>
    <canvas id="kMnistValChart" ></canvas>
</div>

<div class="chart-container">
    <canvas id="kMnistTestChart" class="bar-canvas"></canvas>
</div>



<!-- E-MNIST -->
<div class="chart-container">
    <div class="chart-controls" id="eMnistControls"></div>
    <canvas id="eMnistValChart" ></canvas>
</div>

<div class="chart-container">
    <canvas id="eMnistTestChart" class="bar-canvas"></canvas>
</div>






<script>


const mnistValidationResults = {
    "labels": [
        1,
        2,
        3,
        4,
        5,
        6,
        7,
        8,
        9,
        10
    ],
    "datasets": [
        {
            "label": "Average Pooling + Tanh",
            "data": [
                0.9610000252723694,
                0.9735000133514404,
                0.9768333435058594,
                0.981333315372467,
                0.9828333258628845,
                0.9836666584014893,
                0.9851666688919067,
                0.9853333234786987,
                0.9848333597183228,
                0.984333336353302
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Tanh",
            "data": [
                0.9758333563804626,
                0.9775000214576721,
                0.9796666502952576,
                0.9835000038146973,
                0.9851666688919067,
                0.9848333597183228,
                0.984333336353302,
                0.984666645526886,
                0.9861666560173035,
                0.9851666688919067
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Swish",
            "data": [
                0.9566666483879089,
                0.9775000214576721,
                0.9801666736602783,
                0.9829999804496765,
                0.9854999780654907,
                0.9866666793823242,
                0.9869999885559082,
                0.9878333210945129,
                0.9878333210945129,
                0.9871666431427002
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + GELU",
            "data": [
                0.9700000286102295,
                0.9810000061988831,
                0.984333336353302,
                0.9850000143051147,
                0.9854999780654907,
                0.9865000247955322,
                0.9860000014305115,
                0.9866666793823242,
                0.9868333339691162,
                0.9869999885559082
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + GELU",
            "data": [
                0.9783333539962769,
                0.9816666841506958,
                0.9816666841506958,
                0.9853333234786987,
                0.9878333210945129,
                0.9884999990463257,
                0.9896666407585144,
                0.9894999861717224,
                0.9898333549499512,
                0.9886666536331177
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + ELU",
            "data": [
                0.9769999980926514,
                0.9785000085830688,
                0.9806666374206543,
                0.9835000038146973,
                0.9850000143051147,
                0.9860000014305115,
                0.9866666793823242,
                0.9854999780654907,
                0.987333357334137,
                0.9866666793823242
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Swish",
            "data": [
                0.9746666550636292,
                0.9800000190734863,
                0.98416668176651,
                0.9863333106040955,
                0.987333357334137,
                0.9868333339691162,
                0.9894999861717224,
                0.9900000095367432,
                0.9893333315849304,
                0.9900000095367432
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Leaky ReLU",
            "data": [
                0.9636666774749756,
                0.9788333177566528,
                0.9806666374206543,
                0.9821666479110718,
                0.984000027179718,
                0.98416668176651,
                0.984000027179718,
                0.984499990940094,
                0.9856666922569275,
                0.9853333234786987
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Leaky ReLU",
            "data": [
                0.9775000214576721,
                0.9821666479110718,
                0.9828333258628845,
                0.98416668176651,
                0.984499990940094,
                0.9871666431427002,
                0.987666666507721,
                0.9869999885559082,
                0.9878333210945129,
                0.987500011920929
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Sigmoid",
            "data": [
                0.8806666731834412,
                0.9334999918937683,
                0.9521666765213013,
                0.9618333578109741,
                0.9681666493415833,
                0.9739999771118164,
                0.9764999747276306,
                0.9778333306312561,
                0.9803333282470703,
                0.9816666841506958
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Sigmoid",
            "data": [
                0.9173333048820496,
                0.9631666541099548,
                0.9743333458900452,
                0.9775000214576721,
                0.9808333516120911,
                0.9833333492279053,
                0.984333336353302,
                0.9851666688919067,
                0.9856666922569275,
                0.9863333106040955
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + ELU",
            "data": [
                0.9613333344459534,
                0.9738333225250244,
                0.9760000109672546,
                0.9803333282470703,
                0.9828333258628845,
                0.984333336353302,
                0.984000027179718,
                0.984499990940094,
                0.9860000014305115,
                0.9860000014305115
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + ReLU",
            "data": [
                0.9651666879653931,
                0.9781666398048401,
                0.9816666841506958,
                0.9815000295639038,
                0.9833333492279053,
                0.9854999780654907,
                0.9856666922569275,
                0.9868333339691162,
                0.9868333339691162,
                0.9851666688919067
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + ReLU",
            "data": [
                0.9703333377838135,
                0.9835000038146973,
                0.984499990940094,
                0.9851666688919067,
                0.9865000247955322,
                0.9866666793823242,
                0.9858333468437195,
                0.9861666560173035,
                0.9860000014305115,
                0.987500011920929
            ],
            "fill": false,
            "tension": 0.2
        }
    ]
};



const mnistTestResults = {
    "labels": [
        "Average Pooling + ELU",
        "Average Pooling + GELU",
        "Average Pooling + Leaky ReLU",
        "Average Pooling + ReLU",
        "Average Pooling + Sigmoid",
        "Average Pooling + Swish",
        "Average Pooling + Tanh",
        "Max Pooling + ELU",
        "Max Pooling + GELU",
        "Max Pooling + Leaky ReLU",
        "Max Pooling + ReLU",
        "Max Pooling + Sigmoid",
        "Max Pooling + Swish",
        "Max Pooling + Tanh"
    ],
    "datasets": [
        {
            "label": "Test Accuracy",
            "data": [
                0.9848999977111816,
                0.9894999861717224,
                0.9861000180244446,
                0.9861000180244446,
                0.9763000011444092,
                0.9869999885559082,
                0.9839000105857849,
                0.9876999855041504,
                0.9891999959945679,
                0.9891999959945679,
                0.9873999953269958,
                0.9865000247955322,
                0.9882000088691711,
                0.98580002784729
            ]
        }
    ]
};




















fashionValidationResults = {
    "labels": [
        1,
        2,
        3,
        4,
        5,
        6,
        7,
        8,
        9,
        10
    ],
    "datasets": [
        {
            "label": "Max Pooling + Swish",
            "data": [
                0.8066666722297668,
                0.8381666541099548,
                0.8531666398048401,
                0.8604999780654907,
                0.8686666488647461,
                0.8741666674613953,
                0.8763333559036255,
                0.8799999952316284,
                0.8824999928474426,
                0.8849999904632568
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + ReLU",
            "data": [
                0.7953333258628845,
                0.8348333239555359,
                0.8501666784286499,
                0.8588333129882812,
                0.8654999732971191,
                0.8721666932106018,
                0.8771666884422302,
                0.8815000057220459,
                0.8853333592414856,
                0.8871666789054871
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + ReLU",
            "data": [
                0.8256666660308838,
                0.8464999794960022,
                0.8571666479110718,
                0.8684999942779541,
                0.8778333067893982,
                0.8818333148956299,
                0.8828333616256714,
                0.8840000033378601,
                0.887499988079071,
                0.8901666402816772
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Sigmoid",
            "data": [
                0.6983333230018616,
                0.7543333172798157,
                0.7821666598320007,
                0.7976666688919067,
                0.8140000104904175,
                0.827833354473114,
                0.8389999866485596,
                0.8481666445732117,
                0.8504999876022339,
                0.8556666374206543
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Swish",
            "data": [
                0.7851666808128357,
                0.8183333277702332,
                0.840833306312561,
                0.8533333539962769,
                0.8640000224113464,
                0.8705000281333923,
                0.874666690826416,
                0.8766666650772095,
                0.8803333044052124,
                0.8801666498184204
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Leaky ReLU",
            "data": [
                0.8068333268165588,
                0.8335000276565552,
                0.8560000061988831,
                0.8634999990463257,
                0.8696666955947876,
                0.8755000233650208,
                0.8801666498184204,
                0.8840000033378601,
                0.8861666917800903,
                0.8893333077430725
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Leaky ReLU",
            "data": [
                0.8183333277702332,
                0.8498333096504211,
                0.8678333163261414,
                0.8759999871253967,
                0.8828333616256714,
                0.887333333492279,
                0.89083331823349,
                0.8931666612625122,
                0.893833339214325,
                0.8946666717529297
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + ELU",
            "data": [
                0.8335000276565552,
                0.8575000166893005,
                0.8693333268165588,
                0.875,
                0.8771666884422302,
                0.8821666836738586,
                0.8866666555404663,
                0.890333354473114,
                0.893666684627533,
                0.8963333368301392
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Sigmoid",
            "data": [
                0.674833357334137,
                0.7450000047683716,
                0.7663333415985107,
                0.7820000052452087,
                0.7948333621025085,
                0.8031666874885559,
                0.8111666440963745,
                0.8191666603088379,
                0.824999988079071,
                0.828166663646698
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + ELU",
            "data": [
                0.8044999837875366,
                0.8296666741371155,
                0.8453333377838135,
                0.8568333387374878,
                0.8640000224113464,
                0.8700000047683716,
                0.8731666803359985,
                0.8771666884422302,
                0.8801666498184204,
                0.8824999928474426
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + GELU",
            "data": [
                0.7933333516120911,
                0.8288333415985107,
                0.846666693687439,
                0.859333336353302,
                0.8663333058357239,
                0.8715000152587891,
                0.8758333325386047,
                0.878333330154419,
                0.8815000057220459,
                0.8830000162124634
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + GELU",
            "data": [
                0.8143333196640015,
                0.8511666655540466,
                0.8616666793823242,
                0.8706666827201843,
                0.8778333067893982,
                0.8831666707992554,
                0.8863333463668823,
                0.887499988079071,
                0.8884999752044678,
                0.8918333053588867
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Tanh",
            "data": [
                0.8136666417121887,
                0.8368333578109741,
                0.8514999747276306,
                0.8600000143051147,
                0.8668333292007446,
                0.8706666827201843,
                0.8755000233650208,
                0.8786666393280029,
                0.8806666731834412,
                0.8824999928474426
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Tanh",
            "data": [
                0.8420000076293945,
                0.862666666507721,
                0.8705000281333923,
                0.8773333430290222,
                0.8801666498184204,
                0.8843333125114441,
                0.8866666555404663,
                0.8888333439826965,
                0.8916666507720947,
                0.8914999961853027
            ],
            "fill": false,
            "tension": 0.2
        }
    ]
};

const fashionTestResults = {
    "labels": [
        "Average Pooling + ELU",
        "Average Pooling + GELU",
        "Average Pooling + Leaky ReLU",
        "Average Pooling + ReLU",
        "Average Pooling + Sigmoid",
        "Average Pooling + Swish",
        "Average Pooling + Tanh",
        "Max Pooling + ELU",
        "Max Pooling + GELU",
        "Max Pooling + Leaky ReLU",
        "Max Pooling + ReLU",
        "Max Pooling + Sigmoid",
        "Max Pooling + Swish",
        "Max Pooling + Tanh"
    ],
    "datasets": [
        {
            "label": "Test Accuracy",
            "data": [
                0.8787999749183655,
                0.8797000050544739,
                0.8848000168800354,
                0.8835999965667725,
                0.8213000297546387,
                0.8744000196456909,
                0.8776000142097473,
                0.8860999941825867,
                0.8845000267028809,
                0.8863999843597412,
                0.886900007724762,
                0.8550999760627747,
                0.8849999904632568,
                0.8865000009536743
            ]
        }
    ]
};



const kmnistValidationResults = {
    "labels": [
        1,
        2,
        3,
        4,
        5,
        6,
        7,
        8,
        9,
        10
    ],
    "datasets": [
        {
            "label": "Average Pooling + ELU",
            "data": [
                0.8044999837875366,
                0.8296666741371155,
                0.8453333377838135,
                0.8568333387374878,
                0.8640000224113464,
                0.8700000047683716,
                0.8731666803359985,
                0.8771666884422302,
                0.8801666498184204,
                0.8824999928474426
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + ReLU",
            "data": [
                0.7953333258628845,
                0.8348333239555359,
                0.8501666784286499,
                0.8588333129882812,
                0.8654999732971191,
                0.8721666932106018,
                0.8771666884422302,
                0.8815000057220459,
                0.8853333592414856,
                0.8871666789054871
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + ReLU",
            "data": [
                0.8256666660308838,
                0.8464999794960022,
                0.8571666479110718,
                0.8684999942779541,
                0.8778333067893982,
                0.8818333148956299,
                0.8828333616256714,
                0.8840000033378601,
                0.887499988079071,
                0.8901666402816772
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Tanh",
            "data": [
                0.8136666417121887,
                0.8368333578109741,
                0.8514999747276306,
                0.8600000143051147,
                0.8668333292007446,
                0.8706666827201843,
                0.8755000233650208,
                0.8786666393280029,
                0.8806666731834412,
                0.8824999928474426
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Swish",
            "data": [
                0.7851666808128357,
                0.8183333277702332,
                0.840833306312561,
                0.8533333539962769,
                0.8640000224113464,
                0.8705000281333923,
                0.874666690826416,
                0.8766666650772095,
                0.8803333044052124,
                0.8801666498184204
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Tanh",
            "data": [
                0.8420000076293945,
                0.862666666507721,
                0.8705000281333923,
                0.8773333430290222,
                0.8801666498184204,
                0.8843333125114441,
                0.8866666555404663,
                0.8888333439826965,
                0.8916666507720947,
                0.8914999961853027
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + GELU",
            "data": [
                0.7933333516120911,
                0.8288333415985107,
                0.846666693687439,
                0.859333336353302,
                0.8663333058357239,
                0.8715000152587891,
                0.8758333325386047,
                0.878333330154419,
                0.8815000057220459,
                0.8830000162124634
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + GELU",
            "data": [
                0.8143333196640015,
                0.8511666655540466,
                0.8616666793823242,
                0.8706666827201843,
                0.8778333067893982,
                0.8831666707992554,
                0.8863333463668823,
                0.887499988079071,
                0.8884999752044678,
                0.8918333053588867
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + ELU",
            "data": [
                0.8335000276565552,
                0.8575000166893005,
                0.8693333268165588,
                0.875,
                0.8771666884422302,
                0.8821666836738586,
                0.8866666555404663,
                0.890333354473114,
                0.893666684627533,
                0.8963333368301392
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Leaky ReLU",
            "data": [
                0.8183333277702332,
                0.8498333096504211,
                0.8678333163261414,
                0.8759999871253967,
                0.8828333616256714,
                0.887333333492279,
                0.89083331823349,
                0.8931666612625122,
                0.893833339214325,
                0.8946666717529297
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Sigmoid",
            "data": [
                0.6983333230018616,
                0.7543333172798157,
                0.7821666598320007,
                0.7976666688919067,
                0.8140000104904175,
                0.827833354473114,
                0.8389999866485596,
                0.8481666445732117,
                0.8504999876022339,
                0.8556666374206543
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Swish",
            "data": [
                0.8066666722297668,
                0.8381666541099548,
                0.8531666398048401,
                0.8604999780654907,
                0.8686666488647461,
                0.8741666674613953,
                0.8763333559036255,
                0.8799999952316284,
                0.8824999928474426,
                0.8849999904632568
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Leaky ReLU",
            "data": [
                0.8068333268165588,
                0.8335000276565552,
                0.8560000061988831,
                0.8634999990463257,
                0.8696666955947876,
                0.8755000233650208,
                0.8801666498184204,
                0.8840000033378601,
                0.8861666917800903,
                0.8893333077430725
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Sigmoid",
            "data": [
                0.674833357334137,
                0.7450000047683716,
                0.7663333415985107,
                0.7820000052452087,
                0.7948333621025085,
                0.8031666874885559,
                0.8111666440963745,
                0.8191666603088379,
                0.824999988079071,
                0.828166663646698
            ],
            "fill": false,
            "tension": 0.2
        }
    ]
};


const kmnistTestResults = {
    "labels": [
        "Average Pooling + ELU",
        "Average Pooling + GELU",
        "Average Pooling + Leaky ReLU",
        "Average Pooling + ReLU",
        "Average Pooling + Sigmoid",
        "Average Pooling + Swish",
        "Average Pooling + Tanh",
        "Max Pooling + ELU",
        "Max Pooling + GELU",
        "Max Pooling + Leaky ReLU",
        "Max Pooling + ReLU",
        "Max Pooling + Sigmoid",
        "Max Pooling + Swish",
        "Max Pooling + Tanh"
    ],
    "datasets": [
        {
            "label": "Test Accuracy",
            "data": [
                0.8787999749183655,
                0.8797000050544739,
                0.8848000168800354,
                0.8835999965667725,
                0.8213000297546387,
                0.8744000196456909,
                0.8776000142097473,
                0.8860999941825867,
                0.8845000267028809,
                0.8863999843597412,
                0.886900007724762,
                0.8550999760627747,
                0.8849999904632568,
                0.8865000009536743
            ]
        }
    ]
};




const emnistValidationResults = {
    "labels": [
        1,
        2,
        3,
        4,
        5,
        6,
        7,
        8,
        9,
        10
    ],
    "datasets": [
        {
            "label": "Average Pooling + ReLU",
            "data": [
                0.7695000171661377,
                0.7951666712760925,
                0.8180000185966492,
                0.8356666564941406,
                0.846666693687439,
                0.8525000214576721,
                0.8611666560173035,
                0.8673333525657654,
                0.8711666464805603,
                0.8733333349227905
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + ReLU",
            "data": [
                0.7878333330154419,
                0.8243333101272583,
                0.8398333191871643,
                0.846833348274231,
                0.8606666922569275,
                0.8691666722297668,
                0.8741666674613953,
                0.8786666393280029,
                0.8831666707992554,
                0.8845000267028809
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Swish",
            "data": [
                0.7705000042915344,
                0.8101666569709778,
                0.8391666412353516,
                0.8550000190734863,
                0.8641666769981384,
                0.8705000281333923,
                0.875333309173584,
                0.8805000185966492,
                0.8848333358764648,
                0.8868333101272583
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + ELU",
            "data": [
                0.8084999918937683,
                0.8443333506584167,
                0.8611666560173035,
                0.8698333501815796,
                0.875333309173584,
                0.8805000185966492,
                0.8836666941642761,
                0.8866666555404663,
                0.8880000114440918,
                0.8898333311080933
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Sigmoid",
            "data": [
                0.09733333438634872,
                0.6756666898727417,
                0.7465000152587891,
                0.7681666612625122,
                0.7808333039283752,
                0.796500027179718,
                0.8076666593551636,
                0.8118333220481873,
                0.8165000081062317,
                0.8211666941642761
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Sigmoid",
            "data": [
                0.09733333438634872,
                0.6635000109672546,
                0.750166654586792,
                0.7761666774749756,
                0.7923333048820496,
                0.8088333606719971,
                0.8196666836738586,
                0.8245000243186951,
                0.8321666717529297,
                0.8358333110809326
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Swish",
            "data": [
                0.7609999775886536,
                0.7921666502952576,
                0.8188333511352539,
                0.8358333110809326,
                0.8489999771118164,
                0.8575000166893005,
                0.8643333315849304,
                0.8691666722297668,
                0.8734999895095825,
                0.8766666650772095
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Leaky ReLU",
            "data": [
                0.7940000295639038,
                0.8270000219345093,
                0.8483333587646484,
                0.8585000038146973,
                0.8694999814033508,
                0.875166654586792,
                0.8811666369438171,
                0.8834999799728394,
                0.8861666917800903,
                0.8891666531562805
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + GELU",
            "data": [
                0.7701666951179504,
                0.8075000047683716,
                0.8301666378974915,
                0.843999981880188,
                0.8523333072662354,
                0.8581666946411133,
                0.8619999885559082,
                0.8644999861717224,
                0.8696666955947876,
                0.8708333373069763
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + GELU",
            "data": [
                0.784333348274231,
                0.8203333616256714,
                0.8431666493415833,
                0.8576666712760925,
                0.8654999732971191,
                0.8711666464805603,
                0.8761666417121887,
                0.8815000057220459,
                0.8828333616256714,
                0.8845000267028809
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Leaky ReLU",
            "data": [
                0.7713333368301392,
                0.8073333501815796,
                0.824999988079071,
                0.8383333086967468,
                0.847000002861023,
                0.8553333282470703,
                0.862333357334137,
                0.8671666383743286,
                0.8726666569709778,
                0.874833345413208
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + Tanh",
            "data": [
                0.796833336353302,
                0.8289999961853027,
                0.8476666808128357,
                0.8581666946411133,
                0.8643333315849304,
                0.8683333396911621,
                0.8758333325386047,
                0.878333330154419,
                0.8808333277702332,
                0.8821666836738586
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Max Pooling + Tanh",
            "data": [
                0.8291666507720947,
                0.8578333258628845,
                0.8696666955947876,
                0.8734999895095825,
                0.8778333067893982,
                0.8840000033378601,
                0.8859999775886536,
                0.8881666660308838,
                0.8880000114440918,
                0.8888333439826965
            ],
            "fill": false,
            "tension": 0.2
        },
        {
            "label": "Average Pooling + ELU",
            "data": [
                0.7816666960716248,
                0.8140000104904175,
                0.8378333449363708,
                0.8548333048820496,
                0.862666666507721,
                0.8693333268165588,
                0.8744999766349792,
                0.875333309173584,
                0.8768333196640015,
                0.8778333067893982
            ],
            "fill": false,
            "tension": 0.2
        }
    ]
};



const emnistTestResults = {
    "labels": [
        "Average Pooling + ELU",
        "Average Pooling + GELU",
        "Average Pooling + Leaky ReLU",
        "Average Pooling + ReLU",
        "Average Pooling + Sigmoid",
        "Average Pooling + Swish",
        "Average Pooling + Tanh",
        "Max Pooling + ELU",
        "Max Pooling + GELU",
        "Max Pooling + Leaky ReLU",
        "Max Pooling + ReLU",
        "Max Pooling + Sigmoid",
        "Max Pooling + Swish",
        "Max Pooling + Tanh"
    ],
    "datasets": [
        {
            "label": "Test Accuracy",
            "data": [
                0.8744999766349792,
                0.8682000041007996,
                0.8697999715805054,
                0.8733000159263611,
                0.8134999871253967,
                0.871999979019165,
                0.8754000067710876,
                0.8865000009536743,
                0.8776999711990356,
                0.8870999813079834,
                0.8820000290870667,
                0.8317000269889832,
                0.876800000667572,
                0.8855999708175659
            ]
        }
    ]
};






const results = {
    mnist: {
        validation: mnistValidationResults,
        test: mnistTestResults
    },

    fashionMnist: {
        validation: fashionValidationResults,
        test: fashionTestResults
    },
    kMnist: {
        validation: kmnistValidationResults,
        test: kmnistTestResults
   },
   eMnist: {
    validation: emnistValidationResults,
    test: emnistTestResults
   }
};


function createValidationChart(dataset, results) {

    const activations = [...new Set(
        results.datasets.map(d => d.label.split(" + ")[1])
    )].sort();

    const colors = [
        "#36A2EB", "#FF6384", "#4BC0C0",
        "#FF9F40", "#9966FF", "#FFCD56", "#A3C94D"
    ];

    const datasets = results.datasets.map(d => {
        const [pooling, activation] = d.label.split(" + ");
        const color = colors[activations.indexOf(activation)];

        return {
            ...d,
            borderColor: color,
            backgroundColor: color,
            borderDash: pooling === "Average Pooling" ? [6, 4] : [],
            borderWidth: 2,
            pointRadius: 0,
            pointHoverRadius: 5
        };
    });

    const chart = new Chart(document.getElementById(`${dataset}ValChart`), {
        type: "line",
        data: { labels: results.labels, datasets },
        options: {
            plugins: {
                title: {
                    display: true,
                    text: `Validation Accuracy on ${dataset}`
                }
            }
        }
    });

    // Create controls
    const controls = document.getElementById(`${dataset}Controls`);

    function addButton(label, filter, color = "#64748b") {
        const button = document.createElement("button");

        button.textContent = label;
        button.type = "button";
        button.style.backgroundColor = color;
        button.style.color = "#fff";
        button.style.margin = "4px";
        button.style.padding = "8px 14px";
        button.style.border = "none";
        button.style.borderRadius = "5px";
        button.style.cursor = "pointer";

        button.onclick = () => {
            const indices = chart.data.datasets
                .map((d, i) => filter(d) ? i : -1)
                .filter(i => i !== -1);

            const visible = indices.every(i => chart.isDatasetVisible(i));

            indices.forEach(i => chart.setDatasetVisibility(i, !visible));

            updateButtons();
            chart.update();
        };

        controls.appendChild(button);

        return { button, filter };
    }

    const buttons = [];

    buttons.push(addButton(
        "Avg Pooling",
        d => d.label.startsWith("Average Pooling")
    ));

    buttons.push(addButton(
        "Max Pooling",
        d => d.label.startsWith("Max Pooling")
    ));

    activations.forEach((activation, i) => {
        buttons.push(addButton(
            activation,
            d => d.label.endsWith(" + " + activation),
            colors[i]
        ));
    });

    function updateButtons() {
        buttons.forEach(({ button, filter }) => {
            const indices = chart.data.datasets
                .map((d, i) => filter(d) ? i : -1)
                .filter(i => i !== -1);

            button.style.opacity =
                indices.every(i => chart.isDatasetVisible(i)) ? "1" : "0.4";
        });
    }

    const showAll = document.createElement("button");
    showAll.textContent = "Show All";
    showAll.type = "button";

    showAll.onclick = () => {
        chart.data.datasets.forEach((d, i) =>
            chart.setDatasetVisibility(i, true)
        );

        updateButtons();
        chart.update();
    };

    controls.appendChild(showAll);
}


function createTestChart(dataset, results) {

	
    const activations = [...new Set(
        results.labels.map(label => label.split(" + ")[1])
    )].sort();
	
    const datasets = ["Average Pooling", "Max Pooling"].map((pooling, i) => ({
        label: pooling,

        data: activations.map(activation => {
            const index = results.labels.indexOf(`${pooling} + ${activation}`);
            return index === -1 ? null : results.datasets[0].data[index] * 100;
        }),

        backgroundColor: i === 0 ? "#36A2EB" : "#FF6384",
        borderRadius: 4
    }));
	
	
	// add max horizontal line for each
	datasets.slice().forEach(d => {
    const maxAccuracy = Math.max(...d.data.filter(v => v !== null));

    datasets.push({
        type: "line",
        label: `Best ${d.label}: ${maxAccuracy.toFixed(2)}%`,
        data: activations.map(() => maxAccuracy),
        borderColor: d.backgroundColor,
        borderDash: [5, 5],
        borderWidth: 2,
        pointRadius: 0,
        fill: false
    });
});
	



	
    new Chart(document.getElementById(`${dataset}TestChart`), {
        type: "bar",
        data: { labels: activations, datasets },

        options: {
            responsive: true,
            plugins: {
                title: {
                    display: true,
                    text: `Test Accuracy on ${dataset}`
                },
                tooltip: {
                    callbacks: {
                        label: context =>
                            `${context.dataset.label}: ${context.parsed.y.toFixed(2)}%`
                    }
                }
            },
            
            scales: {
                y: {
              	    beginAtZero: false,
                    ticks: {
                        callback: value => value.toFixed(1) + "%"
                    },
                    title: {
                        display: true,
                        text: "Test Accuracy (%)"
                    }
                }
            }
            
        }
    });
}

Object.entries(results).forEach(([dataset, data]) => {
    createValidationChart(dataset, data.validation);
    createTestChart(dataset, data.test);
});
</script>