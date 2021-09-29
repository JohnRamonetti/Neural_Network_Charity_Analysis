# Neural_Network_Charity_Analysis

## OVERVIEW
### PURPOSE:  The purpose of the current analysis was to determine whether success can be predicted for organizations chosen to receive funding from Alphabet Soup Inc.   A dataset (charity_data.csv) was provided containing information about 34,000+ organizations that have received funding from Alphabet Soup in the past.  After preprocessing the data, a machine-learning model was used to analyze the data.  The model was then evaluated and optimized.

## RESOURCES
  - Source Files: [charity_data.csv](Resources/charity_data.csv)
  - Software: Python 3.7.7, Jupyter Notebook, Pandas, sklearn, tensorflow


## RESULTS
  - Data Preprocessing
     - What variable(s) are considered the target(s) for your model?  The "IS_SUCCESSFUL" field indicates whether the funding was considered successful, and was therefore used as our target for the machine learning model.
     - What variable(s) are considered to be the features for the model?  The following fields were utilized as features for in our analysis:
        - APPLICATION_TYPE—Alphabet Soup application type
        - AFFILIATION—Affiliated sector of industry
        - CLASSIFICATION—Government organization classification
        - USE_CASE—Use case for funding
        - ORGANIZATION—Organization type
        - STATUS—Active status
        - INCOME_AMT—Income classification
        - SPECIAL_CONSIDERATIONS—Special consideration for application
        - ASK_AMT—Funding amount requested
        - Additionally, the "NAME" field, which was initially removed as unmeaningful, was later found to have a positive predictive correlation and was therefore included as a feature for the analysis.

   - What variable(s) are neither targets nor features, and should be removed from the input data?
          The "EIN" (Employee Identification Number) field is a unique identifier for each organization and was of no value for the analysis.  It was removed during pre-processing of the data.

  - Compiling, Training, and Evaluating the Model
    - How many neurons, layers, and activation functions did you select for your neural network model, and why?
        During optimization, we found that 2 hidden layers seemed to optimize our accuracy.  The first had 80 neurons, and the second had 30.  The "ReLu" activation function seemed most effective ("Sigmoid" was used for the output layer).
    - Were you able to achieve the target model performance?
        Several permutations of layers/neurons and other manipulations had little impact on the accuracy results.  However, we found that including the "NAME" field actually had a significant impact and , after [binning the low-frequency "NAMEs"](Images/binning.png), the model's accuracy was increase to [78%](Images/optimized.png), a notable increase from the initial accuracy of [72-73%.](Images/initial.png)
    - What steps did you take to try and increase model performance?  
        In attempting to optimize the model, we tried different activation functions, optimizers, numbers of layers and nodes, as well as manipulating the size and number of data buckets.

## SUMMARY
### Overall, we were surprised to find that most of our manipulations to optimize the model were very limited in their impact.  We were also surprised to find the positive predictive effect of including the "NAME" field.  Ultimately, we think it would be worth trying other machine learning algorithms to see if their accuracy is better.  We'd try Random Forest for starters, but other logistic regression models might be valuable as well.

####################################################


