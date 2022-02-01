# first-algo-trading
This is my first algorithmic trading strategy that I built for the purpose of my quantitative finance class at the University of Alberta.

**Click on the pdf file in the repo to view the project!**


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







































