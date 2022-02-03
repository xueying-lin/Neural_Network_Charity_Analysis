# Neural_Network_Charity_Analysis

## Overview of the analysis
Beks is the data analyst of the non-profit organization, Alphabet Soup. Beks needs to help figure out which organizations worth donations and which ones with high risk.
- Purpose: Use the current dataset to build a neural network model, which can accurately detect the organizations with high risk to avoid the failed donation.

## Results
### Data Preprocessing
   - **Target variables**: *IS_SUCCESSFUL* variable, whether the donation for that application is used effectively or not. 
   - **Features variables**: *APPLICATION_TYPE*, *AFFLIATION*, *CLASSIFICATION*, *USE_CASE*, *ORGANIZATION* (Organization type), *INCOME_AMT* (income classification), *SPECIAL_CONSIDERATIONS* (special consideration for application), *ASK_AMT*(Funding amount requested) 
   - **Removed variables**: *EIN*, *NAME*, *STATUS* (Active status). The variables are removed due to the irrelavent to the models
  
### Compiling, Training, and Evaluating the Model
   - There are three attempts to optimize the performance of the deep learning module. In the final attemps, the model used **three hidden layers.**
        -  The first layer has *90* neurons, using *relu* activation function
        -  The second layer has *55* neurons, using *sigmoid* activation function
        -  The third layer has *30* neurons, using *sigmoid* activation function
        -  ![Optimzation 3](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/8caf00599cb890246d05c4067e1f5634c4378b8d/resources/final_layers_neurons.PNG)
   - Unable to achieve the target model performance: 75%
         - The performance for the final attempt is 72.5%
         - ![Final_accuracy](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/8caf00599cb890246d05c4067e1f5634c4378b8d/resources/final_accuracy.PNG)
   - There are **five steps** taken to optimize the performance
     1. Remove the unrelated variables to optimize the feature variables
       - ![Remove the EIN, NAME, and STATUS variable](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/8caf00599cb890246d05c4067e1f5634c4378b8d/resources/step1.PNG) 
     2. Remove the redundant feature variables
     3. Increase the number of layers and find the balanced number of neurons
     4. Change the activation function for each layer
     5. Increase the number of epochs

## Summary
overall results of the deep learning model. recommendation for how a different model could solve this classification problem, and explain why
