# Regularization vs. Normalization vs. Initialization
## Regularization

:heavy_check_mark: **Reduce Overfitting**

:heavy_check_mark: **Drive the weights to lower values**

* L1 & L2

  * `λ` *- regularization hyperparameter, scalar*

  * What is L2-regularization actually doing?

      > L2-regularization relies on the assumption that a model with small weights is simpler than a model with large weights. Thus, by penalizing the square values of the weights in the cost function you drive all the weights to smaller values. It becomes too costly for the cost to have large weights! This leads to a smoother model in which the output changes more slowly as the input changes.

  * The implications of L2-regularization on:

    * The cost computation:

      A regularization term is added to the cost

    * The backpropagation function:

      There are extra terms in the gradients with respect to weight matrices.

    * Weights end up smaller ("weight decay"):

      Weights are pushed to smaller values.

* Dropout

  * `keep_prob` *- hyperparameter*

  * How does Dropout work?

    > When you shut some neurons down, you actually modify your model. The idea behind drop-out is that at each iteration, you train a different model that uses only a subset of your neurons. With dropout, your neurons thus become less sensitive to the activation of one other specific neuron, because that other neuron might be shut down at any time.

  * What you should remember about dropout:
    * Dropout is a regularization technique.

    * You only use dropout during training. Don't use dropout (randomly eliminate nodes) during test time.

    * Apply dropout both during forward and backward propagation.

    * During training time, divide each dropout layer by keep_prob to keep the same expected value for the activations. For example, if keep_prob is 0.5, then we will on average shut down half the nodes, so the output will be scaled by 0.5 since only the remaining half are contributing to the solution. Dividing by 0.5 is equivalent to multiplying by 2. Hence, the output now has the same expected value. You can check that this works even when keep_prob is other values than 0.5.

## Normalization

## Initialization
