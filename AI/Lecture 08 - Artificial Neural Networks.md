---
tags:
  - ai
  - sheets
---

## Introduction to Artificial Neural Networks (ANNs)

Artificial Neural Networks (ANNs) are fundamental to Deep Learning. They are highly adaptable, powerful, and scalable, making them suitable for complex machine learning tasks.

**Key Applications:**

- Image classification (e.g., Google Images)
- Speech recognition (e.g., Apple's Siri)
- Recommendation systems (e.g., YouTube)
- Game playing (e.g., DeepMind's AlphaGo)

## History of ANNs

- **1943:** Warren McCulloch and Walter Pitts introduced the first computational model of biological neurons, capable of performing logical computations. This laid the groundwork for the first artificial neural network architecture.
- **1950s - 1960s:** Early successes led to optimism about achieving true artificial intelligence.
- **1960s - Early 1980s:** A period of reduced interest ("AI winter") due to unfulfilled promises and limitations of early models.
- **Early 1980s:** Revival of interest with new network architectures and improved training techniques.
- **1990s:** Other machine learning techniques like Support Vector Machines (SVMs) gained favor due to perceived better performance and theoretical foundations.
- **Present:** A resurgence of interest in ANNs, particularly Deep Learning.

## Biological Neurons

Biological neurons communicate through electrical pulses (action potentials) that travel along axons and release neurotransmitters at synapses. When a neuron receives sufficient neurotransmitters, it "fires."

- **Components:** Nucleus, cell body, axon, dendritic branches, synaptic terminals.
- **Network Computation:** Individual neurons are simple, but complex computations arise from the collective activity of many neurons working together in networks.

## Logical Computations with Neurons

McCulloch and Pitts proposed a simplified model of a biological neuron, known as an artificial neuron:

- It has one or more binary (on/off) inputs and one binary output.
- The neuron activates its output if a certain number of its inputs are active.
- These simple artificial neurons can be combined to perform logical operations like AND, OR, and NOT.

**Example of Logical Computations:** Assuming a neuron activates when at least two inputs are active:

- **AND:** Output is 1 only if both inputs are 1.
- **OR:** Output is 1 if at least one input is 1.
- **NOT:** Output is the inverse of the input.

## The Perceptron

Invented by Frank Rosenblatt in 1957, the Perceptron is a foundational ANN architecture. It uses a **Threshold Logic Unit (TLU)**, also known as a Linear Threshold Unit (LTU).

### Threshold Logic Unit (TLU)

- **Inputs and Output:** Inputs and output are numerical.
- **Weights:** Each input connection has an associated weight.
- **Linear Combination:** The TLU first computes a weighted sum of its inputs plus a bias term: z=w1x1+w2x2+⋯+wnxn=wTx+bz=w1​x1​+w2​x2​+⋯+wn​xn​=wTx+b
- **Activation Function:** A step function is applied to the result: y^=f(z)=step(z)={1if z≥00if z<0y^​=f(z)=step(z)={10​if z≥0if z<0​ where y^y^​ is the predicted output.

### Activation Functions in Perceptrons

Common activation functions include:

- **Linear Function:** y=f(net)=K⋅nety=f(net)=K⋅net
- **Threshold Function (Heaviside):** y=f(net)={1if net≥00if net<0y=f(net)={10​if net≥0if net<0​
- **Sigmoid Function:** y=f(net)=11+e−nety=f(net)=1+e−net1​
- **Hyperbolic Tangent Function:** y=f(net)=1−e−net1+e−nety=f(net)=1+e−net1−e−net​

The most common step function for perceptrons is the **Heaviside step function**. A single LTU can perform binary classification if the data is linearly separable. Training an LTU involves finding the optimal weights wiwi​ and bias bb.

### Perceptron Architecture

- A perceptron can consist of one or more TLUs arranged in a single layer.
- This layer is fully connected, meaning every TLU receives input from every input feature. This is also known as a **dense layer**.
- The inputs form the **input layer**.
- The layer of TLUs producing the final outputs is the **output layer**.
- An additional bias term (often represented as x0=1x0​=1) is typically included, sometimes using a dedicated "bias neuron" that always outputs 1.

A perceptron with multiple output neurons can perform multi-class classification simultaneously.

## Perceptron Training: Hebb's Rule (Hebbian Learning)

Rosenblatt's perceptron training algorithm was inspired by Donald Hebb's rule, which suggests that the connection strength between two neurons increases if they fire simultaneously.

The perceptron learning rule is a variant that uses error feedback:

- The connection weights are adjusted to reduce the error between the predicted and target outputs.
- The perceptron is trained on one instance at a time.
- For each output neuron that makes a wrong prediction, weights are reinforced to favor the correct outcome.

### Perceptron Learning Rule

The update rule for a weight wijwij​ (between input ii and output jj) is: wij(next step)=wij+η(yj−y^j)xiwij​(next step)=wij​+η(yj​−y^​j​)xi​ Where:

- wijwij​ is the connection weight.
- ηη is the learning rate (a small positive constant, e.g., 0 < ηη < 1).
- yjyj​ is the target output for neuron jj.
- y^jy^​j​ is the predicted output of neuron jj.
- xixi​ is the input value from feature ii.

### Perceptron Convergence Theorem

- If the training data is **linearly separable**, the perceptron learning algorithm is guaranteed to converge to a solution.
- This algorithm is similar to Stochastic Gradient Descent (SGD).

## Perceptron Weaknesses

- **Inability to solve non-linearly separable problems:** A single perceptron cannot learn patterns like the Exclusive OR (XOR) problem because its decision boundary is linear.
- **Limited expressiveness:** Can only handle linearly separable data.

## Multi-Layer Neural Networks (MLPs)

To overcome the limitations of single-layer perceptrons, multiple layers of neurons can be stacked. This creates a **Multi-Layer Perceptron (MLP)**.

### How a Multi-Layer NN Works

1. **Input Layer:** Receives the features of the training data.
2. **Hidden Layers:** One or more layers between the input and output layers. They process the information from the previous layer through weighted connections and activation functions.
3. **Output Layer:** Produces the network's final prediction.
4. **Feed-Forward:** Information flows in one direction, from input to output, without cycles.
5. **Non-linear Regression:** MLPs can approximate complex, non-linear functions by combining multiple linear and non-linear transformations across layers.

## Backpropagation Algorithm

Backpropagation is the standard algorithm for training Multi-Layer Neural Networks. It's an iterative process that minimizes the error between the network's predictions and the target values.

### The Two Passes of Backpropagation

1. **Forward Pass:**
    - Input data is fed into the network.
    - Signals propagate forward through each layer, calculating the output of each neuron.
    - The network's final prediction is generated.
    - The error between the target output and the predicted output is calculated.
2. **Backward Pass:**
    - The calculated error is propagated backward from the output layer through the hidden layers to the input layer.
    - At each layer, weights are adjusted to reduce the error. This is done using gradient descent on the error function.

### Mathematical Formulation of Backpropagation

For a neuron jj with activation yjyj​ and an error δjδj​:

- **For an output neuron jj:** δj=∂E∂netj=∂E∂yj∂yj∂netjδj​=∂netj​∂E​=∂yj​∂E​∂netj​∂yj​​ If the error EE is mean squared error E=12(tj−yj)2E=21​(tj​−yj​)2, then ∂E∂yj=−(tj−yj)∂yj​∂E​=−(tj​−yj​). If the activation function is sigmoid, ∂yj∂netj=yj(1−yj)∂netj​∂yj​​=yj​(1−yj​). So, for sigmoid output neurons: δj=(tj−yj)yj(1−yj)δj​=(tj​−yj​)yj​(1−yj​) (Note: The provided material uses δj=yj(1−yj)(tj−yj)δj​=yj​(1−yj​)(tj​−yj​), which is equivalent.)
    
- **For a hidden neuron jj:** The error δjδj​ is a weighted sum of the errors of the neurons in the next layer that it connects to: δj=∂E∂netj=∑k∂E∂netk∂netk∂yj∂yj∂netj=∑kδkwkj∂yj∂netjδj​=∂netj​∂E​=k∑​∂netk​∂E​∂yj​∂netk​​∂netj​∂yj​​=k∑​δk​wkj​∂netj​∂yj​​ For sigmoid hidden neurons: δj=yj(1−yj)∑kδkwkjδj​=yj​(1−yj​)k∑​δk​wkj​
    
- **Weight Update Rule:** The change in weight ΔwijΔwij​ for the connection from neuron ii to neuron jj is: Δwij=ηδjxiΔwij​=ηδj​xi​ Where xixi​ is the output of neuron ii (or the input feature if ii is an input). The new weight is wij(new)=wij(old)+Δwijwij​(new)=wij​(old)+Δwij​.
    

### Backpropagation Example Walkthrough

Let's trace a simplified part of the provided example:

**Network Structure:** Input layer: x1,x2x1​,x2​ Hidden layer: H3,H4H3​,H4​ Output layer: Y5Y5​

**Weights (Initial):** w13=0.1,w23=0.8w13​=0.1,w23​=0.8 w14=0.4,w24=0.6w14​=0.4,w24​=0.6 w35=0.3,w45=0.9w35​=0.3,w45​=0.9

**Input:** x1=0.35,x2=0.9x1​=0.35,x2​=0.9 **Target Output:** Ytarget=0.5Ytarget​=0.5 **Learning Rate:** η=1η=1

**Forward Pass:**

1. **Calculate net input to H3H3​:** a3=w13x1+w23x2=(0.1×0.35)+(0.8×0.9)=0.035+0.72=0.755a3​=w13​x1​+w23​x2​=(0.1×0.35)+(0.8×0.9)=0.035+0.72=0.755
2. **Calculate output of H3H3​ (using sigmoid):** y3=11+e−0.755≈0.68y3​=1+e−0.7551​≈0.68
3. **Calculate net input to H4H4​:** a4=w14x1+w24x2=(0.4×0.35)+(0.6×0.9)=0.14+0.54=0.68a4​=w14​x1​+w24​x2​=(0.4×0.35)+(0.6×0.9)=0.14+0.54=0.68
4. **Calculate output of H4H4​:** y4=11+e−0.68≈0.6637y4​=1+e−0.681​≈0.6637
5. **Calculate net input to Y5Y5​:** a5=w35y3+w45y4=(0.3×0.68)+(0.9×0.6637)=0.204+0.59733=0.80133a5​=w35​y3​+w45​y4​=(0.3×0.68)+(0.9×0.6637)=0.204+0.59733=0.80133
6. **Calculate output of Y5Y5​:** y5=11+e−0.80133≈0.69y5​=1+e−0.801331​≈0.69
7. **Calculate initial error:** Error=Ytarget−y5=0.5−0.69=−0.19Error=Ytarget​−y5​=0.5−0.69=−0.19

**Backward Pass:**

1. **Calculate error δ5δ5​ for output neuron Y5Y5​:** δ5=y5(1−y5)(Ytarget−y5)=0.69(1−0.69)(−0.19)=0.69×0.31×(−0.19)≈−0.0406δ5​=y5​(1−y5​)(Ytarget​−y5​)=0.69(1−0.69)(−0.19)=0.69×0.31×(−0.19)≈−0.0406
2. **Calculate error δ3δ3​ for hidden neuron H3H3​:** δ3=y3(1−y3)(w35δ5)=0.68(1−0.68)((0.3)(−0.0406))=0.68×0.32×(−0.01218)≈−0.00265δ3​=y3​(1−y3​)(w35​δ5​)=0.68(1−0.68)((0.3)(−0.0406))=0.68×0.32×(−0.01218)≈−0.00265
3. **Calculate error δ4δ4​ for hidden neuron H4H4​:** δ4=y4(1−y4)(w45δ5)=0.6637(1−0.6637)((0.9)(−0.0406))=0.6637×0.3363×(−0.03654)≈−0.0082δ4​=y4​(1−y4​)(w45​δ5​)=0.6637(1−0.6637)((0.9)(−0.0406))=0.6637×0.3363×(−0.03654)≈−0.0082

**Weight Updates:**

- **Update w35w35​:** Δw35=ηδ5y3=1×(−0.0406)×0.68≈−0.0276Δw35​=ηδ5​y3​=1×(−0.0406)×0.68≈−0.0276 w35(new)=w35(old)+Δw35=0.3+(−0.0276)=0.2724w35​(new)=w35​(old)+Δw35​=0.3+(−0.0276)=0.2724
- **Update w13w13​:** Δw13=ηδ3x1=1×(−0.00265)×0.35≈−0.00092Δw13​=ηδ3​x1​=1×(−0.00265)×0.35≈−0.00092 w13(new)=w13(old)+Δw13=0.1+(−0.00092)=0.0991w13​(new)=w13​(old)+Δw13​=0.1+(−0.00092)=0.0991
- **Update w23w23​:** Δw23=ηδ3x2=1×(−0.00265)×0.9≈−0.00239Δw23​=ηδ3​x2​=1×(−0.00265)×0.9≈−0.00239 w23(new)=w23(old)+Δw23=0.8+(−0.00239)=0.7976w23​(new)=w23​(old)+Δw23​=0.8+(−0.00239)=0.7976
- **Update w45w45​:** Δw45=ηδ5y4=1×(−0.0406)×0.6637≈−0.0269Δw45​=ηδ5​y4​=1×(−0.0406)×0.6637≈−0.0269 w45(new)=w45(old)+Δw45=0.9+(−0.0269)=0.8731w45​(new)=w45​(old)+Δw45​=0.9+(−0.0269)=0.8731
- **Update w14w14​:** Δw14=ηδ4x1=1×(−0.0082)×0.35≈−0.00287Δw14​=ηδ4​x1​=1×(−0.0082)×0.35≈−0.00287 w14(new)=w14(old)+Δw14=0.4+(−0.00287)=0.3971w14​(new)=w14​(old)+Δw14​=0.4+(−0.00287)=0.3971
- **Update w24w24​:** Δw24=ηδ4x2=1×(−0.0082)×0.9≈−0.00738Δw24​=ηδ4​x2​=1×(−0.0082)×0.9≈−0.00738 w24(new)=w24(old)+Δw24=0.6+(−0.00738)=0.5926w24​(new)=w24​(old)+Δw24​=0.6+(−0.00738)=0.5926

After updating weights, another forward pass would be performed with the new weights to see if the error has decreased. This process repeats until convergence.

## Tuning Hyper-parameters

The performance of ANNs depends heavily on hyper-parameters, which are set before training. Tuning these is crucial.

**Key Hyper-parameters:**

- **Network Topology:**
    - Number of hidden layers.
    - Number of neurons per hidden layer.
- **Activation Function:** Choice of function (e.g., sigmoid, ReLU, tanh).
- **Learning Rate (ηη):** Controls the step size during weight updates.
- **Initial Weights:** The starting values of the weights.
- **Batch Size:** The number of training instances used in one update step (for mini-batch gradient descent).
- **Number of Epochs:** The total number of times the training dataset is passed through the network.

Tuning often involves experimentation and techniques like grid search or random search.

## Neural Networks as a Classifier

### Strengths

- **Noise Tolerance:** Can handle noisy data well.
- **Generalization:** Ability to classify patterns not seen during training.
- **Versatility:** Suitable for continuous-valued inputs and outputs.
- **Real-world Applications:** Successful in various domains (e.g., handwriting recognition).
- **Parallelism:** Algorithms are inherently parallelizable.
- **Rule Extraction:** Techniques exist to extract symbolic rules from trained networks.

### Weaknesses

- **Training Time:** Can require significant time to train, especially for large datasets and complex models.
- **Hyper-parameter Tuning:** Requires empirical determination of parameters like network structure.
- **Poor Interpretability:** Difficult to understand the exact meaning of learned weights and the decision-making process of hidden units ("black box" nature).
