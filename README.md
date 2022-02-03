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
       - The special consideration variable only has yes and no two categories, so I removed the no one to improve the performance
       - ![step2](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/step2.PNG)
       
     3. Increase the number of layers and find the balanced number of neurons
       -![step3-1](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/step3-1.PNG)
       -![step3-2](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/step3-2.PNG)
       -![step3-3](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/step3-3.PNG)
       - Increase the number of layers to three compared to two. Increase the number of neurons for each layer first, considering the outfitting potential, decrease the number accordingly.
       
     4. Change the activation function for each layer
        -Try different activation function first
        -![step4-1](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/step4-1.PNG)
        -![step4-2](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/step4-2.PNG)
        -![step4-3](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/step4-3.PNG)
        -The performance improved when change to the sigmoid function as belows, so increase the use of sigmoid function
        -![proof-1](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/proof4-1.PNG)
        -![proof-2](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/proof4-2.PNG)
        -![proof-3](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/proof4-3.PNG)
       
     5. Increase the number of epochs
        -Increase the number of epochs from 50 to 80 to see whether there is an improvement
        -![step5](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/step5-1.PNG)
        -![step5-2](https://github.com/xueying-lin/Neural_Network_Charity_Analysis/blob/dfbab15225fd0d393b6f06e493ec7c5cfcbbb9eb/resources/step5-2.PNG)
     

## Summary
The overall model has the accuracy rate of 72.5% after optimization. The initial accuracy rate is about 72.6%. Although the rate seems similar, the accuracy rate for each epochs improved quickly for the final model. 

The random forest classifiers can be used for this dataset. First, the random forest classifiers can perform faster than the deep learning model. Second, the data here is tabular. The random forest classifiers performs well on larget tabular dataset and can achieve comparable predictive accuracy.
