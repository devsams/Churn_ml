# Churn_ml
In order to fight churn, Model Fitness has digitized a number of its customer profiles. The task is to analyze them and come up with a customer retention strategy.

### Aim of the study <a class="anchor" id="aim-bullet"></a>
In order to fight churn, Model Fitness has digitized a number of its customer profiles. Your task is to analyze them and come up with a customer retention strategy.

You should:

- Learn to predict the probability of churn (for the upcoming month) for each customer
- Draw up typical user portraits: select the most outstanding groups and describe their main features
- Analyze the factors that impact churn most
- Draw basic conclusions and develop recommendations on how to improve customer service:
    - Identify target groups
    - Suggest measures to cut churn
    - Describe any other patterns you see with respect to interaction with customers

## Table of Contents:

* [Introduction](#intro-bullet)
* [Description of the data](#descrip-bullet)
* [Aim Of the study](#aim-bullet)
* [Libraries used](#lib-bullet)

-----

1.  [Task 1: Prepare the data for analysis](#task1-bullet)

    1. [Task 1.1: Check for missing values and data types.](#task1.1-bullet)
    
    2. [Task 1.2: Add a date and time column and a separate column for dates](#task1.2-bullet)

-----

2. [Task 2: Carry out exploratory data analysis (EDA)](#task2-bullet)

    1. [Task 2.1: Look at the dataset: does it contain any missing features? Study the mean values and standard deviation (use the `describe()` method).](#task2.1-bullet)
    
    2. [Task 2.2: Look at the mean feature values in two groups: for those who left (churn) and for those who stayed (use the `groupby()` method)](#task2.2-bullet)
    
    3. [Task 2.3: Plot bar histograms and feature distributions for those who left (churn) and those who stayed](#task2.3-bullet)
    
    4. [Task 2.3: Build a correlation matrix and display it](#task2.4-bullet)  
    
-----    

3.  [Task 3: Build a model to predict user churn, Build a binary classification model for customers where the target feature is the user's leaving next month.](#task3-bullet)

    1. [Task 3.1: Divide the data into train and validation sets using the `train_test_split()` function.](#task3.1-bullet)
    
    2. [Task 3.2: Train the model on the train set with two methods: logistic regression](#task3.2-bullet)
    
    3. [Task 3.3: Train the model on the train set with two methods: random forest](#task3.3-bullet)
    
    4. [Task 3.4: - Evaluate accuracy, precision, and recall for both models using the validation data. Use them to compare the models. Which model gave better results?](#task3.4-bullet) 
    
    
-----


4. [Task 4: Create user clusters](#task4-bullet)

   1. [Task 4.1:  Standardize the data](#task4.1-bullet)
    
   2. [Task 4.2: Use the `linkage()` function to build a matrix of distances based on the standardized feature matrix and plot a dendrogram.](#task4.2-bullet)
    
   3. [Task 4.3: Train the clustering model with the K-means algorithm and predict customer clusters. (Let the number of clusters be `n=5`, so that it'll be easier to compare your results with those of other students. However, in real life, no one will give you such hints, so you'll have to decide based on the graph from the previous step.)](#task4.3-bullet)
    
   4. [Task 4.4:  Look at the mean feature values for clusters.- Plot distributions of features for the clusters. Do you notice anything?](#task4.4-bullet)
    
   5. [Task 4.5: Calculate the churn rate for each cluster (use the `groupby()` method). Do they differ in terms of churn rate? Which clusters are prone to leaving, and which are loyal?](#task4.5-bullet)
   
-----

5. [Overall conclusion:](#task5-bullet)

------ 


## Introduction <a class="anchor" id="intro-bullet"></a>

One of the most common problems gyms and other services face is customer churn. How do you know if a customer is no longer with you? You can calculate churn based on people who get rid of their accounts or don't renew their contracts. However, sometimes it's not obvious that a client has left: they may walk out on tiptoes.

Churn indicators vary from field to field. If a user buys from an online store rarely but regularly, you can't say they're a runaway. But if for two weeks they haven't opened a channel that's updated daily, that's a reason to worry: your follower might have gotten bored and left you.

For a gym, it makes sense to say a customer has left if they don't come for a month. Of course, it's possible they're in Cancun and will resume their visits when they return, but's that's not a typical case. Usually, if a customer joins, comes a few times, then disappears, they're unlikely to come back.

-----

### Description of the data <a class="anchor" id="descrip-bullet"></a>

**Data used in the second part of the project**


## Instructions for completing the project

### Step 1. Download the data

- `'Churn'` — the fact of churn for the month in question
- Current dataset fields:
    - User data for the preceding month
        - `'gender'`
        - `'Near_Location'` — whether the user lives or works in the neighborhood where the gym is located
        - `'Partner'` — whether the user is an employee of a partner company (the gym has partner companies whose employees get discounts; in those cases the gym stores information on customers' employers)
        - `Promo_friends` — whether the user originally signed up through a "bring a friend" offer (they used a friend's promo code when paying for their first membership)
        - `'Phone'` — whether the user provided their phone number
        - `'Age'`
        - `'Lifetime'` — the time (in months) since the customer first came to the gym
- Data from the log of visits and purchases and data on current membership status
    - `'Contract_period'` — 1 month, 3 months, 6 months, or 1 year
    - `'Month_to_end_contract'` — the months remaining until the contract expires
    - `'Group_visits'` — whether the user takes part in group sessions
    - `'Avg_class_frequency_total'` — average frequency of visits per week over the customer's lifetime
    - `'Avg_class_frequency_current_month'` — average frequency of visits per week over the preceding month
    - `'Avg_additional_charges_total'` — the total amount of money spent on other gym services: cafe, athletic goods, cosmetics, massages, etc.
    
-----
