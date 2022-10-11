![alt text](https://live.staticflickr.com/65535/48431984232_f801bfcef9_b.jpg)

# Global Airport Reccomendation System.

Want to build your own airport? Out of 19,000 airports listed in the U.S, 14,000 are privately owned. Building an airport isn't very complex and expensive compared to what people normally think. Building an airport can also bring positive impacts to the local community by supplying quit various number of jobs. This is because builders, plumbers, electricians will be needed for the building of the airport. In building airports there are several factors that matters. Altitude is one of the most important factor to think carefully when building an airport. Operating at a high altitude airport does require an additional amount of care. In this project, I will be creating a model that can help my clients what type of airport they should build based on the given features.


# 1. Data 
Datahub is a center of data exchange that is supported by data science. It's an open platform that people can freely enter where numerous data sheets are provided for free. A lot of Data scientsts and Data engineers utilize this space to create ideas and make projects. 

• https://datahub.io/core/airport-codes

• https://datahubproject.io/

# 2. Method

Utilizing this datasheet, it was possible to make a decision of choosing the key feature which is altitude(elevation(ft)). The column 'altitude_ft' was very important and helpful for me to understand the relationhsip between flights and density altitude. Due to the abundant external resources, it was possible for me to easily understand how to handle this dataset. 

# 3. Data Wrangling

• NaNs & Duplicated Rows - I plotted the MSNO matrix to see if the values are missing completely at random or not missing at random or just missing at random. The columns that contained null values were elevation_ft, continent, municipality, gps_code, local_code, and the missing values were definitely not missing with certain patterns. There were no Duplicated Rows. 

• Dropping Columns(Curse of Dimensionality) - The following 6 columns that were contained as primary key values. 
1. Name
2. Municipality
3. Gps_code
4. Iata_code
5. Local_code
It is reasonable to drop these columns because it wouldn't help the training for the model since every single value is unique.

• Outliers - There were too many outliers but most of them are within the 95% confidence interval. The one's which are outisde of the interval are 2 data points. One in medium_airport and one in heliport. I took a look on them using external resources and those two values are facts so let's keep it.

• Column merging - The counts for each airports have big gaps. The quantity of small airports has at least 3 times more than heliport, medim_airport, seaplane_base, large_airport, balloonport. I decided to group them up based on their mean elevation_ft. Therefore, I came up with the group seaplane_base as large_airport + seaplane_base and medium_airport as balloonport + medium_airport.

• False Informations - I identified that a lot of values in the states columns weren't states. Some were actually continents and some were country names. Time is gold and I don't want to get stuck here too much which made me drop some values that weren't adequate.


# 4. EDA
• ECDF plot - Can visually see what 

• One way Anova - Used this test to find out if there is a difference in mean between the groups of airports. I was thinking to use two independent values which would lead me to test using two-way ANOVA but it wouldn't be necessary because for now the key feature would be elevation_ft.

• Tukeyhsd - Tukey's HSD is a test I used to make sure how each groups are statistically different from each other.


# 5. Algorithms & Machine Learning
1. Light BGM Classifier
2. Ada Boost Classifier
3. Cat Boost Classifier


# 6. Winner & Evaluation
• 


# 7. Future Improvements  
• All sources of datasets contributed to the predictive power of the model
• Out of 3 supervised classification models, the LGBM  provided the best results.
• Out of 67 features, we used only 31 features for the best model with 12 from the flight data, 16 from the weather data and 3 from the flight historical     performances data (which we engineered).
• Train Set - 80%, Test Set - 10%, Validation Set - 10%
• With more features, the model can be improved in the future.
• Log loss would be a good lose metric to use because it’s robust to imbalance datasets.






