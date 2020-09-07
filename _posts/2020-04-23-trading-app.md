---
title: "Virtual Trading Application"
date: 2020-04-23
tags: [flask, sql, python, api]
excerpt: "Virtual stock trading web app using real time data"
mathjax: "true"
---
<span style="font-size: 14px;">
    <a href="https://github.com/candaceng/virtual-trading">GitHub Repo</a> &emsp;
    <a href="https://cn23-finance.herokuapp.com/">Web Application</a> &emsp;
</span>

### About
A virtual trading web app that uses real time data pulled from the IEX Cloud API. Users can:
- Register for an account 
- Get a stock quote 
- Buy/sell stocks
- View their stock profile  
User profiles are stored in a database managed on PostgreSQL and the web application is hosted on Heroku. 

### How I built it
The dynamic web app was built with Python, using the Flask framework. SQL was used to store the databases of registered users and all stock purchases/sells. HTML, CSS, and Bootstrap were used for the frontend to style the user interface. IEX Cloud was the platform used to gather real time financial data through their API. 