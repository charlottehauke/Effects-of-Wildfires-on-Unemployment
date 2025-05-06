## Contributors:
- Charlotte Hauke
- Sierra Reshke
- Quinn Turner

# Effects of Wildfires on Unemployment

## Introduction
In several studies, it has been shown that wildfires have a significant impact on local economies and various socioeconomic factors. We hypothesized that larger fires would have a negative impact on unemployment rates in the counties they occurred in, which is supported by previous research. We analyzed this relationship by utilizing several advanced data mining techniques. After experimenting with the inclusion and exclusion of wildfire data in the creation of a model, we concluded that wildfires have a negligible impact on the prediction of unemployment rates on a local level.


## Goal
The goal of our project was to quantify and explore the relationship between wildfires and unemployment rate and explore the interactions between these features in the United States on a county level using data analysis and building predictive models. To do this, we analyzed the data and created various visualizations to improve our understanding of the data, and we built predicitive models. To train our model, we used a data set consisting of fire size, unemployment rate, number of employees, consumer price index, interest rate, and work stoppages as features, which predicted future unemployment rates. Using our data analysis and models, we then explored the impacts of wildfires on unemployment to determine if wildfires had a significant impact on future unemployment rates.

## Methods
Our initial methodology involved collecting datasets on wildfires, unemployment, and climate, then using Python's Pandas library to clean and preprocess the data. After cleaning, we performed an initial analysis and generated various visualizations. We then developed and ran models to predict unemployment, but found that the wildfire data did not significantly impact model performance.

In response, we revised our approach by constructing a more comprehensive unemployment prediction model, incorporating wildfire data to analyze its effect on performance. We also conducted smaller-scale studies to explore potential relationships. We gathered additional datasets related to economic indicators, cleaned and preprocessed this data, and performed exploratory analysis. We categorized the "Fire_Size" feature into five bins, ranging from the largest to the smallest fires, and conducted studies on unemployment in counties that experienced particularly large wildfire incidents. Finally, we ran models focusing solely on the largest fires to predict unemployment.

## Results

Our analysis revealed that while wildfires have significant environmental and socioeconomic impacts, their direct influence on unemployment rates at the county level in the United States is minimal. A linear regression model was employed to predict unemployment rates, incorporating wildfire data (fire size) and economic indicators (e.g., consumer price index and interest rates). The model demonstrated moderate performance in predicting unemployment trends when using prior unemployment rates, economic factors, and fire size data. The model was further improved by performing k-fold cross validation and feature engineering. These findings suggest that wildfires may not have a measurable impact on unemployment rates at the county level due to the various other factors at play driving unemployment rates. However, potential isolated and localized or industry-specific effects remain areas for future exploration.

Graphs highlighting key results are displayed below. Please see UnemploymentModels.ipynb for evidence of the analysis efforts completed and the in-depth model and data exploration performed (analyzing trends in unemployment post-wildfire, feature significance, and model performance comparisons).


### Model Performance

The following graphs illustrate the Mean Squared Error (MSE) and \( R^2 \) scores for various models predicting unemployment rates up to 12 months in advance during feature engineering. Note that the linear regression model performs the best (lowest MSE, highest R^2) in each case.


#### Temporal Dependencies Feature Engineering
![MSE Graph](https://drive.google.com/uc?id=17DR6WNgoMNoA8inuACbVzJFTBTir6sI8)


<br></br>
A linear regression model was chosen as our baseline model to improve upon. The following graphs illustrate the exploration of different values of k when performing k-fold cross-validation. Implementing k-fold cross-validation led to and improved results compared to when no cross-validation was performed. Thus, it was determined that our current Linear Regression model would be updated to perform 5-fold cross-validation to improve prediction accuracy without detriment to runtime complexity.  <br><br>



#### k-Fold Cross-Validation on Linear Regression Model
![K-Fold Cross-Validation](https://drive.google.com/uc?id=1STCTVGOgVrULap2cXpQRqvFTDEtAF-6I)


<br></br>

The final improvement to the Linear Regression model explored was implementing feature engineering and training the model on additional added data. It can be seen in the graphs below that the inclusion of these features resulted in lower MSE and higher R^2 values for each predicted month. Specific features added included Fire_Size_Rate (captures interaction between Fire_Size and Rate to model multiplicative effects; Fire_Size * Rate),  CPI_InterestRate (captures interaction between CPI and Interest_Rate for potential economic insights;  CPI * Interest_Rate), and Unemployment_MoM_Change (month-over-month change in Rate to capture temporal dynamics).<br>
<br>




#### Feature Engineering on Linear Regression Model
![Feature Engineering](https://drive.google.com/uc?id=1mTFx6UyWh4KgTPnsqPhdJi8tShGh0W4F)


<br><br>

## Project File Structure
This project is organized into the following structure\
root/                 
├── Graphs/        &ensp; &ensp; &ensp; &ensp;#Contains final results and model related visualizations\
│\
├── CleaningPreprocessingEDA/      &ensp; &ensp; &ensp; &ensp;#Contains all cleaning and preprocessing code            
│\
├── Visualizations.ipynb     &ensp; &ensp; &ensp; &ensp;#Contanins code and output for EDA graphs\
├── README.md         
└── FinalReport.pdf         &ensp; &ensp; &ensp; &ensp;#Finals written project report

Note: Original and cleaned datasets have not been included due to file sizes

