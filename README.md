# Deep Learning Challenge
-----------
# Alphabet Soup Funding Final Analysis
-----------
## Purpose
In this project, we'll use a deep learning model, to create a binary classification model that can predict if an Alphabet Soup-funded organization will be successful based on the features in the dataset. I will be using machine learning and neural networks to analyze a CSV containing over 34,000 organizations that have received funding from Alphabet Soup, using metadata columns to predict the success of future applicants.

## Analysis
The first model uses 2 hidden layers with 15 and 10 nodes and ReLu activation. I performed 100 trials. The results were 72.65% accuracy and 0.55 loss during validation with the test data.
Attempting to reach an accuracy of 75% by optimizing the model, I attempted to changing the number of bins by increasing the 'CLASSIFICATION' cutt of to 2500 or reducing it to 500. I also tried changing the 'APPLICATION_TYPE' cutt off 1000 and 100. I tried changing the activation type to tanh, leaky_relu, and sigmoid. I changed the number of hidden layers increasing them to 6, and changed the number of nodes between 3 and 100. I was never able to achieve an accuracy of greater than 73%.

I did some investigating and found examples of using auto-optimization. I set up a function to test multiple variables at one time. By setting the hyperparameters to test multiple variations, I was able to get an accuracy of 73.15% and loss of 0.55. 

### Data Preprocessing
- What variable(s) are the target(s) for your model?
    - The target for each model was the IS_SUCCESSFUL column. The ultimate goal is to predict which applicants will be successful, so we will utilize all other features to ultimately make a prediction
- What variable(s) are the features for your model?
    - The available features for my model are: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT	
- What variable(s) should be removed from the input data because they are neither targets nor features?
    - The variables removed are: EIN and NAME
#### Compiling, Training, and Evaluating the Model
- How many neurons, layers, and activation functions did you select for your neural network model, and why?
    - In the first model, I used 2 hidden layers with 100 neurons each utilizing the ReLU activation. For the output layer the Sigmoid activation was used. I chose ReLU as I could immediately identify by looking at my data that it was non-linear, so I felt that would be the optimal activation to begin with.
    - In the second model, I attempted to use the LeakyReLU, Tanh, and Sigmoid activations, increased and decreased the number of hidden layers and nodes and changed the number of bins in my test and training data.
    - In my final model, I chose auto-optimization to get the best model and hyperparameters to attempt accuracy higher than 75%. This model has 6 layers, with the first layer having 43 nodes and the remaining layers having 21, 19, 77, 93, and 3 nodes respectively. The activation function used throughout this model is leaky_relu.

- Were you able to achieve the target model performance?
 	- The highest I was able to achieve was 73.15%.  I had some trials with accuracy as low as 55%.

### Alternative Solutions
I believe a random forest could work well for this problem because it is a type of machine learning that excels at grouping, and could likely help predict funding for organizations. Also random forests work by combining many decision trees together, which can help to prevent overfitting which was an issue I encountered.

