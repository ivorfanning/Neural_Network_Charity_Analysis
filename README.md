# Neural_Network

Neural networks are a set of algorithms that are modeled after the human brain. They are an advanced form of machine learning that recognizes patterns and features in input data and provides a clear quantitative output. In its simplest form, a neural network contains layers of neurons, which perform individual computations. These computations are connected and weighed against one another until the neurons reach the final layer, which returns a numerical result, or an encoded categorical result.

# Overview of the project analysis

By using neural networks tech and building a machine learning model, we are helping Alphabet Soup company to predict whether the applicants will be successful if funded by Alphabet Soup. Alphabet soup's business team has more than 34000 data over years, we are going to use these data to build a binary classification machine learning model, see if we can achieve 75% accuracy of sucessfully prediction.

# Results

There are two main steps of building this model which are "Data Preprocessing" and "Compiling, Training, and Evaluating the Model"

Firstly, the foremost step is "Data Preprocessing":

- What variable(s) are considered the target(s) for your model?
  
  **Since our purpose is to predict if the applicant will be sucessful funding by Alphabet Soup company, the target of this model is the value of column "IS_SUCCESSFUL"**
  ![decide target variable]()
  
- What variable(s) are considered to be the features for your model?

  **If we want to predict accuratly, the input features will be the columns that has influence on the "IS_SUCCESSFUL" results.**
  ![variable lists]()
  
- What variable(s) are neither targets nor features, and should be removed from the input data?

  **The very first of preprocessing data is to remove the unrelated columns, which are the identification columns "EIN" and "NAME". Other column should have different weighs to the prediction result.** 
  ![remove id columns]()

The second step is "Compiling, Training, and Evaluating the Model":

- How many neurons, layers, and activation functions did you select for your neural network model, and why?

  **Based on the previour example in the module 19 which contains 55 input features, the model used two layers. In our model, there are 44 features, so we try two hidden layers. In order to determine the number of nodes and activation function, we did a little research and found that for binary classification model, the best try of number of nodes is the sqrt of number of input times number of outputs, so the number of neurons in first hidden layer is sqrt of 44*2 which is close to 9, and in the second layer we tried 4 neurons. The best activation funciton for binary classification is "Relu" and "Sigmoid", keep this same as our modul 19 example.**

- Were you able to achieve the target model performance?

  **After running a few times, the accuracy stops at epoch 27, so we set the epochs we use for the model is set to 30. The accuracy of our model is around 72%, and it does not meet our expectation of 75% accuracy model preformance.**
  
- What steps did you take to try and increase model performance?

  **Since the model does not meet our expectation, firstly I tried to reduce more columns, such as "USE_CASE" and "ORGANIZATION", meantime I increased more bins for variable "APPLICATION_TYPE" and "CLASSIFICATION", the accuracy of prediction decreases after the change.
  Secondly, I used the same columns as before, but only increased number of bins for variable "APPLICATION_TYPE" and "CLASSIFICATION", the accuracy impored a little bit, around 0.02%. 
  Lastly, I increased the number of neruons in each hidden layers, and increased the epochs to 50, the model still does not have a big improvment.**

# Summary

The original deep neruon network classification model achieved 72.4% accuracy, and the optimization we tried did not give the model big improvment. We need to figout out the other ways to improve our model.

- To obtain more data in order to better optimize our model.
- To Change the model from neruon network to Random Forests for example. Based on the dataset we currently have, the random forests model may suit our need better, sicne random forests model is also suitable for binary classification problem.
- To dig deeper on the current dataset, for example the ASK_AMT column may contain outlier that cause noise, we could use visualization tech to find more fact under the data.
