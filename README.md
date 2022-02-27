# Welcome to House Rocket Company.
![image](https://github.com/frmoriya/house-rocket-project/blob/main/images/home_image_1920.jpg)

The House Rocket company operates in the real estate market. 
Their business model consists of buying a apartement house at a lowed price of the market average and reselling it with a profit margin.

Disclaimer:
The company house rocket is a fictitious company. However, business problems and the solutions to solve them are based in the real world.

# 1. Business Problem

The company plans to operate in the King County city and the CEO needs anwer two questions:

1) What apartment house should buy and what is a purchase price?
2) When is the best time to sell the property and what price?  


# 2. Undestanding the Business

Classification of construction degree and condition of the building according to King Country, USA:
https://info.kingcounty.gov/assessor/esales/Glossary.aspx?type=r


## Building Condition:

Relative to age and grade. Coded 1-5.

1 = Poor- Worn out. Repair and overhaul needed on painted surfaces, roofing, plumbing, heating and numerous functional inadequacies. Excessive deferred maintenance and abuse, limited value-in-use, approaching abandonment or major reconstruction; reuse or change in occupancy is imminent. Effective age is near the end of the scale regardless of the actual chronological age.

2 = Fair- Badly worn. Much repair needed. Many items need refinishing or overhauling, deferred maintenance obvious, inadequate building utility and systems all shortening the life expectancy and increasing the effective age.

3 = Average- Some evidence of deferred maintenance and normal obsolescence with age in that a few minor repairs are needed, along with some refinishing. All major components still functional and contributing toward an extended life expectancy. Effective age and utility is standard for like properties of its class and usage.

4 = Good- No obvious maintenance required but neither is everything new. Appearance and utility are above the standard and the overall effective age will be lower than the typical property.

5= Very Good- All items well maintained, many having been overhauled and repaired as they have shown signs of wear, increasing the life expectancy and lowering the effective age with little deterioration or obsolescence evident with a high degree of utility.


## Undestanding the real estate market and seasonality

What are the slowest months for real estate?

The number of homes sold usually increase in the spring season. The sales of houses between February and March increase 24%, followed by the busiest months of May, June, July and August. In contrast, the slowest months are November, December, January and February.

To identify the months of seasonality,we calculate the weeks/month.

January = 4 Weeks | February = 5 Weeks | March = 5 Weeks | April = 4 Weeks | May = 4 Weeks | June = 5 Weeks |    
July = 4 Weeks | August = 5 Weeks | September = 4 Weeks | October = 4 Weeks | November = 5 Weeks | December = 4 Weeks


Weeks:

|......... 1 ......... - ...... 8 ..... - ...... 13 .....|... 14 ...-... 22 ...-.. 26 ..|..27.. - .. 35 ... - ... 42 ...|......... 43 ....... - .....48..... - ........ 54 ........|

| December - January - February | March - April - May | June - July - August | September - October - November |

|------------- Winter --------------|------- Spring -------|------ Summer -------|------------------ Fall ----------------|

|------------------- More Cheaper -----------------------|-------------------- More Expensive ------------------------|



# 3. Business Assumptions

To project development we will assume the following premises:

- Delete duplicate id from dataset
- Delete inconsistency data from dataset
- The "price" column will be considered the purchase amount

# 4. Solution Planning

Deliverables:
- Deliver apartment house buy/sell suggestions in a CSV file.
- Identify 3 Business insights
- View apartment house location on city map
- Provide the solution in the cloud

## Phases to development

### Step 01. Data Collect:

- The database is available on the Kaggle website. The Data refers to apartment house for sale in Country King, USA.
- CSV file: "kc_house_data.csv" 

[Dataset from Kaggle] : https://www.kaggle.com/harlfoxem/housesalesprediction/metadata

![kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=Kaggle&logoColor=white)

https://github.com/frmoriya/house-rocket-project/blob/main/jpy_notebook/kc_house_data.csv

### Step 02: Cleaning Data:

- Delete duplicate ID
- Delete inconsistency data

### Step 03: Exploration Data: 
Data analysis for type conversion

### Step 04: Resolution of the Business Question 1:

    - Find the median property price. We will use the median because the variance in property values is high.
    - Comparing house prices with the median price
    - Recommend the purchase of houses with a price below the median price and good condition.
    - Export Suggestion purchase to CSV file

### Setp 05: Resolution of the Business Question 2:

    - Find the median property price
    - Group properties by zipcode and seasonality
    - Find the media price by zipcode and seasonality
    
    Condition to Sell house:

    1) If the purchase price is higher than the median price(by zipcode/seasonality): The sale price = purchase price + 10%
    2) If the purchase price is less than the median price(by zipcode/seasonality): The sale price = purchase price + 30%

### Step 06: Getting the geographic coordinates (lat, Long): 

 Address identification through geographic coordinates and configure the city map

### Step 07: Deploying in the cloud

The solution is available on [<img alt="Heroku" src="https://img.shields.io/badge/heroku-%23430098.svg?style=for-the-badge&logo=heroku&logoColor=white"/>](https://houserocketproject.herokuapp.com/).

# 5. Top 4 Insights

***Hypothesis 01:*** Waterfront houses are 30% more expensive than average?

***True*** The waterfront houses has 276.29% higher than the average.

![image](https://github.com/frmoriya/house-rocket-project/blob/main/images/waterfront.png)

***Hypothesis 02:*** House build before 1955 are 50%  more cheap than average?

**False** The houses build before 1955 is 7.36% cheap than the average.

![image](https://github.com/frmoriya/house-rocket-project/blob/main/images/build1955.png)

***Hypothesis 03:*** Houses without a basement are 50% larger than those with a basement?

**False** Houses without basement are 27.66% bigger than the average.

![image](https://github.com/frmoriya/house-rocket-project/blob/main/images/meanbasement.png)

***Hypothesis 04:***  House prices growthing 10%  YoY ( Year over Year )?

**False** he house price growing 0.70%

![image](https://github.com/frmoriya/house-rocket-project/blob/main/images/YoY.png)

# 8. Business Results

Total apartment house with potential profit : 3827 unit

Purchase = 3827 apartment house

|  Purchase Value  |   Profit Value   |

|  Us 1506345173.0 | Us 431377777.70  | 


| season    | purchase     |     sales     |

|  fall     |  248970872.0 |  316192104.8  |

|  spring   |  462116975.0 |  598954956.9  |

|  summer   |  542279412.0 |  695968150.8  |

|  winter   |  252977914.0 |  326607738.2  |


Recomendation:
- Adquirir imovel proximo ao mar do cep 98070, pois possuem menor valor de compra
- Buy a apartment house located in to zipcode 98070 with waterfront. They have a lower purchase price with initial value Us 285000.0
- Purchase apartment house renovated or built after 1955.

# 9. Conclusions

The "House Rocket" project succeeded in answering two business questions (which house to buy and when to sell), identifying 3827 properties, in good condition, out of a total of 21434 properties.

The purchase of the 3827 apartment house will cost the value of Us 1506345173.0, but with a profit of Us 431377777.70 (after the sale of the properties).

The geographic location of the property is available on a website hosted on heroku. [<img alt="Heroku" src="https://img.shields.io/badge/heroku-%23430098.svg?style=for-the-badge&logo=heroku&logoColor=white"/>](https://houserocketproject.herokuapp.com/)

Demo:
- Purchasde CSV file: https://github.com/frmoriya/house-rocket-project/blob/main/dataset/Report_Suggestion_Buy.csv

- Sale suggestion CSV file: https://github.com/frmoriya/house-rocket-project/blob/main/dataset/Report_Suggesstion_Sell.csv

Exploratory data analysis (EDA) identified the insights below:

    The waterfront houses has 276.29% higher than the average.
    The houses build before 1955 is 7.36% cheap than the average.
    Houses without basement are 27.66% smaller than houses with a basement.
    house prices growing 0.70% YoY( 2014 - 2015 ).
    If sold all houses, the TOTAL PROFIT, is Us 431377777.70 .
    The cheapest zipcode is 98023, and total average values is U$ 89000.00 .
    The most expensive zipcode is 98102, and the highest house is Us 7700000.00 .


# 10. Lessons Learned


# 11. Next Steps to improve
- Address localization improvement
- Improvement the web site with news features

# 12. Author

Francisco Moriya

[<img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>](https://www.linkedin.com/in/francisco-moriya-43560b11/)
