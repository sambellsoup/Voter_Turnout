# Voter Turnout
Multilinear Regression project to identify trends that increase or decrease voter turnout in countries globally. I am attempting to find specific features in order to predict voter turnout. I will begin by examining voter turnout on a global scale, and then focus on specific countries to predict the voter turnout for that country's next election. 

# EDA
I combined data sets from IDEA and the UN HDR. The dataset from IDEA is comprised of a comprehenive global collection of voter turnout statistics from presidential and parliamentary elections since 1945. This dataset also contains whether or not an election had compulsory voting. 

The dataset taken from the Human Development Reports (HDR) from the United Nations Development Programme. This data is from the years 1990-2017 and covers different topics including education, economic, health, and general population figures. 

My target is the voter turnout figures taken from the IDEA dataset, and my features are taken from the HDR dataset. Some examples of these features are: expected years of schooling, government expenditure on education, gross national income, foreign direct investment, life expectancy at birth, infants lack of immunizations, infant mortality rate, urban population percentage, and youn/old age dependency ratio. 

Voter Turnout can be measured either by voters over registered voters, or voters over the voting age population. Each parameter has its drawbacks. The registration roll for each country is difficult to keep up to date, and the voting age population is based on the most recent census figures. Both voter turnout measurements have similar distributions. They have minor skew 

![Voter Turnout over Registered Voters](link-to-image)

![Voter Turnout over Voting Age Population](link-to-image)

In an effort to decide whether or not to include compulsory voting and the type of election (presidential/parliamentary) in my analysis, I conducted a 2 sample t-test on both features. I rejected the null hypothesis for both due to very low p-value in my results. Compulsory voting 
has an effect on voter turnout, and voter turnout for presidential and parliamentary elections are not the same. 



# Modeling

I wanted to make my model using only the necessary features, so I conducted a variety of feature selection techniques including L1/Lasso, KBest, and recursive feature selection. My residual plot showed a random pattern, indicating that a linear model may be a good fit. 

![Residual Plot for Voters over Voting Age Population](link-to-image)

After all of my feature selection, the best features that were consistently indicated by the majority of the feature selection methods were:
  1. Urban Population (%)
  2. Education Index (mean of years of schooling and expected years of schooling)
  3. Mortality rate of adult men
  4. Mortality rate of infants
  5. Expected years of schooling
  6. Mortality rate of adult women
  7. Life expectancy
  
  Here are some simple scatterplots showing relationships between key features and voter turnout over voting age population.
  
![Voter Age Population Turnout Percentage Compared with Urban Population (%)](link-to-image)
![Voter Age Population Turnout Percentage Compared with Education Index](link-to-image)
![Voter Age Population Turnout Percentage Compared with Morality Rate of Men](link-to-image)
![Voter Age Population Turnout Percentage Compared with Infant Mortality Rate](link-to-image)
![Voter Age Population Turnout Percentage Compared with Expected Years of Schooling](link-to-image)
![Voter Age Population Turnout Percentage Compared with Mortality Rate of Women](link-to-image)
![Voter Age Population Turnout Percentage Compared with Life Expectancy](link-to-image)

Using these parameters, my random forest model had these following scores:
\nMean Absolute Error: 10.924
\nMean Squared Error: 188.585
\nRoot Mean Squared Error: 13.733

Map Visualization: https://voterturnoutmap.herokuapp.com/MapScript

# Next Steps

I will continue trying different parameters for the global scale voter turnout for better results. The root mean squared error is reduced with the inclusion of more features.

I will create more visualizations.

I will create more models for specific countries with the United States as my first priority, I will predict the voter turnout for the election in 2020.



  
