# Introduction

You can choose any of the tasks below


## REST Api Client

Task is to design and create a program that:
* Gets the data from provided by a  REST API.
  For example you can use any of the services below: 
  - https://randomuser.me/api/
  - https://yesno.wtf/api

You should consider: 
* scalability
* documentation
* testing
* handling cases when API doesn't work correctly 


## Financial service

Create a program that exposes endpoint for processing financial data.
* Input is a list of transactions Buy (K) or sell (S).
* The output is a net profit for all the years. 
* The cost of adding a transaction is 0.39% of value of the transaction or 3 PLN when the calculated cost is less than 3 PLN. 
* The transaction cost should be substracted from the total profit.
* When there is more that one buy transaction, when you sell the same instrument you should follow the (FIFO)[https://bossa.pl/edukacja/podatek-gieldowy/metoda-fifo] rule.

### Example input:

```
    [
      {
        "TIME": "18.11.2019 11:58:05",
        "CODE": "A",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": 10,
        "PRICE": 1.415499,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "18.11.2019 11:49:42",
        "CODE": "A",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": "1,500",
        "PRICE": 1.435577,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "07.11.2019 09:01:02",
        "CODE": "B",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": 46,
        "PRICE": 91.94003,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "07.11.2019 09:15:06",
        "CODE": "C",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": 1000,
        "PRICE": 4.10999,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "28.05.2019 16:46:22",
        "CODE": "D",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": 1980,
        "PRICE": 16.9337,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "29.10.2019 16:49:29",
        "CODE": "B",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 46,
        "PRICE": 86.516102,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "04.04.2019 15:57:02",
        "CODE": "C",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 6500,
        "PRICE": 4.075834,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "20.03.2019 09:34:49",
        "CODE": "D",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 1300,
        "PRICE": 15.811425,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "08.03.2019 11:24:24",
        "CODE": "E",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": "1,500",
        "PRICE": 4.293191,
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
        "PRICE": 4.00233,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "03.01.2019 09:53:12",
        "CODE": "E",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 500,
        "PRICE": 4.136068,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "19.12.2018 15:15:21",
        "CODE": "F",
        "MARKET": "WWA-GPW",
        "K/S": "S",
        "VOLUME": 6500,
        "PRICE": 4.91089,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "18.12.2018 15:00:27",
        "CODE": "D",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 680,
        "PRICE": 15.76123,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "28.11.2018 16:36:19",
        "CODE": "F",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 6500,
        "PRICE": 4.768525,
        "CURRENCY": "PLN"
      },
      {
        "TIME": "22.03.2018 12:14:16",
        "CODE": "C",
        "MARKET": "WWA-GPW",
        "K/S": "K",
        "VOLUME": 3300,
        "PRICE": 4.563971,
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
        "PRICE": 50.117269,
        "CURRENCY": "PLN"
      }
    ]

```

### Example output:


```
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
      },
      {
        "year": 2019,
        "code": "E",
        "profit": 45.05
      },
      {
        "year": 2019,
        "code": "E",
        "profit": 387.76
      },
      {
        "year": 2018,
        "code": "F",
        "profit": 680
      }
    ]
```
