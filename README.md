# first-algo-trading
This is my first algorithmic trading strategy that I built for the purpose of my quantitative finance class at the University of Alberta.



My trading strategy starts by the simplest investing principle of buying low and selling high. When looking at a stock chart in retrospective it
is easy to say when to buy and when to sell but the truth is that it is impossible to time the market. For that reason, my strategy will
gradually buy the dips and reluctantly sell during the good times.

## Main idea
I looked at the distribution of historic returns of the S&P. A day negative return of 6% is rather rare, compared to days of -2% or -3%. My
strategy will be based on buying those 'big' dips as they happen.

And to sell, my algorithm will sell as the big green days come along. Then I will include many rules to this base strategy to maximize
profits. Such as:
-   What are the cumulative returns over the past x days? Do it for
    various x's. Each x with its column.
-   What influence does the VIX have?

First lets look at the distributions for the daily, weekly, monthly, trimonthly, semiannual and annual returns of the S&P. It is much better
to buy after a 40% drawdown over a certain time than buying a big but insignificant drop in one day.

It is in times of great volatility that our algorithm would start buying and selling.


So depending on how high is the volatility, the algorithm will decide how much risk to take on each trade execution. With machine learning,
you can optimize how great the positions should be depending on volatility. I want my bot to be more aggressive with the buying and less
aggressive with selling during volatility spikes.

But one day returns are too unpredictable to make decisions, for that its better to take a weighted decision with accumulated returns over a
certain time horizon.

By filtering returns using longer time horizons, it should yield a smaller sample of outstanding returns, by filtering out days where on
the first you earn 10% and on the second -8%, for example. And it also has the ability to identify x-day-long trends and capitalize on them.


As we augment the time horizon, the abnormal returns are more scarce and it is more apparent that positive returns come out after negatives.
Therefore the long-time horizon opportunities are the ones in which we should more aggressively buy the dip.

The idea now is to, within the range of the long-term abnormal returns, buy the daily dips. To capitalize on this we will buy the stock when the
sign of the returns reverses.

Let put the abnormal returns on the stock chart. To better visualize the buying moments:


##### Is the standard deviation correct?

The standard deviation used already takes into account all these dips. So it could be considered taking the standard deviation of the future at
that time. But history repeats itself and this standard deviation would be valid right before the 2008 crash as well as right before the
coronavirus crash. Moreover, it shows that these buying/selling opportunities occur in times of high volatility, with measures such as
garch and the VIX index, availably known at the time.

Since the bot only activates in abnormal returns, it will not work in time where the market steadily grows, therefore when we buy, we buy in
bigger quantities and when we sell, sell in smaller quantities to that way capture as much growth as possible.

Here for example, we buy whenever outstanding returns turn reverse their sign.


The strategy will consist in buying when:

-    Cumulative returns reverse signs meaning buying later after the big     drawdown when sign turns negative.
-    And buying when the bull market returns after market crashes. 
-    
The selling rules are to sell a smaller quantity when:

-   We have at least a position of 2, because we want to hold the stock as much as possible during a bull market.
-   And when there is abnormal positive returns for a one-year period and a 6-month period.


### Optimization

Now what are the buying and selling proportions, or in other words: how aggressive to be, at which the Cumulative Returns is maximized?
By testing with different values,

#### 3D charts of parameters vs Cumulative Returns

The white parts are where Cumulative returns = -1. That is, we lose all.

Seems like there is a linear relationship between buying and selling proportions...
The combinations of buying and selling proportions with positive returns are shown below:



### **Walk Forward period** 

To test the strategy, I used the proportions that respect my risk profile,
-   Positive returns
-   Omega greater than 2
-   The lowest risk (annual standard deviation)

That is, a buying proportion of 1.5 and selling of -0.15.


## Results:


### Takeaways

The strategy is certainly very passive. It is a strategy more suitable
for low risk profiles and for long term holders. It is a strategy that
maximizes gains by deciding to buy after a big dip and to gradually sell
to make profits. Because of this long-term hold factor, it is rather
safe.

Needless to say that it also requires these abnormal return periods in
which it activates. The benefits of that are that there is less comission fees, as well as less capital gains tax after selling the positions.

Perhaps it will also work with more volatile stocks
that earn positive returns in the long run.

### Learning
 
In this project I learnt that a good strategy isn't necessarily the most aggressive one. Sometimes buying a few times rather than many yields the
best results. Also that it is important to analyze the results of a strategy carefully to check its validity. The training period and the
testing period are very important too, otherwise it would be cheating to test your strategy on the same period where you derive the tuned
parameters. Overall it has been a great experience to do this Quantitative Trading Project. The experience in itself is worth a lot,
from the small tweaking to the bigger picture planning.

I will definitely pursue more complex quant strategies that include machine learning techniques and a more deep analysis of the underlying asset.







































