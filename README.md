# Introduction

You can choose any of the tasks below. The solution should be available in Github/bitbucket. 


## 1. REST Api Client

Task is to design and create a program that:
* Fetches the data from provided by a  REST API.
  You can use any of the services below: 
  - https://randomuser.me/api/
  - https://yesno.wtf/api

You should consider: 
* scalability
* documentation
* testing
* handling cases when API doesn't work correctly 


## 2. Financial service

Create a program that exposes endpoint for processing financial data.
* Input is a list of transactions Buy (K) or sell (S).
* The output is a net profit for all the years. 
* The cost of adding a transaction is 0.39% of value of the transaction or 3 PLN when the calculated cost is less than 3 PLN. 
* The transaction cost should be substracted from the total profit.
* When there is more that one buy transaction, when you sell the same instrument you should follow the [FIFO](https://bossa.pl/edukacja/podatek-gieldowy/metoda-fifo) rule. Make sure that you understand what it is before your start coding.

### Example input:

```json
    [
      {
        "TIME": "18.11.2019 11:58:05",
        "CODE": "A",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": 10,
        "PRICE": 1.41,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "18.11.2019 11:49:42",
        "CODE": "A",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": "1,500",
        "PRICE": 1.43,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "07.11.2019 09:01:02",
        "CODE": "B",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": 46,
        "PRICE": 91.94,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "07.11.2019 09:15:06",
        "CODE": "C",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": 1000,
        "PRICE": 4.10,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "28.05.2019 16:46:22",
        "CODE": "D",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": 1980,
        "PRICE": 16.93,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "29.10.2019 16:49:29",
        "CODE": "B",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 46,
        "PRICE": 86.51,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "04.04.2019 15:57:02",
        "CODE": "C",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 6500,
        "PRICE": 4.07,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "20.03.2019 09:34:49",
        "CODE": "D",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 1300,
        "PRICE": 15.81,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "08.03.2019 11:24:24",
        "CODE": "E",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": "1,500",
        "PRICE": 4.29,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "05.02.2019 09:54:29",
        "CODE": "E",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": "1,100",
        "PRICE": 4.136068,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "07.01.2019 09:53:12",
        "CODE": "E",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 2100,
        "PRICE": 4.00,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "03.01.2019 09:53:12",
        "CODE": "E",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 500,
        "PRICE": 4.13,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "19.12.2018 15:15:21",
        "CODE": "F",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": 6500,
        "PRICE": 4.91,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "18.12.2018 15:00:27",
        "CODE": "D",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 680,
        "PRICE": 15.76,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "28.11.2018 16:36:19",
        "CODE": "F",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 6500,
        "PRICE": 4.76,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "22.03.2018 12:14:16",
        "CODE": "C",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 3300,
        "PRICE": 4.56,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "02.02.2018 16:06:27",
        "CODE": "C",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 3300,
        "PRICE": 4.467355,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "31.01.2018 12:12:15",
        "CODE": "G",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 530,
        "PRICE": 50.11,
        "CURRENCY": "PLN"
      }
    ]

```

### Example output (results doesn't have to be exact):

```json
    [
      {
        "year": 2019,
        "code": "A",
        "profit": -3.27
      },
      {
        "year": 2019,
        "code": "B",
        "profit": 217.49
      },
      {
        "year": 2019,
        "code": "C",
        "profit": -390.81
      },
      {
        "year": 2019,
        "code": "D",
        "profit": 2003.52
      }
     // ...
    ]
```

You should consider: 
* testing
* simple design
