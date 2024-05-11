# credit-risk-classification

# Module 12 Report

## Overview of the Analysis
### Purpose
The purpose for the analysis on the lending data was to determine credit risk using data from a peer to peer lending company.
I was trying to predict whether opportunities were good lending options or high risk lending options.

### Process
I set up the data with y being the "loan_status" column and x being the rest of the columns.
I then set up my test_train_split with x_train, x_test, y_train, and y_test using the data.
I ran a logistic regression using solver "lbfgs" and random_state = 1 due to the instructions (I like using 42 for the Hitchiker's reference).
I fit my regression with x_train and y_train, and then I ran the predictions to x_test.
I counted the number of values with each prediction to determine if one outweighed the other. In this case good lending options outweighed bad by over 18,000 instances, which is significant in a model that has only 19,384 values.
After that I ran the predictions and y_test through a confusion matrix an printed a classification report.

## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model:
    * This model gave us an accuracy on the f1-score of 99%.
    * Precision was 100 % for good lending options(0) and 85% for bad lending options(1). Macro avg was 92%.
    * Recall was 99% for good lendign options(0) and 91% for bad(1). Macro avg was 95%
    * Macro avg for F-1 score was 94%

## Summary

The accuracy of the f1-score is 99 percent, but since the accuracy can be pretty easily skewed by such a large difference between the majority class (healthy loans) and the minority class (high risk loans), I think it would be more helpful to actually look at the other values associated.

Looking at the f1-score, which will give us the harmonic mean of precision and recall, the model has 94% accuracy on average. The reason I used F1 instead of precision or recall is because it would depend on the banks lending policies whether they were more concerned about. Looking specifically at recall will give more fale positives (in this case more loans listed as high-risk), which would protect the company in question from more risks, but may frustrate customers and lead to a drop off. If they focus on precision they will end up with more false negatives(meaning false healthy loans in this case), which opens them up to more risky loans. 

I would personally focus on the recall aspect since most banks like to avoid risk when it comes to loans specifically (as opposed to say investments, where some risk is typically more tolerated), but there are lenders who may focus on the higher risks and offest potential losses with higher interest rates or other non-payment penalties.

This model seems to do a good job with it's predictions, but I think there are likely other models that would work a little better given the bad lending options are the ones that would typically hurt a lender, and they may want more accuracy on that end than 91%, which was the highest in this model.
