# Starbucks Portfolio Optimization

## **Table of Contents**
1. [Introduction](README.md#Introduction)
2. [File Description](README.md#File-Description)
3. [Libraries used](README.md#libraries-used)
4. [Results](README.md#results)

## **Introduction**<br/>

  The dataset provided in this portfolio optimization was originally used as a take-home assignment provided by Starbucks for their job candidates. The data for this exercise consists of about 120,000 data points split in a 2:1 ratio among training and test files. In the experiment simulated by the data, an advertising promotion was tested to see if it would bring more customers to purchase a specific product priced at $10. Since it costs the company 0.15 to send out each promotion, it would be best to limit that promotion only to those that are most receptive to the promotion. Each data point includes one column indicating whether or not an individual was sent a promotion for the product, and one column indicating whether or not that individual eventually purchased that product. Each individual also has seven additional features associated with them, which are provided abstractly as V1-V7.
  
  Task is to use the training data to understand what patterns in V1-V7 indicate that a promotion should be provided to a user. Specifically, your goal is to maximize the following metrics:
  
  * **Incremental Response Rate (IRR)**

IRR depicts how many more customers purchased the product with the promotion, as compared to if they didn't receive the promotion. Mathematically, it's the ratio of the number of purchasers in the promotion group to the total number of customers in the purchasers group (treatment) minus the ratio of the number of purchasers in the non-promotional group to the total number of customers in the non-promotional group (control).

IRR = Purch<sub>treat</sub>/Cust<sub>treat</sub> - Purch<sub>control</sub>/Cust<sub>control</sub>

  * **Net Incremental Revenue (NIR)**

NIR depicts how much is made (or lost) by sending out the promotion. Mathematically, this is 10 times the total number of purchasers that received the promotion minus 0.15 times the number of promotions sent out, minus 10 times the number of purchasers who were not given the promotion.

NIR = (10 x Purch<sub>treat</sub> - 0.15 x Cust<sub>treat</sub>) - 10 x Purch<sub>control</sub>

**How to Test Strategy**
The metrics are only being compared for the individuals we predict should obtain the promotion.<br/>
See how each variable or combination of variables along with a promotion influences the chance of purchasing. 

## **File Description**<br/>
There is a jupyter notebook file which contains the code, to test the hypothesis, build model & fit and predict. <br/>
There is a test_results python script which is used to evaluate the model from the jupyter notebook above. <br/>
Training & Test data sets (CSV files)

## **Libraries Used**<br/>
Following Python libraries are used 
Numpy <br/>
Pandas <br/>
Scikit Learn <br/>
Scipy <br/>
Imblearn

## **Results** <br/>
Compare the Predicted versus actuals and check for the accuracy to find out if our optimization strategy was successful or not.<br/>
Random Forest model had issues with underfit & hence were unable to fit the model.<br/>
Since the data wasnt balanced, used Easy Ensemble Classifer for this use case which had better Mean ROC AUC statistic as compared to Random Forest Model.<br/>
**Our Model output** <br/>
Your irr with this strategy is 0.0179. Your nir with this strategy is 282.60.<br/>
**Udacity Model output** <br/>
We came up with a model with an irr of 0.0188 and an nir of 189.45 on the test set.

Concluding, Our Model had significantly better NIR but slightly lower IRR.




