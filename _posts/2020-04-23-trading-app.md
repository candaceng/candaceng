---
title: "CN23 Finance"
date: 2020-04-23
tags: [flask, sql, python, api]
header:
    image: "/images/finance/header.PNG"
excerpt: "A virtual trading web application using real time data"
gallery1: 
    - image_path: /images/finance/register.PNG
    - image_path: /images/finance/login.PNG
gallery2:
    - image_path: /images/finance/get-a-quote.PNG
    - image_path: /images/finance/quote.PNG
gallery3:
    - image_path: /images/finance/buy.PNG
    - image_path: /images/finance/sell.PNG
---
<span style="font-size: 14px;">
    <a href="https://github.com/candaceng/virtual-trading">GitHub Repo</a> &emsp;
    <a href="https://cn23-finance.herokuapp.com/">Web Application</a> &emsp;
</span>

### About
A virtual trading application that uses real time data pulled from the IEX Cloud API. It allows users to register for an account and login and their profiles are stored in a database managed on PostgreSQL.

{% include gallery id="gallery1" %}

Users can enter a stock symbol (e.g. ENB for Enbridge) to get its current market price.
{% include gallery id="gallery2" %}

There is also a feature to buy/sell stocks in live time.
{% include gallery id="gallery3" %}

The homepage displays the stocks a user has on hand along with their unrealized loss/gain. The table outlines the number of shares bought and the current market price. 
<br><br><img class="align-center" src="{{ site.url }}{{ site.baseurl }}/images/finance/stock-profile.PNG" alt="" height="300" width="500">

The history tab lists all their previous transactions made on the account. The table indicates exactly how many shares of what stock was bought or sold. 
<br><br><img class="align-center" src="{{ site.url }}{{ site.baseurl }}/images/finance/transaction-history.PNG" alt="" height="300" width="500">

### How I built it
The dynamic web app was built with Python, using the Flask framework. SQL was used to store the databases of registered users and all stock purchases/sells. HTML, CSS, and Bootstrap were used for the frontend to style the user interface. IEX Cloud was the platform used to gather real time financial data through their API. 

<span style="font-size: 14px;">
    <a href="https://github.com/candaceng/virtual-trading">GitHub Repo</a> &emsp;
    <a href="https://cn23-finance.herokuapp.com/">Web Application</a> &emsp;
</span>