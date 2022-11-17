<p align="center">
  <img src="https://github.com/ashokkumarvaradarajan/ban5753-fall2022-team-ex-machina-miniproject-2/blob/main/Images/intro.jpg" />
</p>


# **CONTENTS**

[**BACKGROUND**	](#_Toc119524595)

[**DATA DICTIONARY**](#_Toc119524596)

[**DATA ANALYSIS**](#_Toc119524597)

[**Process**](#_Toc119524598)

[**Data Observation**](#_Toc119524599)

[**Exploratory Data Analysis**](#_Toc119524600)

[**Identifying Null Values**](#_Toc119524601)

[**Analyzing Multicollinearity**](#_Toc119524602)

[**Bi-Variate Analysis**](#_Toc119524603)

[**Feature Distribution**](#_Toc119524604)

[**Feature Engineering**](#_Toc119524605)

[**MODELING**](#_Toc119524606)

[**Logistic Regression**](#_Toc119524607)

[**Decision Tree Classifier**](#_Toc119524608)

[**Gradient Boosting Classifier**](#_Toc119524609)

[**Random Forest**](#_Toc119524610)

[**RESULT**](#_Toc119524611)

[**K-MEANS**](#_Toc119524612)

[**RECOMMENDATION**	](#_Toc119524613)


# ![](Images/line.png)
**BACKGROUND**

XYZ bank ran a marketing campaign driven by phone calls, in order to increase the potential clients of term deposits. The campaign ran from May 2008 to November 2010. Data was collected from this campaign to analyze the success of the campaign and to predict, whether the marketed customer will sign up for the for the term deposit or not. Furthermore, exploratory data analysis (EDA), was performed to study the relationships between the data points.

# ![](Images/line.png)
# **DATA DICTIONARY**

|**Variable Name**|**Description**|**Data Type**|
| :-: | :-: | :-: |
|Age |Age of the Customer|Numeric|
|Job|Type of job |Categorical|
|Marital|Marital status |Categorical|
|Education |Education of the customer|Categorical|
|Default|Has credit in default? |Categorical|
|Housing|Has housing loan? |Categorical|
|Loan|Has personal loan? |Categorical|
|Contact|Contact communication type |Categorical|
|Month|Last contact month of year |Categorical|
|Day\_of\_week|Last contact day of the week |Categorical|
|Duration|Last contact duration, in seconds|Numeric |
|Campaign|Number of contacts performed during this campaign and for this client (includes last contact)|Numeric|
|Pdays|Number of days that passed by after the client was last contacted from a previous campaign (999 means client was not previously contacted) |Numeric|
|Previous|Number of contacts performed before this campaign and for this client |Numeric|
|Poutcome|Outcome of the previous marketing campaign |Categorical|
|Emp.var.rate|Employment variation rate - quarterly indicator |Numeric|
|Cons.price.idx|Consumer price index - monthly indicator |Numeric|
|Cons.conf.idx|Consumer confidence index - monthly indicator |Numeric|
|Euribor3m|Euribor 3 month rate - daily indicator |Numeric|
|Nr.employed|Number of employees - quarterly indicator |Numeric|

![](Images/line.png)

# **DATA ANALYSIS**
## **Process**                                                                                                                                       

<p align="center">
  <img src="https://github.com/ashokkumarvaradarajan/ban5753-fall2022-team-ex-machina-miniproject-2/blob/main/Images/steps.png" />
</p>

## **Data Observation**

1. Number of variables: 20
    - Categorical Variables: 10
    - Numeric Variables: 10
2. Campaign Duration: 2.5 Years (May 2008- Nov 2010)
3. Number of Rows: 41,000 approximately

![](Images/data_description.png)


## **Exploratory Data Analysis**

### **Identifying Null Values**
No null values were found in the dataset.

![](Images/null_values.png)

### **Analyzing Multicollinearity**

![](Images/corr_1.png)

emp.var.rate, euribor3m, nr.employed had high multicollinearity. After observing the collinearity of aforementioned variables with others, emp.var.rate, euribor3m were dropped. Below if the collinearity matrix after dropping these variables.

![](Images/corr_2.png)

Dropping emp.var.rate, euribor3m successfully handled high mullticollinearity in the dataset.

### **Bi-Variate Analysis**
![](Images/bi_var_1.png)![](Images/bi_var_2.png)![](Images/bi_var_3.png)

The above graphs shows the relationship between x-variables with y-variable. These graphs were useful to study the trend between x and y variable and how they are related.
### **Feature Distribution**

![](Images/hist.png)

It can be observed from the above graphs that high percentage of the data is highly skewed. This problem was addressed in the modeling process.

### **Feature Engineering**

- The categorical variables were one-hot encoded, to be used in the model.
- Vector Assembler was then used to generate features to be used in the model.
- Features were then scaled using standard scaling as it enhances the performance of machine learning algorithms such as logistic regression, gradient boosting, random forest etc.
- ![](Images/br.png) Weighted column was created in order to provide equal importance to each row when modeling.

# **MODELING**
Four models were developed for the dataset and their AUC was compared for model selection.

|**Model**|**AUC Score**|
| :-: | :-: |
|Logistic Regression|0.9420|
|Decision Tree Classifier|0.8450|
|Gradient Boosting Classifier|0.9202|
|Random Forest|0.9446|

Analyzing all the AUC score, random forest is selected as the final model. Another reason of selecting random forest is that no variable transformation was required. Any linear model like logistic regression would require variable transformation as the dataset is highly skewed and thus results are unreliable. On the other hand, random forest being a non-linear model, can handle skewed datasets as well as outliers.

# **RESULT**

Random forest is selected as final model with high AUC score of 0.9446.

<p align="center">
  <img src="https://github.com/ashokkumarvaradarajan/ban5753-fall2022-team-ex-machina-miniproject-2/blob/main/Images/auc.png" />
</p>


# **K-MEANS**

# **RECOMMENDATION**

1. ## **Stay In Touch**

    - The bank's marketing team needs to build a pipeline in order to be in constant touch with the potential customers.
    - Marketing campaigns can be build incorporating newsletters, emails etc. to always stay in customers mind.
    - Various schemes and offers can keep the existing customers loyal and lure potential customers to invest in the schemes.

2. ## **Build Trust**

    - Appreciating the loyalty of customers and making them bank's brand ambassador is the easiest way to build trust amongst the potential customer.
    - Incorporating non-private detail such as a customer's growth rate within the company, the journey of them benefitting from the bank's schemes and resources will not only build trust amongst the existing customers but will also lay a strong reliable foundation amongst the potential customers.
    - These details can be incorporated in newsletters, Ad campaigns etc. to expand the reach.

3. ## **Targeted Campaigns**

