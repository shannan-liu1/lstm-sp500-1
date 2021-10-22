# Introduction, Goals, Outcome
The S&P 500 stock market index was created in 1957, and it's a collection of US equities used to track the performance of the broader American equity market. Today, this index tracks the performance of 505 common stocks issued by 500 of the largest firms in the US by market capitalisation, and the index accounts for roughly 80% of the US equity market in terms of market cap.

The S&P 500 index has changed over time as different public companies have been added to or removed from the index as a result of their growth or decline. Companies have also been removed from the index due to other reasons such as being taken private by private equity firms or because of mergers and acquisitions. For simplicity, the project will only use price data on extant constituents of the S&P 500 and will not consider companies who used to be part of the S&P 500.

The goal of this project is to use a long short-term memory (LSTM) network to generate buy and sell signals for stock that is part of the S&P 500 index. To achieve this, the neural network will be trained on the daily stock price data of the constituents of the S&P500 index from 03/01/2001 to 15/10/2021. In this kernel, the stock that signals will be generated for is Apple.

Outcome: a test accuracy of 0.5573394298553467; better than I expected, but still not very good.

# Conclusion, Future Study, Recommendations
From the results, we see that both data sets scored pretty similarly and that they both produced buy and sell predictions only slightly better than a coin toss. This suggests that the data used to predict the target could be filled with a lot of noise that the LSTM is using to make its predictions. Alternatively, this observation may suggest that more data (larger "sequence_length"s) may be needed for the LSTM to pick up reliable patterns.

In the future, dimension reduction could reduce the amount of noise that the LSTM picks up. To perform dimensionality reduction, I would first run a logistic regression of all the stationary variables in the data set onto the target variable and then pick out the statisitically significant variables to move forward with in training and testing. An alternative approach would be to use the Boruta Algorithm, although I suspect it would take much longer and not function on my computer.

Going in the opposite direction, instead of reducing the number of variable inputs, it may be worthwhile to test the LSTM on the larger data sets that my computer couldn't handle to see if the LSTM picks up on other important patterns.

In addition to altering the number of input variables, it might be worthwhile to alter the prediction period. Perhaps the model would show more definite results if it aimed to predict a stock's price changes 1 period into the future instead of 2 periods into the future (i.e. if periods_ahead = 1, not 2).

Finally, moving forward, it may be worthwhile looking into how this model can be applied toward the volatile markets of Cryptocurrencies.

However, as it stands, the data in this notebook is quite versatile, and we can use this notebook to build out models that generate buy/sell predictions on the price of any single S&P 500 equity based on the movement of the other 504 equities in the S&P 500.
