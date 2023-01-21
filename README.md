![LB   Sons_2](https://user-images.githubusercontent.com/109354592/210472331-776fcdfd-617b-4fc3-98a9-8113439ff8b8.png)


# Forecasting Financial Performance of Small Business

## Project Overview
The purpose of this project is to determine the financial viability of a small business. We have an understanding that small businesses go to accounting firms with fears about going under, however, by the time the firm realizes that the company is flat they’ll notify the business that it’s too late. The intent of this project, is to be able to use machine learning for any small business with a simple exchange of data, our main focus will be LB & Sons with a potential to expand the data model to other small business entities. 

Jerry Barron, Vice-President of LB & Sons, has provided a dataset to help determine:

<ins>Questions we would like to answer with our machine learning model
  
1.	<ins>Future financials of the business
2.	<ins>Plateau date, if any, of the business
3.	<ins>Forecasted future of the business

## Website
Please click the link to learn more about **[LB & Sons](https://lbsons.com/)**
  
![LB   Sons_1](https://user-images.githubusercontent.com/109354592/210474611-73d80216-56cf-4942-b1e2-e016d5ea19d7.png)

## Resources
* [LB_Forecast_Cash_1.csv](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/868a1601c7760b9ab84af13c4cfac5e3cb98570e/Resources1/Resources/csv/LB_Forecast_Cash_1.csv)
* [LB_Forecast_Rec_1.csv](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/868a1601c7760b9ab84af13c4cfac5e3cb98570e/Resources1/Resources/csv/LB_Forecast_Rec_1.csv)
* [LB_Sales.csv](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/868a1601c7760b9ab84af13c4cfac5e3cb98570e/Resources1/Resources/csv/LB_Sales.csv)
  
## Google Slides
  
- [Link to Presentation ](https://docs.google.com/presentation/d/12877hyohQi5KKqA3wQwVStfloywcexorWbZkf9SNgG4/edit#slide=id.g1d8956e4783_0_133)

## Technologies Used
  To perform our analysis, we had to determine which machine learning tool we were going to use.  We referenced scikit learn (Choosing the right estimator), which pointed to regression as our best choice.  The dataset was less then 100,000 samples but more then 50 samples.  Based on the cheat sheet below we decided to start with regression and expand to other models to experiment.
  
 ![scikit learn](https://user-images.githubusercontent.com/108476566/213287819-2c7c09da-891a-4d22-9ba2-3ca8e4833882.png)


  
 ## Dependent and Independent Variables
 Machine learning is based on the cross-analysis of dependent and independent variables.  The dependent variable (y) is the output we are wanting to predict and the independent variable(X) is an input that impacts the dependent variable(output).  The goal for the project was to find the independent variable(X) affect the dependent variable(y).
 
 To predict financial stability, we used supervised learning analyzes.  Our focus was on Cash and Receivables.  Cash is an important asset in the company as without substantial Cash it is very difficult to run a business.  The business needs cash to meet payroll demands, materials for current and future jobs, equipment repairs, supplier and operational expenses.  Without Cash, a company can quickly find themselves in large amounts of debt.  Construction companies are known to finance just about everything from payroll, to equipment, to the actual current job.  This is where a construction company can get into trouble.  Financing all your cash needs could make your company bankrupt very quickly.  Although, it is very possible to finance everything, it is not the way LB&Sons functions as a business.  LB&Sons follows the ideas of our grandparents, "If you dont have the money in hand as Cash, probably should not purchase".  Wether that is payroll or any other items.  Cash is King!
 
 ## Linear Regression-Cash
  
 We started out with Linear Regression on both Cash and Receivables.  Receivables fuels and feeds Cash.  Once a job is performed, an invoice is established with the client and a receivable is created.  The receivable is what is owed to the company.  Receivables can be a positive but also a negative, thus the reason we wanted it as part of our analysis.  Receivables are only good if the company can collect them.  This is the real world.  Not something you learn in school.  In the real world, just because you perform a job doesn't mean your going to get paid for that job.  It is very important for a company to forecast receivables and ensure the company is collecting its money owed.  If a company is not able to collect its debts, Cash will decline at a rapid rate and could cause your company to go bankrupt.  Some of the tools used to collect receivables is the use of attornies, collection agencies, lien letters, lien enforcements.  A lien is when a company performs a job on a property that is not public and issues a mechanics lien against the property in order to collect its receivables.  This is very threatening but usually results in payment and sour relationship with the client.
  
 For the development environment we used Jupyter Notebook.  It is a popular choice and is something we have used in class.  It combines code, explanatory notes, and visualizations.  We built the first supervised learning model to predict the target variable using linear regression.  Linear regression plots a straight line on the hyperplane that helps predict the target value.  We wanted to use the hyperplane to inspect the known data points to see the distance between the hyperplane and each data point.  
  
  To use this algorithm, we coded the linear regression model to predict cash based on receivables as the independent variable.  We added the correlation coefficient for the independent variable with the y-intercept to predict the value of the dependent variable(cash).
  
  First we imported our python libraries.
  
  ![Python libraries](https://user-images.githubusercontent.com/108476566/213348415-7a1207b8-02bc-4eb8-b176-dde5b3e1f056.png)

  Second, we imported the dataset.  Using the Pandas pd.read_csv, we loaded the CSV dataset into a dataframe and assign the dataframe as a variable called df using the equal operator.
  
  ![Import dataset](https://user-images.githubusercontent.com/108476566/213348879-6911bd20-98c7-4836-9719-fa40b183c317.png)

  There where no variables to remove.  The data was already transformed into a numerical format in order for the algorithm to read the data.
  
  Next, we used the df.head() function to preview the dataframe.
  
  ![dfhead](https://user-images.githubusercontent.com/108476566/213349326-a0bad6f3-d77f-4d8e-a54d-94cd19f5cbf8.png)

  To inspect the full extent of any missing values, we used the isnull().sum() function.
  
  ![isnull](https://user-images.githubusercontent.com/108476566/213349572-c3fee6ee-4aa0-4e04-87cf-3d7acdb28bc0.png)

   There were no number of missing values.
  
  We used a heatmap to analyze the correlation(corr) between the variable combinations.  Heatmaps are useful for understanding relationships between variables.  The variables are structured as both columns and rows on a matrix, with individual values represented as colors on a heatmap.  There is a correlation between weeks, y(cash) and receivables.  The heat map shows color red intensity or brightness between these variables.  
  
  ![heatmap](https://user-images.githubusercontent.com/108476566/213349838-357fbe0b-920b-496a-936e-ec85b190d24c.png)

  We inspected the shape of the dataset using df.shape.  We have 52 rows and 4 columns.
  
  ![dfshape](https://user-images.githubusercontent.com/108476566/213352396-8af56593-2082-4c59-b38f-be12700cf455.png)

  Next, we set the X and y variables.  The X array contains the independent variables, and the y is the dependent variable that we are wanting to predict (cash). We sub-divided the data into training and test sets using a standard 70/30 split.  We used a random seed number of 10.
  
 ![XY variables](https://user-images.githubusercontent.com/108476566/213352992-cf2e667c-ace9-4076-bda8-fdd13edb81d4.png)
 
  Next we set the algorithm using scikit-learn regression algorithm as a variable.  Then, we used fit to link the training data to the algorithm stored in the variable model.
  
  ![setalgorithm](https://user-images.githubusercontent.com/108476566/213353330-786d165e-886a-49d6-969c-a564ee38b86c.png)

  We found the y-intercept and X coefficients.  
  
  ![coefficients](https://user-images.githubusercontent.com/108476566/213353625-f76f8181-2f29-4e6e-9766-872ddb3d60a8.png)

  Next, we ran the prediction model.  We inputed the previous week receivables and week 53 as input features.  At the time, we were trying to predict week 53.  We ran the model.  The predicted value of cash is $1,255,673.62 with a mean absolute error is $95,863.  This means that on average, the model miscalculated the actual cash amount by approximately $95,863.
  
  ![PredictWeek53](https://user-images.githubusercontent.com/108476566/213354328-994a1a13-0b3f-49da-9b28-5d02d9d036bc.png)

  $95,863 dollars is alot to miscalculate cash, so we looked at other models to see if there was a better correlation. 
  
   ## Linear Regression-Receivables
  
  We ran five machine learning algorithms to compare to the linear regression model to determine the best model to use.
  
![5 models](https://user-images.githubusercontent.com/108476566/213488988-ae523e9e-ed58-410e-bcd1-a7c9096088fd.png)
![Five models cont](https://user-images.githubusercontent.com/108476566/213489652-730e1db8-f90c-4ed6-a362-cb45dd85a4b5.png)

We did a R2 comparison to see which model had the best R2 score.  Linear regression, Lasso, Ridge and SGD where the closest to 1.  In addition, we looked at the mean squared error for comparison.  Linear regression was closest to 1 for R2, it had the lowest mean squared error, and lowest root mean squared error.  We ran the model and below is the actual to predicted receivables.
  
![R2 comparison](https://user-images.githubusercontent.com/108476566/213492150-bec2d056-0ae4-4ada-8b8d-106f8a5a4dbc.png)
![mean squared error](https://user-images.githubusercontent.com/108476566/213492567-60c94221-924f-48e7-ad90-fed689a1dd56.png)
![Predicted Receivables](https://user-images.githubusercontent.com/108476566/213493707-0027c8ea-619d-4ecc-af47-521066b979c1.png)

  
  We looked at other machine models,  please see our work at Cash Estimate, Cash Forecast Linear Regression, Cash Regression, Decision Tree Classification, Decision Tree for Regression, Linear Regression Beginners Guide and Linear Regression.   Ultimately, we decided on a  time series model called "Facebook Prophet".  See description below under Machine Model.
  
  
* [Linear Regression Beginners Guide.ipynb](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/8647947c069d2f8f686af907b8060808b34e75b8/Resources1/Resources/ipynb/Linear%20Regression%20Beginners%20Guide.ipynb)
* [Linear Regression.ipynb ](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/9bdf2eca32dd13c20cf3a1339dd08bdf7fadde42/Resources1/Resources/ipynb/Linear%20Regression.ipynb)
* [Cash Forecast Linear Regression Best R2 score.ipynb](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/9bdf2eca32dd13c20cf3a1339dd08bdf7fadde42/Resources1/Resources/ipynb/Cash%20Forecast%20Linear%20Regression%20Best%20R2%20score.ipynb)
* [Cash Estimate.ipynb](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/9bdf2eca32dd13c20cf3a1339dd08bdf7fadde42/Resources1/Resources/ipynb/Cash%20Estimate.ipynb)
* [Cash Regression.ipynb](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/79d16eb0d1df2fc81b7b207620bbbffb6aba5031/Resources1/Resources/ipynb/Cash%20Regression.ipynb)
* [Decision Tree Classification.ipynb](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/e817ee27dc31f6ca3e247a381255d286fbce7231/Resources1/Resources/ipynb/Decision%20Tree%20Classification%20LB.ipynb)
* [Decision Tree for Regression.ipynb](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/e817ee27dc31f6ca3e247a381255d286fbce7231/Resources1/Resources/ipynb/Decision%20Tree%20for%20Regression.ipynb)
* [LB Cash Prophet.ipynb](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/0c2a20e9f583adbc435f5e2ca552f18a9953e026/Resources1/Resources/ipynb/LB%20Cash%20Prophet.ipynb)
* [LB Receivables Prophet.ipynb](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/0c2a20e9f583adbc435f5e2ca552f18a9953e026/Resources1/Resources/ipynb/LB%20Receivables%20Prophet.ipynb)
* [Time Series Forecasting.ipynb](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/6ab0fbe081dd492e8f4ef88743f7148cfdb23586/Resources1/Resources/ipynb/Time%20Series%20Forecasting%20In%20Python.ipynb)

## Database
Using the years of data, spanning from 2021-2022, within the CSV files (Cash Flow, Receivables, and Sales) provided by Jerry from LB & Sons, we implimented the files into Tableu. We created four main graphs/tables to depict the Forecasts and recievables of cash for LB & Sons.

We will be breaking down each of the graphs/tables within our [Tableau file](https://github.com/William-Venable/Forecasting-Financial-Performance-of-Small-Buisnesses/blob/main/Financial_Perf_Dashboard/Financial_Performance.twbx) in the points below:
  
  - <ins>Forecast and Receivable
  
    - We have two main bars, Forcasted Receivables and Receivables. The forcasted receivables is the total sum of total forcasted receivables over the past two years within the CSV files, as well as the receivables being the sum of total receivables within the files.
   
 ![Forecast   Receivables](https://user-images.githubusercontent.com/109354592/211960376-82bde994-1007-4457-a8da-3ece2276474e.png)
    
  - <ins>Forcast and Receivable by Week
  
    - This table is just our previous Forecast and Receivable table but broken down by week. Anywhere that there is a null for the dates is a week that LB & Sons did not get any receivables.
    
 ![Forecast   Reveivables by Week](https://user-images.githubusercontent.com/109354592/211960418-e2e86797-f461-48f1-9bfe-47cf006c0d1f.png)

  - <ins>Sales by Week
  
    - This graph is a depiction of the total number of sales within each month over the past two years. We can see that during the Spring (April) going into the Summer (June), LB & Sons received the most amount of sales.
    
 ![Sales by Week](https://user-images.githubusercontent.com/109354592/211960500-91fc3be3-a2a5-4712-9658-7a54a9c8f400.png)

  - <ins>Forecasted Cash and Receivable
  
    - Within the graph, we have two lines, our Forecasted Cash (Blue line) and Actual Receivables (Orange Line). This clearly depicts a breakdown of the total amount of revenue received in 2022.
    
![Forcasted Cash   Receivables](https://user-images.githubusercontent.com/109354592/211960557-b18c7676-829c-4f93-8760-5087550bd7e2.png)

## Machine Learning Model

**Facebook Prophet** - https://facebook.github.io/prophet/

<ins>What is Facebook Prophet?
  
Prophet is a forecasting procedure implemented in R & Python. Prophet is fast & provides automated forecasts that can be tuned by data scientist & analysts.
  
It shows a time series data based on an addictive model where non-linear trends are fit with yearly, weekly, and daily seasionality, plus holiday effects. It works best with time series that have strong seasonal effects and several seasons of historical data. 
  
Prophet is open source software released by Facebook’s Core Data Science team. It is available for download on CRAN and PyPI.

Prophet is: `Accurate and fast`, `Fully automatic`, `Turnable forecast`, & `Available in R or Python`   
  
## LB & Sons Analysis

<ins>Description and Analysis of our data looking over LB& Sons
  
<ins>What are some possible improvements we could make?
- `How can our model be improved on?`
  
  ![LB   Sons](https://user-images.githubusercontent.com/109354592/210474480-6c687ea1-56ba-4134-9e81-bfbeabb5dd42.png)

  


  
