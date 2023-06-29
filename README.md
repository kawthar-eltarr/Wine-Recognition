# Wine Recognition

To achieve Multiple label classification using Multilayer Perceptron, you can either use Categorical Cross Entropy or Sparse Categorical Cross Entropy as loss functions, both suitable for multi-class classification problems.

The choice between them depends on the format of your target labels.
​
​
### Why use One-Hot Encoding with Categorical Crossentropy ?
Categorical Crossentropy is typically used in multi-class classification tasks where each input sample belongs to one and only one class and, one-hot encoded labels have to be used for the categorical cross-entropy loss.
​
### What is the difference between sparse_categorical_crossentropy and categorical_crossentropy?
Both have the same loss function and are ultimately doing the same thing, only difference is in the representation of the true labels.
​
- **Categorical Cross Entropy** : Use this crossentropy loss function when there are two or more label classes. We expect labels to be provided in a one_hot representation.
- **Sparse Categorical Cross Entropy** : Use this crossentropy loss function when there are two or more label classes. We expect labels to be provided as integers.


### Steps after scaling and splitting the data

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

After trying both losses functions, in this very context, the Wine Recognition model converges faster when using Sparse Categorical Cross Entropy.
​
## What is in this repository ?

* MLPClassifier_CCE.ipynb : MLP classification where loss function used is Categorical Cross Entropy.
* MLPClassifier_SCCE.ipynb : MLP classification where loss function used is Sparse Categorical Cross Entropy.
