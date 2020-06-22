# DS_challenge
Here I have used Python Jupyter Notebook to solve this challenge.

  Python Version :Python 3.7.6 (!python -V)
  Jupyter Notebook : 6.0.3

Packages/Liabraries used:

   import pandas as pd
   
   import numpy as np
   
   import matplotlib.pyplot as plt
   
   %matplotlib inline
   
   import seaborn as sns
   
   from sklearn.linear_model import LogisticRegression
   
   from sklearn.metrics import confusion_matrix
   
   from sklearn import metrics
   
   from sklearn.model_selection import train_test_split
   
   import pandas_profiling

Coding Style:
I have commented before each step to show the purpose.

Also I ran one command at a time to display the output of each step/command,instead of creating funstions.

But we can create different functions using def

e.g. def import_data(csv_fileName):
   
        data_df = pd.read_csv(csv_fileName, delimiter=':')
   
         return data_df
  
  we can call this function later in main() function or whereever we need to read input data, we need to  pass the parameter    csvfile with path and inputfile name
  
e.g.  data = import_data('./tide-receipt-matching-challenge/data.csv')

Steps followed to resolve this challenge
1. Understand the problem:
   we want to build a model to learn which matching features are the most successful.
   produce a trained model which can be used to order a set of transactions by likelihood of matching a receipt image. 
2. Imported the python libraries to import and explore the data
3. Imported the data csv
   Data has ':' as a delimeter so need to use delimeter value in read_csv function.
4. Explore the data to understand the. We found out that this is the supervised classification problem and we have labled data
  with bollean value ( yes/no) we need to use Logistic regression to build the model.
5. We added labeled column to classify dataset ( Matched receipt/ Not matched receipt)
6. We checked the correlation by using df.corr()
7. Defined the feature columns and non feature columns.
8. Created subsets of dataset a.with only featured columns b. with target/labels column.
9. performed data split by using train_test_split() with test size 0.2 means 20%.
10.Imported the Logistic regression model and fit the  model on train dataset.
11.Tested teh odel on test data and predicted the result.
12. We calculated the model accuacyscore,classification report and predicated probability.
13. We found out the most important features as below
   1.DateMappingMatch
   2.DescriptionMatch
   3.PredictedAmountMatch
   4.TimeMappingMatch
   5.ShortNameMatch
   6.PredictedNameMatch
   7.PredictedTimeCloseMatch
   8.AmountMappingMatch
   9.DifferentPredictedDate
   10.DifferentPredictedTime
   
 14. Next we wanted to sort the invoice_receipt data by the matching order. So I tried to use whole dataset to build a model    and to calcuate the predicted probability for whole dataset.
 15. merged te probability result into original dataset.
 16. Sorted (desc)the data on 'pred_probability' value grouped by receipt_idand company_id.
 

