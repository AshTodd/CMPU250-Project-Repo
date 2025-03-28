# CMPU250 Project Repo
 Domestic violence reporting and analysis by Ash Todd, Nora Phelan, Eaint May and Zack Taylor.

## Table of Contents
* [Exploratory Data Analysis & Data Preparation Q/A](#Exploratory-Data-Analysis-&-Data-Preparation-Q/A)
  - [Exploring the Data](#Exploring-the-Data)
  - [Data Preparation and Cleaning](#Data-Preparation-and-Cleaning)
* [Codebook](#CodeBook)
  - [Used Variables Table](#Used-Variables)
  - [Created Variables Table](#Created-Variables)
 
## Exploratory Data Analysis & Data Preparation Q/A

### Exploring the Data:

#### What is your outcome variable(s)? How well does it measure the outcome you are interested in? How does it relate to your expectations?

The outcome variable in our model is the Precinct Code. We aim to build a predictive model that forecasts the Precinct Code of a case, as part of an effort to model predictive policing. The Precinct Code effectively captures the geographic location of an incident, a key aspect of understanding patterns in crime and law enforcement activities. 

#### What are your key explanatory variables?

Key explanatory variables are the Suspect Sex, Suspect Race, Suspect Age, Offense Type, and the number of reports reported in the precinct. 

### Data Preparation and Cleaning:

#### What data cleaning did you have to do?

We changed all NaNs in the Poverty, Median Income, and Unemployment columns into 0 as they are categorical variables with missing values. We decided to do this because the existing data in the columns are all 1. In the Intimate Relationship Flag, the entries are either ‘MISSING’, ‘Yes’, ‘YES’, ‘No’, or ‘NO’. We changed all entries to title case and created a new dataframe with just the ‘Yes’ entries to the Intimate Relationship Flag to focus specifically on IPV. We also dropped a row where the Suspect Reported Age is 1017, ruling it as a human input error. The Suspect Reported Age and Victim Reported Age also had some NaN values. We filled the NaNs with the average reported age of both variables.

#### How did you prepare the data?

To create a model, we had to take care of non-categorical columns. We made Victim Sex and Suspect Sex into dummy variables with 0=Male and 1=Female. There were also ‘UNKNWN’ values in the Suspect Sex column, which we decided to drop. We also decided to make a new column Felony Offense with the Offense Type column as a dummy variable with Felony Assault and Rape = 1 and DIR = 0. 

#### Are you deciding to exclude any observations? If so, why?

We decided to exclude observations that are not IPV as we decided to focus on IPV so that the model can be trained on a more homogenous dataset, specifically tailored to understanding patterns within intimate partner relationships. This can hopefully lead to more accurate predictions and a deeper understanding of the factors contributing to IPV.

#### Did you have to create any new variables from existing variables? If so, how and why?

We made dummy variables using Victim Sex, Suspect Sex, and Felony Offense with the goal to build models with these variables.

## CodeBook

### Used Variables

| Variable | Description |
| --- | --- |
| Suspect Race | Race of the suspect in an IPV report |
| Victim Race | Race of the victim in an IPV report |
| Suspect Age | Age of the suspect in an IPV report |
| Victim Age | Age of the victim in an IPV report |
| Precinct Code | Precinct in which the IPV report took place |

### Created Variables

| Variable | Description |
| --- | --- |
| Suspect-Victim Age Gap | Difference between the age of the suspect and the victim in an IPV report (Positive val indicates the suspect is older, negative val indicates the victim is older) |
| Felony Offense | Binary indicating whether a felony offense was described in an IPV report (1 indicates felony) |
