# Wine Recognition with Multilayer Perceptron

To achieve Multiple label classification using Multilayer Perceptron, you can either use Categorical Cross Entropy or Sparse Categorical Cross Entropy as loss functions, both suitable for multi-class classification problems.

The choice between them depends on the format of your target labels.

The focus of this repository is to compare both loss function with same MLP architecture.
​
### Why use One-Hot Encoding with Categorical Crossentropy ?
Categorical Crossentropy is typically used in multi-class classification tasks where each input sample belongs to one and only one class and, one-hot encoded labels have to be used for the categorical cross-entropy loss.
​
### What is the difference between sparse_categorical_crossentropy and categorical_crossentropy?
Both have the same loss function and are ultimately doing the same thing, only difference is in the representation of the true labels.
​
- **Categorical Cross Entropy** : Use this crossentropy loss function when there are two or more label classes. We expect labels to be provided in a one_hot representation.
- **Sparse Categorical Cross Entropy** : Use this crossentropy loss function when there are two or more label classes. We expect labels to be provided as integers.


### Steps after Standard scaling and splitting the data

if you use Sparse Categorical Cross Entropy :

- Set input layer to : (number of features, )
- Set output layer to number of labels and use softmax activation function
- Use Sparse Categorical Cross Entropy loss function

​
if you use Categorical Cross Entropy :

- Convert target labels to one-hot encoded vectors (with tf.one_hot or keras.to_categorical)
- Set input layer to : (number of features, )
- Set output layer to number of labels and use softmax activation function
- Use Categorical Cross Entropy loss function

After trying both losses functions, in this very context, both Wine Recognition models converge after around a 100 Epochs. Note that without Standard Scaling the data, a lot less Epochs are needed to converge. Since the input features have significantly different scales, we scaled it to a similar range, to achieve better performance.
​
## What is in this repository ?

* MLPClassifier_CCE.ipynb : MLP classification where loss function used is Categorical Cross Entropy.
* MLPClassifier_SCCE.ipynb : MLP classification where loss function used is Sparse Categorical Cross Entropy.
