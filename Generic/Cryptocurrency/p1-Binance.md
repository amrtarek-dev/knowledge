

```python
from binance import Client
import pandas as pd

# API_KEY    from Binance account
# API_SECRET from Binance account

# Make Binance client
client = Client(API_KEY, API_SECRET)
# Get account data
client.get_account()
# Datastream by websocket
# ToDo

# Get historical prices
# Type, interval (1 miniute), how much geting back
data = client.get_historical_klines('BTCUSDT', '1m', '30 min ago UTC')
# Could be used in Dataframe
# [
#   [
#    1499040000000,      // Kline open time
#    "0.01634790",       // Open price
#    "0.80000000",       // High price
#    "0.01575800",       // Low price
#    "0.01577100",       // Close price
#    "148976.11427815",  // Volume
#    1499644799999,      // Kline Close time
#    "2434.19055334",    // Quote asset volume
#    308,                // Number of trades
#    "1756.87402397",    // Taker buy base asset volume
#    "28.46694368",      // Taker buy quote asset volume
#    "0"                 // Unused field, ignore.
#   ]
# ]
pd.DataFrame(data)

# Let's make a function for it
def gethistory(symbol, interval, lookback):
    frame = pd.Dataframe(client.get_historical_klines(symbol, internal, lookback))
    # let's just use the first 6 column [open time : Volume]
    #[:,:6]. all rows, and columns until number 6
    frame = frame.iloc[:, :6]
    # let's name the columns
    frame.columns = ['Time', 'Open', 'High', 'Low', 'Close', 'Volume']
    # let's use time columns as index
    frame = frame.set_index('Time')
    # convert the Kline open time from Unix to readable
    frame.index = pd.to_datetime(frame.index, unit='ms')
    # convert the frame values from strings to float
    frame = frame.astype(float)
    return frame

btc = gethistory('BTCUSDT', '1m', '30 min ago UTC')
doge = gethistory('DOGEUSDT', '1m', '30 min ago UTC')
doge.Open.plot()
# So you can analyse the graph and make a desigen to Buy or Sell

## Let's add strategy to Buy and sell
# buy if asset fell by more than 0.2% (from latst reading) (within the last 30 min)
# sell if asset rises by more than 0.15% (to include the fees)
# sell if asset falls by 0.15% (Risk management)

def strategy(symbol, qty, Buyed=False):
    df = gethistory(symbol, '1m', '30 min ago UTC')
    # cumulative return, that take a look how the asset was performing
    # about the last 30 min.
    # the rel
    cumulret = (df.Open.pct_change() +1).cumprod() -1
    if not Buyed:
        # check if the last acumulated return less than 0.2%
        if cumulret[-1] < -0.2/100:
            # Make the buy order
            order = client.create_order(symbol=symbol, side='BUY', type='MARKET', quantity=qty)
            print(order)
            Buyed=True
        else:
            print('No Trafe has been executed')
    else:
	    # get the data history to sell
	    while True:
		    df = gethistory(symbol, '1m', '30 min ago UTC')
		    # to have the data from the moment of Buying
		    sincebuy = df.loc[df.index > pd.to_datetime(order['transactTime'], unit='ms')]
		    # check if it is not the same moment of buying
		    if len(sincebuy) > 0:
				# get the acumulative return from the moment of buying
				sincebuy_cumulret = (sincebuy.Open.pct_change() +1).cumprod() -1
				if sincebuy_cumulret[-1] > 0.15/100 or sincebuy_cumulret[-1] < -0.15/100:
					# sell
					order = client.create_order(symbol=symbol, side='SELL', type='MARKET', quantity=qty)
					print(order)
					Buyed=False
					break
```


# Resources
https://binance-docs.github.io/apidocs/spot/en/#change-log