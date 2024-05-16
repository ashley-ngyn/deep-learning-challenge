# Alphabet Soup Charity #
deep learning challenge

## Instructions ##
1. Preprocess the Data
    * StandardScaler
    * train_test_split
2. Compile, Train, and Evaluate the Model
    * neural network with TensorFlow
3. Optimize the Model
    * optimize model to achieve predictive accuracy higher than 75%

## Overview ##
The purpose of this analysis is to create a binary classifer using a deep learning neural network. It was done for a nonprofit foundation Alphabet Soup, who wants a tool to help select applicants for funding with the best chance of success. Alphabet Soup provided a dataset that contained more than 34,000 organizations that received funding from Alphabet Soup from over the years. The CSV provided included information such as: identication (EIN and name), application types, affliation, government organization classifcation, use case for funding, organization type, status (active or not), income classification, special considerations, ask amount for funding, successfulness use of funds. <br/>

The analysis involved preprocessing the dataset by dropping unnecessary columns, assigning categorical variables, and splitting the data into training and testing variables. After this, the neural network model is created, trained, and evaluated to determine the loss and accuracy. The goal of this analysis is to achieve a predictive accuracy greater than 75%, which may include various methods such as adjusting bins, changing neuron values, adding/removing hidden layers, or adjusting epoch values. <br/>

## Results ##
#### Data Preprocessing #### 
    * Target Variable:
        * "IS_SUCCESSFUL" column, which determines whether or not the funds were successful
    * Feature Variables:
        * All columns aside from "IS_SUCCESSFUL"
    * Variables Removed (not target or features):
        * "EIN" column removed since it only represented a identification number
        * "NAME" column was also removed initially, but later added because it improved the models accuracy.
#### Compiling, Training, and Evaluating the Model #### 
* For the intial model, the neuron unots were 1 and used a sigmoid activation layer. The layers used were 8(relu), 16(sigmoid), and 32(sigmoid) with 100 epochs. <br/>

![1](https://github.com/ashley-ngyn/deep-learning-challenge/assets/150317761/e798c6dd-a2fc-421b-87d7-5c977cec6da6) <br/>
 
 The predictive accuracy was 72.38% with a loss of 0.5557. <br/>

![2](https://github.com/ashley-ngyn/deep-learning-challenge/assets/150317761/1a9d0907-ac2b-4510-90bf-917317cfc686)
<br/>

 * In the next attempt for optimization, there were more neurons added and the epochs were changed from 100 to 50.<br/>

 ![3](https://github.com/ashley-ngyn/deep-learning-challenge/assets/150317761/b685b3b9-6fbc-48ff-a7c4-f3a36d21ab17)
<br/>

 The predictive accuracy was 72.50% with a loss of 0.5569. Although these results were slightly better than the previous results, it did not reach an accuracy of 75%. Thus, futher optimization needed to be done. <br/>

![4](https://github.com/ashley-ngyn/deep-learning-challenge/assets/150317761/20c38d93-1dd7-475e-b5b6-74141d019e93) <br/>

 In the final attempt, instead of using application types as the bins, names were used instead. This will provide more data for the neural network to use for testing.<br/>

![5](https://github.com/ashley-ngyn/deep-learning-challenge/assets/150317761/ea60cc3e-4c44-495b-8e21-067e5fc06559) <br/>

 In addition to changing the bins from application type to name, the neuron sizes were slightly changed but seeing from the previous optimization model it should not have made such a difference. Epochs were changed back to 100 seeing the performance did better with that versus 50.<br/>

![6](https://github.com/ashley-ngyn/deep-learning-challenge/assets/150317761/4eb5e3cd-71c5-474e-aa87-27183c75c8c1)
<br/>

 From the results, the predictive accuracy was 76.06% with a loss of 0.4800. By adding name was a bin inplace of application type, the model had more accuracy and a smaller loss.<br/>

![7](https://github.com/ashley-ngyn/deep-learning-challenge/assets/150317761/401008b7-dfee-4c4e-9ee4-d6a96ef58936)
<br/>

## Summary ##
The neural network model was able to reach 76% accuracy after multiple optimization attempts. In order to achieve optimization, various changes may be done to the neuron values, hidden layers, feature values, binning values, and epoch value. In this specific models, the change of neuron values and hidden layers slightly increased the accuracy, but not enough to reach 75%, so the changing of the binning value from applicationt type to name provided the model with better fit data to reach accuracy over 75%. But with multiple optimization attempts, there may be other models suggested for better accuracy. <br/>

Other models such as Random Forest Classifier or Support Vector Machine (SVM) are recommended because these models have been shown to be more effective with binary classification models. With these models, it would be possible to achieve higher accuracy with less optimization attempts. In addition, both models are better at handling numerical and categorical variables alone with outliers. Overall, these models are worth trying in order to achieve accuracy higher than 76% which was done in this analysis.

## Code Sources ##
[stackoverflow](https://stackoverflow.com/questions/50447222/google-colaboratory-keras-save-model-in-hdf5-file-format-and-download-it-to-l) : used to download model from google collaborate
