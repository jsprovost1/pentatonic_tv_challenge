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

