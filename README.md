# Forex_Reinforcement_Learning
Implementation of an automated Forex trading system based on reinforcement learning

The project we would like to work on for this course is to implement an automated
trading system for FOREX (Foreign Exchange) using price predictions based on reinforcement
learning algorithms such as Q-learning and/or other machine learning algorithms such as LSTM.
Possible methods of using reinforcement learning for stock prediction have been partially
covered in class, so we believe it would be interesting to see how this plays in the foreign
exchange market.
The dataset we will be using is from the API provided by OANDA, which is one of the
largest foreign exchange platforms today. OANDA’s API provides several functions, and among
one of them is being able to get past price data on select currencies. You are allowed to choose
different time intervals (from 5 seconds to a year) and get the closing, opening, highest, and
lowest price for each of those intervals. One limitation though is that only 500 data points can be
called at once, meaning that if we choose the 1 minute interval we can only get data from the
past 500 minutes, and if choose a 1 day interval, we get the prices from the past 500 days.
Getting more data points from the past is easy, either through searching online or using platforms
such as the MT4, where you can get data from the very beginning of online forex trading.
However, in this project we may limit ourselves from using more than those 500 points.
Instead of training a model or agent on a huge dataset, we might train it on the 500 most recent
points and retrain the model after every 250 candlesticks. We believe that recent data is a better
indicator for near future movement than data from years ago, so we want to test out this method
that only focuses on recent data. If this turns out to not be enough data then we will fall back to
use older pricing data.
The data can easily be transformed into a Pandas DataFrame, which will be easier to
work with than the original dataset. Some modifications have to be made to the dataset, such as
converting the date values from string variables to datetime, dropping unnecessary columns, and
organizing and putting values into numpy arrays.
In the case of reinforcement learning, we are hoping to find a way to get a reward
function that rewards gaining profit greatly, and then give some extra reward depending on the
amount of profit. We want the agent to focus on getting a profit, no matter how small, rather than
to take risks to get large profits as my priority is to make an automated trader that is profitable,
not necessarily one with a high risk high return mentality. We would rather aim for a bot that has
more wins than losses than a bot that loses many but makes a lot on a few occasions.
We are planning on trading USDJPY and/or EURUSD, as these are among the more
commonly traded pairs and also have lower spreads. The oandapy API also allows to open and
close orders as long as you have a key and your account ID, so the ultimate goal is to have the
python script trade by itself without any human interaction.
As seen above, we have come up with some theories on what would create a profitable
trading machine, and we are curious to see what kind of results would they show in comparison
to other possible implementations, such as using all available data instead of only 500 points or
using solely the amount of profit as a reward rather than the fact of whether the trading was
profitable or not. Also there are several sources online that show how training through different
machine learning algorithms can closely predict future prices, but we would like to see trained
machines in live action and see if they are able to achieve anything close to what they seem to
achieve on historic data
