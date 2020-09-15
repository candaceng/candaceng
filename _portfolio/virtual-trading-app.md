---
title: "CN23 Finance"
date: 2020-04-23
tags: [flask, sql, python, api]
header:
    image: "/images/finance/header.png"
    teaser: "/images/finance/teaser.png"
excerpt: "A virtual trading web application using real time data pulled from an API"
---
<span style="font-size: 14px;">
    <a href="https://github.com/candaceng/virtual-trading">GitHub Repo</a> &emsp;
    <a href="https://cn23-finance.herokuapp.com/">Web Application</a> &emsp;
</span>

### About
A virtual trading application that uses real time data pulled from the IEX Cloud API. It allows users to register for an account and login and their profiles are stored in a database managed on PostgreSQL.
<figure class="half">
    <a class="image-popup" href="/images/finance/register.PNG" title="Registering for an account">
        <img src="/images/finance/register.PNG">
    </a>
    <a class="image-popup" href="/images/finance/login.PNG" title="Login screen">
        <img src="/images/finance/login.PNG">
    </a>
</figure>

Users can enter a stock symbol (e.g. ENB for Enbridge) to get its current market price.
<figure class="half">
    <a class="image-popup" href="/images/finance/get-a-quote.PNG" title="Querying for a quote">
        <img src="/images/finance/get-a-quote.PNG">
    </a>
    <a class="image-popup" href="/images/finance/quote.PNG" title="Stock quote">
        <img src="/images/finance/quote.PNG">
    </a>
</figure>

There is also a feature to buy/sell stocks in live time.
<figure class="half">
    <a class="image-popup" href="/images/finance/buy.PNG" title="Buy stocks page">
        <img src="/images/finance/buy.PNG">
    </a>
    <a class="image-popup" href="/images/finance/sell.PNG" title="Sell stocks page">
        <img src="/images/finance/sell.PNG">
    </a>
</figure>


The homepage displays the stocks a user has on hand along with their unrealized loss/gain. The table outlines the number of shares bought and the current market price. 
<br><br>
<a class="image-popup" href="/images/finance/stock-profile.PNG" title="User portfolio">
    <img src="/images/finance/stock-profile.PNG" class="align-center" height="300" width="500">
</a>

The history tab lists all their previous transactions made on the account. The table indicates exactly how many shares of what stock was bought or sold. 
<br><br>
<a class="image-popup" href="/images/finance/transaction-history.PNG" title="User transaction history">
    <img src="/images/finance/transaction-history.PNG" class="align-center" height="300" width="500">
</a>

### How I built it
The dynamic web app was built with Python, using the Flask framework. SQL was used to store the databases of registered users and all stock purchases/sells. HTML, CSS, and Bootstrap were used for the frontend to style the user interface. IEX Cloud was the platform used to gather real time financial data through their API. 

<span style="font-size: 14px;">
    <a href="https://github.com/candaceng/virtual-trading">GitHub Repo</a> &emsp;
    <a href="https://cn23-finance.herokuapp.com/">Web Application</a> &emsp;
</span>