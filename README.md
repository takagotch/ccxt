### ccxt
---
https://github.com/ccxt

https://github.com/ccxt/ccxt/wiki/Manual

```sh
npm install ccxt

pip install ccxt
```

```js
var ccxt = require ('ccxt')
console.log (ccxt.exchanges)
console.log(ccxt.exchanges)

exchnage.methodName ()
exchange.method_name ()

'use strict';
const ccxt = require ('ccxt');
(async function () {
  let kraken = new ccxt.kraken ()
  let bitfinex = new ccxt.bitfinex ({ verbose: true })
  let huobipro = new ccxt.huobipro ()
  let okcoinusd = new ccxt.okcoinusd ({
    apiKey: 'YOUR_PUBLIC_API_KEY',
    secret: 'YOUR_SECRET_PRIVATE_KEY',
  })
  
  const exchangedId = 'binance'
    , exchangeClass = ccxt[exchangeId]
    , exchange = new exchangeClass ({
      'apiKey': 'YOUR_API_KEY',
      'secret': 'YOUR_SECRET',
      'timeout': 30000,
      'enableRateLimit': true,
    })
  
  console.log (kraken.id, await kraken.loadMarkets ())
  console.log (bitfinex.id, await bitfinex.loadMarkets ())
  console.log (huobipro.id, await huobipro.loadMarkets ())
  
  console.log (kraken.id, await kraken.fetchOrderBook (kraken.symbols[0]))
  console.log (bitfinex.id, await bitfinex.fetchTicker ('BTC/USD'))
  console.log (huobipro.id, await huobipro.fetchTrades ('ETH/CNY'))
  
  console.log (okcoinusd.id, await okcoinusd.fetchBalance ())
  
  console.log (okcoinusd.id, await okcoinusd.createMarketSellOrder ('BTC/USD', 1))
  
  console.log (okcoinusd.id, await okcoinusd.createLimitBuyOrder ('BTC/USD', 1, 2500.00))
  
  bitfinex.createLimitSellOrder ('BTC/USD', 1, 10, { 'type': 'trailing-stop' })
})

```

```py
import ccxt
print(ccxt.exchanges)
import ccxt.async_support as ccxt


import ccxt

hitbtc = ccxt.hitbtc({'verbose': True})
bitmex = ccxt.bitmex()
huobipro = ccxt.huobipro()
exmo = ccxt.exmo({
  'apiKey': 'YOUR_PUBLIC_API_KEY',
  'secret': 'YOUR_SECRET_PRIVATE_KEY',
})

exchange_id = 'binance'
exchange_class = getattr(ccxt, exchange_id)
exchange = exchange_class({
  'apiKey': 'YOUR_API_KEY',
  'secret': 'YOUR_SECRET',
  'timeout': 30000,
  'enableRateLimit': True,
})

hitbtc_markets = hitbtc.load_markets()

print(hitbtc.id, hitbtc_markets)
print(bitmex.id, bitmex.load_markets())
print(huobipro.id, huobipro.load_markets())

print(hitbtc.fetch_order_book(hitbtc.symbols[0]))
print(bitmex.fetch_ticker('BTC/USD'))
print(huobipro.fetch_trades('LTC/CNY'))

print(exmo.fetch_balance())

print(exmo.id, exmo.create_market_sell_order('BTC/USD', 1))

print(exmo.id, exmo.create_limit_buy_order('BTC/EUR', 1, 2500.00))

kraken.create_market_buy_order('BTC/USD', 1, {'trading_argeement': 'agree'})
```
