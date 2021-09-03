# lstm-sp500-1
Using a simple long short-term memory neural network, I aimed to correctly classify profitable buy-sell signals for Apple's stock 5 days into the future with an accuracy of more than 50%. My initial hypothesis was an accuracy within the following range: [0.46, 0.52]

The neural network was trained on the daily stock price data (high, low, open, adj. close, volume) of the component stocks of the S&P 500 (excluding Apple), with pricing data ranging from 2004 to 2021.

Outcome: a test accuracy of 0.5558510422706604; better than I expected, but still not very good.
