# **Implementation of a SDR classifier.**

A classifier in machine learning is an algorithm that automatically orders or categorizes data into one or more set of “classes”. The SDR classifier takes the form of a single layer classification network that takes SDRs as input and outputs a predicted distribution of classes.The SDR Classifier accepts a binary input pattern from the level below (the "activationPattern" - the vector of Temporal Memory’s active cells) and information from the sensor and encoders (the "classification") describing the true (target) input.

![image](https://user-images.githubusercontent.com/116737927/213930553-b17a2fa3-12fd-451c-8975-28eb94ce7ce8.png)

Fig1. SDR Classifier in relation to the other modules of an HTM Network

**SDR** by books is known as Sparse Distributed Representations. It is the fundamental data structure which is used to represent and model the information in brain and in HTM systems. Generally, computers represents the infromation in form of traditional data structures such as trees, lists, ASCII representaions etc. These data structures are well suited when information is discrete and well defined. However, information is brain or in any HTM system is neither discrete nor well defined. Hence we represent the information in form of SDR, just like the brain does.

A SDR contains thousand of bits and each bit corresponds to a neuron. At any given point in time, for a given set of bits, certain bits are active and rest of them are inactive. This arrangement represent a thing at that point in time. At next point in time, representation changes making different bits active. Now this arrangement represents an another thing. As the time elapses and machine learns from various inputs, we have multiple SDRs representing muliple things and pattern of real world. These SDR can be associated, linked and compared to predict and classify new types of things which are completely unknown to the system.

The SDR classifier maps input patterns to class labels. There are as many output units as the number of class labels or buckets (in the case of scalar encoders). The output is a probabilistic distribution over all class labels. During inference, the output is calculated by first doing a weighted summation of all the inputs, and then perform a softmax nonlinear function to get the predicted distribution of class labels During learning, the connection weights between input units and output units are adjusted to maximize the likelihood of the model.

**Methods to be implemented:**

- compute(recordNum, patternNZ, classification, learn, infer)
  : Process one input sample
- infer(patternNZ, actValueList)
  : Return the inference value from one input sample.
- inferSingleStep(patternNZ, weightMatrix)
  : Perform inference for a single step. Given an SDR input and a weight matrix, return a predicted distribution.
- static create(\*args, \*\*kwargs)
  : Create a SDR classifier factory. The implementation of the SDR Classifier can be specified with the “implementation” keyword argument.

**Project outline:**

1. Finding input dataset and preprocessing and converting it to the format accepted by SDR classifier as input.
2. implementing Learning function
3. implementing Inference function
4. Unit tests
5. Training the model and enhancing the results by trying different parameter values.