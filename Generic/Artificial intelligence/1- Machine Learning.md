
## Learning modes
The process of learning is how anything can make decisions, like for example humans, animals, or AI systems.
They can adapt their behavior based on their experiences.

### Reinforcement learning
Reinforcement learning is the process of learning in an environment through feedback from an AI's behavior, it is how kids learn to walk. (TRY and ERROR) ( No one tells you how)

### Unsupervised learning
In unsupervised learning is the process of learning without training labels ( also called Clustering or Grouping). Sites like youtube use unsupervised learning to find patterns in the frames of a video and compress those frames so that videos can be streamed to us quickly.

### Supervised learning 
In supervised learning is the process of learning with training labels, it is the most widely used kind of learning when it comes to AI, and it's what we will focus on.
This is when some one knows the right answer (Called supervisor) points out mistakes during the learning process. (teacher and student)


AI it self has been inspired from the Human neurons, each neuron has 3 basic parts:
- The cell body:
- Dendrites:
- Axon: The axon of one neuron is separated from the dendrites of another neuron by a small gap called a synapse
Neurons talk to each other by passing electronic signals through synapses, as one is received the signals the electric energy inside of its cell body builds up until a threshold is crossed, then an electric signal shoots down to the axon and is passed to another neuron, then repets.

AI can learn any thing in form of supervised learning if you have labels and enough data.
It can make the simplest decision (Yes or No) which is called the binary function

There are multiple activation functions to analysis 1D graph and gives a decision like:
UNIT Step (Heaviside), Sign (SIGNUM), Linear, PIECE-WISE LINEAR, LOGISTIC (SIGMOID), HYPERBOLIC TANGENT.

Let's start with the step function (UNIT STEP) (YES OR NO) (0 or 1)
It depends on taking an input for specific specs and depend on supervised YES or NO the step function will update the decision bias to decide. (Dynamic threshold until the right decision).

We update the decision maker by update rule, if the decision is wrong we put the update rule with one, and then the AI will update the decision maker until it get the right decision from multiple True false tries.

With this way we can generate a confusion matrix to get the actually True and false to the decided True and false, and the total and this will gives you 2 new concepts ( The precision and Recall)

- Precision tells us how much you should trust your program when it says it's found something.
- Recall tells you how much your program can find of the thing you're looking for.