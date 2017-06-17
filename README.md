# United-Airlines-NYSE-vs-Tweets
(This is a work in progress.)  

The abundance of data generated by Twitter users has attracted the interest of those wishing to predict fluctuations in the stock market.  The basic idea is that certain emotional aspects of the ['Twittersphere'](https://en.oxforddictionaries.com/definition/twittersphere) at any given moment can predict investor activity.  Some success has been achieved already, with researchers correlating certain aspects of the mood of the Twittersphere with Dow Jones Industrial Averages several days later ([see here](https://arxiv.org/pdf/1010.3003.pdf)).  

Personally, I was curious to see if the mood of tweets directed at or referring to a specific company could be used to predict the stock prices of that company.  I chose to do a time-series analysis of United Airlines' (UAL) NYSE quote values vs. the sentiment of tweets discussing United Airlines.  I gathered about 3 weeks worth of tweets about United Airlines using Twitter's Streaming API, as well as minute-by-minute quotes of United stock activity using Google Finance.


First, I gathered tweets using Tweepy and MongoDB (using RoboMongo as a GUI) ([see code](https://github.com/TheresaBrons/United-Airlines-NYSE-vs-Tweets/blob/master/StreamUALTweetsNoOutput.ipynb)).  I also gathered UAL stock prices from Google Finance, which is just one of [several ways](https://www.quantshare.com/sa-426-6-ways-to-download-free-intraday-and-tick-data-for-the-us-stock-market) to do so.  

## Outline:
* ### Cleaning and preparing raw data for analysis and visualization
[This code](https://github.com/TheresaBrons/United-Airlines-NYSE-vs-Tweets/blob/master/CleanUALQuotes.ipynb) formats the .txt file downloaded from Google Finance.  In particular, I wanted to fix the time-stamps, which were given in a strange format.
* ### Visualizations of the raw data using matplotlib and pylab
#### Visualizing the NYSE United Airlines stock prices

Here is the [code](https://github.com/TheresaBrons/United-Airlines-NYSE-vs-Tweets/blob/master/UnitedQuotesVisualization.ipynb).

The graph below graphs the stock prices as they change over time.  The large linear portions are due to 'connecting the dots' during the process of graphing and do not correspond with actual data points.  The vertical red lines indicate market openings.

<img src="https://github.com/TheresaBrons/United-Airlines-NYSE-vs-Tweets/blob/master/UALLineGraph.png" width="700" height="300">


The next graph shows the distribution of the stock prices over the same time period. 
<img src="https://github.com/TheresaBrons/United-Airlines-NYSE-vs-Tweets/blob/master/UAL_QuoteDistribution.png" width="700" height="300">


Because the stock prices were neither normally distributed nor stationary, I took the first difference, i.e. the change in between one quote and the next quote.  The next graph shows how the stock price is changing over time.

<img src="https://github.com/TheresaBrons/United-Airlines-NYSE-vs-Tweets/blob/master/UAL_DifferenceOverTime.png" width="700" height="300">

You can see that the distribution of the changes of the stock prices is much more well-behaved:

<img src="https://github.com/TheresaBrons/United-Airlines-NYSE-vs-Tweets/blob/master/UAL%20DifferenceDistribution.png" width="700" height="300">

#### Visualizing Tweets about United Airlines

Here is the [code](https://github.com/TheresaBrons/United-Airlines-NYSE-vs-Tweets/blob/master/UnitedTweetVisualization.ipynb).




* ### Time-series analysis on the UAL quotes
* ### Times-series analysis on the UAL quotes vs. tweet sentiment averaged over time

 
