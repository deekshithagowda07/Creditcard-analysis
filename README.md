# Credit_Card_Dashboard

# Credit Card Data Visualition and Analysis

This is a simple data visualition analysis on credit card data set based on transactions and customers using Microsoft Power BI and Jupyter Notebooks.


## Supervised by

- Dr. Agughasi Victor Ikechukwu,(Assistant Professor) Department of Computer Science and Engineering [@Victor-Ikechukwu](https://www.github.com/Victor-Ikechukwu)

## Collaborators

- 4MH21CS017 [@deekshithagowda07](https://www.github.com/deekshithagowda07)
- 4MH21CS018 [@deekshitha24](https://www.github.com/deekshitha24)
- 4MH21CS029 [@HVarshitha21](https://www.github.com/HVarshitha21)
- 4MH21CS050 [@mehwish4610](https://www.github.com/mehwish4610)

## Data Analysis using Jupyter Notebook

To view or downoad the notebook click the links below

[downloadNotebook](https://github.com/Mehwish4610/Credit_Card_Dashboard/blob/main/Credit_Card%20(1).ipynb)


## Deployment using Power BI

To deploy :
 
 1. Download Data :
 https://github.com/Mehwish4610/Credit_Card_Dashboard

2. Import data to SQL database: (PostgresSql)
    1. Prepare csv file
    2. Create tables in SQL
    3. import csv file into SQL

3. Creation of coloumns in Power BI :
    
    DAX Queries


    - AgeGroup = SWITCH(
                    TRUE(),
                    'public cust_detail'[customer_age] < 30, "20-30",
                    'public cust_detail'[customer_age] >= 30 &&
                    'public cust_detail'[customer_age] < 40, "30-40",
                    'public cust_detail'[customer_age] >= 40 &&
                    'public cust_detail'[customer_age] < 50, "40-50",
                    'public cust_detail'[customer_age] >= 50 &&
                    'public cust_detail'[customer_age] < 60, "50-60",
                    'public cust_detail'[customer_age] >= 60, "60+",
                    "unknown"
                    )

    - IncomeGroup = SWITCH(
        TRUE(),
        'public cust_detail'[income] < 35000, "Low",
        'public cust_detail'[income] >= 35000 && 'public cust_detail'[income] <70000, "Med",
        'public cust_detail'[income] >= 70000, "High",
        "unknown"
        )

    - week_num2 = WEEKNUM('public cc_detail'[week_start_date])
    
    - Revenue = 'public cc_detail'[annual_fees] + 'public cc_detail'[total_trans_amt] + 'public cc_detail'[interest_earned]

    - Current_week_Reveneue = CALCULATE(
        SUM('public cc_detail'[Revenue]),
        FILTER(
            ALL('public cc_detail'),
            'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])))

    - Previous_week_Reveneue = CALCULATE(
        SUM('public cc_detail'[Revenue]),
        FILTER(
            ALL('public cc_detail'),
            'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])-1))
    '''


## Screenshots

![CustomerReport](https://github.com/Mehwish4610/Credit_Card_Dashboard/blob/main/customerd.png)
![TransactionReport](https://github.com/Mehwish4610/Credit_Card_Dashboard/blob/main/transaction.png)


