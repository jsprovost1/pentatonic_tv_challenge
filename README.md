# Pentatonic Television: Predicting Future TV Buyers

## Outline
1. Data Exploration<br/>
    
   &nbsp;&nbsp;&nbsp;&nbsp;1.1 The Data
    
   &nbsp;&nbsp;&nbsp;&nbsp;1.2 Data Description & Preprocessing<br/>

2. Data Visualization<br/>
   
   &nbsp;&nbsp;&nbsp;&nbsp;2.1 Distribution & Boxplots Plots
     
   &nbsp;&nbsp;&nbsp;&nbsp;2.2 Analysis For The Different Features
   
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2.2.1 Professions<br/>
         
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2.2.2 Cities<br/>
         
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2.2.3 Age Group<br/>
         
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2.2.4 Home Income<br/>
      
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2.2.5 Mixed Features<br/>       

3. Creating Train/Test Sets<br/>

4. Extracting Feature Profiles From PCA Analysis<br/>


## Introduction

A fictional electronic company called Pentatonic specialized into selling high-end televisions. They also hold a wide variety of home entertainment products to complement the purchase of a television.

In the current market, Pentatonic is striving and just purchased a smaller company, Meridian, which used to have an important part of the market despite its size. Since the merger occurred, Pentatonic is looking to target their new clients form Meridian with a marketing campaign highlighting their new state-of-the-art television. As the lead data scientist for Pentatonic, we have access to the data of thousand of customers.

The goal of the project is to determine which customers should we target with our new marketing campaign in order the increase the sales.

## Exploratory Data Analysis
The data set contained some missing values and erronous entries that were talen care of during the preprocessing phase. Furthermore, features like "Education", "City", and "Job_title" were initially encoded using numerical values. We made sure to replace those numerical values by the proper level for each variable.

Distribution plots revealed a potential bimodal distribution for the age, which was further explored later on. Indeed, the data suggested that a small group of clients who did not purchase a television drove that peak around 28 years old.

![dist_plot_age](https://user-images.githubusercontent.com/24415049/139962243-dc2a8f8c-df73-4c2e-9e4e-f94be5bfd4a7.png)
![dist_plot_age_target](https://user-images.githubusercontent.com/24415049/139962427-0e966362-1ded-4fa8-8b70-d0158367b484.png)

We have a highly imbalanced data set with respect to our target feature capturing whether a client has purchased a television or not.

![target_feature](https://user-images.githubusercontent.com/24415049/139962785-60c875b3-d796-45a8-8013-c7918e07e131.png)

Furthermore, no professions, or cities had an over/under-representation with respect to the target feature as the following figures highlight.

![professions](https://user-images.githubusercontent.com/24415049/139963143-6e45ad58-e4f1-4e31-aed0-ebe43739ac12.png) ![cities](https://user-images.githubusercontent.com/24415049/139963148-e5e885b5-32a5-4bb7-9bea-a005fafaf6e7.png)

We found a slight trend highlighting a greater percentage of retirees purchasing a new television; however this difference was not statistically confirmed.

![table_professions](https://user-images.githubusercontent.com/24415049/139963498-b48d3eca-7595-445d-b767-3553496f4b1b.png)


After performing a Principal Component Analysis, the result showed two main components supporting two different groups of clients.
A first group of clients showed:<br/>
    - High Household Income<br/>
    - High Income<br/>
    - High Transactional Volume<br/>
    - Low Financing Volume<br/>
    - Low Credit Card Volume.<br/>
    
A second group of clients reported:<br/>
    - High Income<br/>
    - High Financing Volume<br/>
    - Low Household Income<br/>
    - Low Credit Card Volume.<br/>
    
## Modeling
The goal was to predict which clients would purchase a new television in the future, so we could setup a marketing campaign to target the clients who were undecided.
Three models were built and trained using: Logistic Regression, Random Forest, and Gradient Boosting. All three models were evaluated on recall minimizing the proportion of false positives. Then, the best model was fine tuned using gridsearch in order to maximize the choice of hyperparameters. 
The Gradient Boosting model had the best recall with only 26% of false positives reported.


The main goal of our approach was to identify which clients should be targeted by the new marketing campaign to maximize the conversion. Based on the probability of purchasing a television, the test clients were ranked based on accuracy. Three groups of clients were determined: clients for which we are fairly confident that they will purchase a television, clients for which we are fairly confident that thet will not purchase a new television, and clients that are just above and below the decision boundary.


<img width="311" alt="decision_boundary" src="https://user-images.githubusercontent.com/24415049/140001414-dcba46cc-f49f-4acb-8399-5cc4c165769e.png">
