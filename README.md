# Quanta exoTrader

##Basic Strategy Settings

Trade Limit (TRADE_LIMIT)

Purpose: Specifies the amount of base currency to use for each trade.
Impact: Controls the exposure per trade, affecting potential profit and loss per transaction.
Time Frame (PERIOD)

Purpose: Sets the chart time frame for analysis.
Impact: Influences the frequency of trades and sensitivity to market changes; shorter periods may lead to more trades and higher responsiveness.
Min Notional (MIN_VOLUME_TO_SELL)

Purpose: Establishes the minimum transaction size allowed by the exchange for trading.
Impact: Ensures all trades meet the exchange's minimum requirements, affecting the execution of smaller trades.
Ignore Trades Before (IGNORE_TRADES_BEFORE)

Purpose: Sets a timestamp before which all previous trades are disregarded.
Impact: Prevents the strategy from considering outdated or irrelevant market data, focusing analysis on recent trends.
Safety Settings
Trend Protection (TREND_PROTECTION)

Purpose: Activates a mechanism to halt buy orders during bearish macro trends.
Impact: Reduces the risk of buying in a downtrend, potentially improving the strategy's risk management.
Safe Trade (BUY_BELOW_BEP)

Purpose: Ensures that buy orders are only placed when the price is below the break-even point (BEP).
Impact: Aims to maximize the safety of entry points by avoiding purchases at inflated prices.
Full Sell Only (SELL_ALL_ASSET)

Purpose: Enables the strategy to execute a full sell of the quote balance upon the next sell signal.
Impact: Useful in downtrending markets to prevent holding declining assets, possibly limiting losses.
Partial Sell Settings
Partial Sell Below BEP (PARTIAL_SELL_BELOW_BEP)

Purpose: Allows the algorithm to execute partial sells below the unit cost.
Impact: Enhances flexibility in managing trades, allowing for profit-taking even when prices are below average cost.
Partial Sell Ratio % (PARTIAL_SELL_RATIO)

Purpose: Defines the percentage of profitable units to sell when a partial sell condition is met.
Impact: Balances between realizing profits and maintaining a position for further potential upside.
Partial Sell Gain % (PARTIAL_SELL_GAIN)

Purpose: Sets the minimum percentage gain required to trigger a partial sell.
Impact: Ensures partial sells are profitable, securing a specified minimum gain before execution.
Order Handling
Limit Orders (POST_ONLY_ORDERS)

Purpose: Determines whether to use limit orders that will only execute at the limit price.
Impact: Provides control over the execution price, potentially reducing slippage but may result in missed trades if prices move quickly.
Bid and Ask Position (BID_ORDER_BOOK_POSITION, ASK_ORDER_BOOK_POSITION)

Purpose: Specifies the placement of buy and sell orders within the order book.
Impact: Influences how quickly trades are likely to be executed, with positions closer to the current price potentially filling faster.
Order Refresh Time (ORDER_REFRESH_DELAY)

Purpose: Sets the duration an order will remain active before being canceled if not filled.
Impact: Ensures orders remain relevant to current market conditions and are refreshed regularly.
Kill Open Orders (ORDER_KILL)

Purpose: Cancels all open orders when the trading signal window closes.
Impact: Prevents stale orders from affecting new trading cycles, ensuring that each cycle starts fresh.
