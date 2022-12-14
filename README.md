# Football_Transfers2022

This code allows to create a csv or json file with the data about the transactions between football teams during the summer window (from 1-July-2022 to 1-September-22). The transactions have been obtined by scraping on the website Transfermark.com.

## Methodology

For data collection have been used BeautifulSoup library and CSS selectors. These data are stored in a DefaultDict and, later on, converted to csv an json files ready for use.

## How you can use this code ?

An important thing to use this code is to know how indicate the date to get the information. The first way is by indicating a range of date. The second one, is by indicating only the begining day and do the scraping until today. 

> FIRST WAY: Using range of date

> Important things! 
> - If you want to scraping from 2022-07-01 you must indicate one day less 2022-06-30.  
> - You can see 2 functions. If you want to scraping between range of dates you must use the sencond one. Therefore you mustn't delete the comments of the first function.
> You can see an example below:

```
# Start date for scraping. In this case 2022-06-30
players_dict = calculate_days_to_scrap(datetime.strptime('2022-06-30', '%Y-%m-%d'))

# USE THIS FUNCTION IF YOU WANT TO DO A SCRAPING FROM A SPECIFIC DATE TO TODAY
'''def calculate_days_to_scrap(fromDay):
    today = date.today()-timedelta(days=1)
    today = datetime(today.year, today.month, today.day)
    total_days = (today - fromDay).days
    if total_days !=0:
        first_day = today - timedelta(days=(total_days))
        players_dict = check_date(first_day, today)
    return players_dict'''

#  USE THIS FUNCTION IF YOU WANT TO DO A SCRAPING ONLY OF SUMMER MARKET WINDOW
def calculate_days_to_scrap(fromDay):
    last_day = datetime.strptime('2022-09-01', '%Y-%m-%d')
    players_dict = check_date(fromDay, last_day)   
    return players_dict
```

SECOND WAY: From a specific day to today

> - If you want to scraping from 2022-07-01 you must indicate one day less 2022-06-30.  
> - In this case you must to comment the second function and delete the comments of the first one. 
> - If you use this option, the last day to scraping will be today's date in your computer.
> - You can see an example below:

```
# Start date for scraping. In this case 2022-06-30
players_dict = calculate_days_to_scrap(datetime.strptime('2022-06-30', '%Y-%m-%d'))

# USE THIS FUNCTION IF YOU WANT TO DO A SCRAPING FROM A SPECIFIC DATE TO TODAY
def calculate_days_to_scrap(fromDay):
    today = date.today()-timedelta(days=1)
    today = datetime(today.year, today.month, today.day)
    total_days = (today - fromDay).days
    if total_days !=0:
        first_day = today - timedelta(days=(total_days))
        players_dict = check_date(first_day, today)
    return players_dict

#  USE THIS FUNCTION IF YOU WANT TO DO A SCRAPING ONLY OF SUMMER MARKET WINDOW
'''def calculate_days_to_scrap(fromDay):
    last_day = datetime.strptime('2022-09-01', '%Y-%m-%d')
    players_dict = check_date(fromDay, last_day)   
    return players_dict'''
```

## Other things
> You can see this dataset in [Kaggle](https://www.kaggle.com/datasets/davidmolina/football-summer-market-2022). If you create a data analysis of this dataset, encourage to you upload it to kaggle.

Thank you!
