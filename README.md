# Ranging-Markets-Identification

This work-in-progress repository will contain different materials about ranging markets. The aim of this repository is to test, analyze and build a ranging market detection tool.


## Dataset

The dataset used is the time series of Ethereum's ETH-Perpetuals prices collected from FTX broker (w/ a timeframe of 15 minutes). We mainly focus on closing prices.


## Process

Explanation of the following file : 
>rangingMarkets.ipynb


Firstly, we choose to load several financial indicators from the python library ta (https://technical-analysis-library-in-python.readthedocs.io/en/latest/ta.html#) :

* Average Directional Movement Index (ADX) = "determines the strength of a trend. The trend can be either up or down".
* Average True Range (ATR) = "measures market volatility by decomposing the entire range of an asset price for that period".
* Relative Strength Index (RSI) = "tracks the speed of price changes to watch for overbought and oversold conditions".
* Simple Moving Average (SMA)
* Bollinger Bands (BB)
* Commodity Channel Index (CCI) = "focuses on normal deviations from an asset's moving average price to spot divergences from normal trend cycles".

More details on https://www.investopedia.com/.


Secondly, we define the conditions on our indicators. Those conditions, if met, reflect ranging markets.

Thirdly, we test our different indicators on ETH-PERP and plot the results. On the plots :

* the BLUE segments represent the RANGING markets
* the RED segments represent the TREND markets

By observing historical prices on the first 4 plots, we can see that ADX, ATR and RSI give acceptable results. Nevertheless, there is a significant number of wrong detections, where blue lines appear even though the market would not seem to be going sideways to the naked eye.

Finally, the more constrainsts we add, the less ranging markets we identify (see last plot); the detection seems to get more accurate.
