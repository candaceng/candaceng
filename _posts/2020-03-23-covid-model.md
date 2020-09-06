---
title: "A Mathematical Model of the Covid-19 Curve"
date: 2020-03-23
tags: [mathematical modelling, tutorial]
excerpt: "A visual guide to flattening the curve"
mathjax: "true"
---
<span style="font-size: 14px;">
    <a href="https://github.com/candaceng/covid-model">GitHub Repo</a> &emsp;
    <a href="https://stupefied-mcnulty-6a906f.netlify.com">Web Application</a> &emsp;
</span>
<body className="container" style="font-size: 18px;">
    <p>
        We hear the phrase "flatten the curve" a lot, but what does that really mean? Inspired by the YouTube channel Numberphile, this article explores a 
        method of modelling the Covid-19 virus. In the video, differential equations are plugged into a free statistical software to visualize and 
        understand what this curve is all about. You can watch the video below or read through the article (or both!).
        <br><br><i>Disclaimer: I am not an epidemiologist; this article is for informational purposes only.</i>
    </p>
    <iframe width="500" height="300"
        src="https://www.youtube.com/embed/k6nLfCbAzgo">
    </iframe>
    <br>
    <p>
        It is common in epidemiology for the SIR model to be used. The acronym represents three variables: 
        <ul>
            <li><b>S</b> = the number of people susceptible to the disease</li>
            <li><b>I</b> = the number of people infected</li>
            <li><b>R</b> = the number of recovered people</li>
        </ul>
        It is important to note that a "recovered" person in this context means that the person is no longer contagious, and deaths do fall under this category.
        You can think of R standing for "removed" instead. From here we define three more variables, each of which represents the initial values of the SIR 
        variables (SStart, IStart, and RStart). We assume that at time = 0, 1% of the population is infected, leaving the remaining 99% susceptible. The number
        of recovered patients would start at 0 for obvious reasons. So we have,   
        <ul>
            <li><b>SStart</b> = 0.99</li>
            <li><b>IStart</b> = 0.01</li>
            <li><b>RStart</b> = 0</li>
            <li>time <b>t</b> as the independent variable</li>
        </ul>
        We then define two adjustable constants that will aid in the derivation of the equations. The first one of which is <b>transm</b>, 
        which represents the transmission rate of the disease. The equation <b>S'(t, S, I, R)</b> denotes the rate of change of S with respect 
        to time which is dependent on the variables t, S, I, and R. A reasonable way to express this rate would be to multiply the transmission rate with the 
        number of susceptible and infected people. The rate would also be negative because the number of susceptible people is expected to decrease as more
        of them become infected. The second constant we introduce is <b> recov</b>, which represents the recovery rate of infected patients.
        Naturally, the rate of change of R with respect to time would be the number of infected people multiplied by the rate of recovery. The last equation,
        the rate of change of I with respect to time, would be the rate at which people are getting infected minus the rate at which people are recovering.
        Summarizing the equations, we have,      
        <ul>
            <li><b>S'(t, S, I, R) </b>= -(transm)(S)(I)</li>
            <li><b>I'(t, S, I, R) </b>= (transm)(S)(I) - (recov)(I)</li>
            <li><b>R'(t, S, I, R) </b>= (recov)(I)</li>
        </ul>
        Solving these three differential equations gives the curves shown below. Just for the purpose of visualization, the transmission rate was arbitrarily
        set to 3.2, the recovery rate was set to 0.23, and time ranged from 0 to 20. Note that the units of these values do not matter as we are only concerned 
        with the shape of the model. t = 20 could represent days, weeks, or years and the same curves would be produced.
        <br><br>
        <img class="center" src="/images/graph-1.png" alt="" height="300" width="500">
        <br><br>
        Notice that the y values range from 0 to 1. This is representative of the percentage of the human population in decimal form. The red curve (percentage of 
        infected individuals) is what we are currently concerned about. It can be seen in the curve that the peak almost hits 0.8, meaning that nearly 80% of 
        the world's population is expected to be infected at once. If the transmission rate were to decrease then the peak of the red curve decreases along with it,
        as illustrated below. 
        <br><br>
        <img class="center" src="/images/graph-2.png" alt="" height="300" width="500">
        <br><br>
        This is what the media means by "flattening the curve"! Here's what we can do collectively to lower the transmission rate:       
        <ul>
            <li>Practicing <b>social distancing</b></li>
            <li>Washing your hands <b>properly</b> (i.e. using soap and water)</li>
            <li><b>Covering your mouth and nose</b> if you cough or sneeze</li>
            <li><b>Avoid</b> touching your face</li>
        </ul>
        I encourage you to learn more about Covid-19 on reliable sites such as the <a href="https://www.who.int/">World Health Organization</a> or the&nbsp;
        <a href="https://www.cdc.gov/">Centers for Disease Control</a>
    </p>
    <h5 class="center">Stay informed and stay healthy!</h5>
</body>