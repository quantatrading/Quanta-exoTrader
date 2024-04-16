# About Quanta exoTrader

Given the dynamic nature of the digital currency market, speed and trading accuracy are critical to managing return on investment and capital efficiency. Quanta exoTrader offers a hands-off approach to winning high probability trades across any time frame. With data science at its core, Quanta exoTrader navigates through market volatility, executing high profitability trades with precision whilst being capitally efficient. The algorithm's foundation in advanced analytics means it doesn't just react to the market—it anticipates it, transforming complex data into profitable trading opportunities. Quanta exoTrader is your co-pilot for sustainable investment growth.

Alongside the Quanta exoTrader algorithm on Gunbot, the package also comes with a Trading View Visualisation, Tuning and Backtesting indicator. Settings below apply to both Gunbot and Trading View where applicable.

Quanta exoTrader is licensed for use on the Gunbot crypto trading platform.

# Quanta exoTrader Configuration Settings

This document provides an overview of all the configuration settings available for Quanta exoTrader. Each setting includes a purpose and impact section to help traders understand how to best utilise the options to suit their trading style.

## Basic Strategy Settings

The basic strategy settings section includes parameters that define fundamental aspects of the trading strategy. Traders can customise parameters such as the trade limit, time frame, minimum notional value, and ignore trades before timestamp. These settings allow traders to control the size of their positions, the duration over which market data is analysed, compliance with exchange requirements, and the exclusion of historical trading data, respectively. By adjusting these parameters, traders can tailor the strategy to their specific preferences and market conditions.

- **Trade Limit (`TRADE_LIMIT`) - Default: 0**
  - **Purpose**: Specifies the amount of the base asset to be used on each trade, allowing traders to control the size of their positions.
  - **Impact**: Adjusting the trade limit affects the capital allocation per trade, influencing the potential profit or loss per transaction. Higher limits allow for larger positions but increase risk exposure, while lower limits reduce risk but may limit profit potential.

- **Time Frame (`PERIOD`) - Default: 5**
  - **Purpose**: Determines the time frame for trading operations, defining the duration over which market data is analysed to generate trading signals.
  - **Impact**: Changing the time frame alters the frequency and granularity of trade signals. Shorter periods provide more frequent but more volatile and higher frequency signals, suitable for short-term trading. Longer periods offer fewer but more reliable signals and profits, better suited for longer-term strategies.

- **Min Notional (`MIN_VOLUME_TO_SELL`) - Default: 11**
  - **Purpose**: Sets the minimum notional value required for selling assets on the exchange, ensuring trades meet the exchange's minimum requirements.
  - **Impact**: Adjusting the minimum notional value affects the size of trade orders, ensuring they meet the exchange's requirements for order execution. Higher values may limit the frequency of orders but ensure compliance with exchange rules, while lower values increase trade frequency but risk order rejection.

- **Ignore Trades Before (`IGNORE_TRADES_BEFORE`) - Default: 0**
  - **Purpose**: Specifies the timestamp before which historical trading data should be ignored, ensuring accurate analysis of recent market conditions.
  - **Impact**: Setting the ignore trades before timestamp ensures that historical data beyond a certain point is not considered in trading decisions. This helps prevent outdated information from influencing strategy performance and ensures that trades are based on current market conditions.

## Safety Settings

The safety settings section comprises configurations related to risk management and trade safety. Traders can enable or disable trend protection, safe trade, and full sell-only mode. These settings help traders mitigate risks associated with unfavorable market conditions, ensuring that buy orders are executed only during bullish trends, below break-even prices, or with the option to sell the entire quote balance during downtrends. By utilising these safety features, traders can enhance the resilience of their trading strategy and protect capital from potential losses.

- **Trend Protection (`TREND_PROTECTION`) - Default: false**
  - **Purpose**: Enables or disables trend protection, allowing the algorithm to avoid buying in bearish market conditions.
  - **Impact**: When trend protection is enabled, the algorithm refrains from initiating buy orders if the macro trend (H4) is bearish, reducing the likelihood of entering positions during downtrends. Disabling trend protection may result in buy orders being executed regardless of the prevailing market direction, increasing the risk of losses during downtrends.

- **Safe Trade (`BUY_BELOW_BEP`) - Default: true**
  - **Purpose**: Determines whether buy orders are only executed below the break-even price, helping to ensure purchases occur at favorable prices.
  - **Impact**: Enabling safe trade ensures that buy orders are executed only when the price is below the break-even point, reducing the risk of buying at overvalued prices. Disabling safe trade allows buy orders to be executed regardless of price position relative to the break-even point, potentially leading to purchases at less favorable prices.

- **Full Sell Only (`SELL_ALL_ASSET`) - Default: false**
  - **Purpose**: Enables or disables full sell-only mode, allowing the algorithm to sell the entire quote balance on the next sell signal.
  - **Impact**: When full sell-only mode is enabled, the algorithm sells the entire quote balance on the next sell signal, which can be beneficial during downtrending markets to liquidate positions quickly. Disabling full sell-only mode allows for standard sell orders, providing more flexibility in managing assets during varying market conditions.

## Partial Sell Settings

The partial sell settings section offers parameters for fine-tuning the partial sell functionality of the strategy. Traders can enable partial sell orders below the break-even price and specify the ratio and gain percentage for partial sell orders. These settings allow traders to implement profit-taking strategies by gradually liquidating profitable assets while retaining exposure to potential price increases. By adjusting these parameters, traders can optimise profit-taking strategies based on market conditions and risk tolerance, maximising returns while managing downside risk.

- **Partial Sell (`PARTIAL_SELL_BELOW_BEP`) - Default: false**
  - **Purpose**: Enables or disables partial sell orders below the break-even price, allowing for the gradual liquidation of assets.
  - **Impact**: When partial sell is enabled, the algorithm can conditionally execute sell orders for a portion of the asset balance below the break-even and buy VWAP price, allowing traders to take profits while retaining some exposure to potential price increases. PS Active tooltip provides a live view of the contitions required for partial sells to be active. Disabling partial sell results in standard sell orders only, potentially limiting flexibility in profit-taking strategies.

- **Partial Sell Ratio % (`PARTIAL_SELL_RATIO`) - Default: 90**
  - **Purpose**: Sets the percentage of profitable units to be sold in partial sell orders, controlling the extent of asset liquidation.
  - **Impact**: Adjusting the partial sell ratio determines the proportion of profitable units to be sold when executing partial sell orders, allowing traders to customise profit-taking strategies based on market conditions. Higher ratios result in more aggressive profit-taking, while lower ratios allow for more conservative asset management.

- **Partial Sell Gain % (`PARTIAL_SELL_GAIN`) - Default: 0.5**
  - **Purpose**: Specifies the minimum percentage gain required for executing partial sell orders, ensuring profitability before initiating asset liquidation.
  - **Impact**: Setting the partial sell gain percentage establishes a threshold for profitable asset liquidation, preventing premature sell orders that may result in unrealised gains. Higher thresholds prioritise profitability, while lower thresholds may trigger sell orders more frequently but with reduced profitability potential.

## Order Handling

The order handling section provides configurations for managing order execution and placement. Traders can choose between post-only limit orders and market orders, specify bid and ask positions within the order book, set the order refresh time, and enable or disable order kill functionality. These settings enable traders to control the execution price, order priority, responsiveness to market changes, and the lifecycle of open orders. By customising order handling parameters, traders can optimise order execution efficiency and adapt to dynamic market conditions.

- **Limit Orders (`POST_ONLY_ORDERS`) - Default: false**
  - **Purpose**: Determines whether to use post-only limit orders that will only execute at the limit price, providing control over the execution price.
  - **Impact**: Enabling post-only limit orders ensures that orders are posted at specific price levels, allowing traders to control the execution price and potentially reduce trading costs. Disabling post-only limit orders results in market orders, which may execute at less favorable prices but offer greater speed of execution.

- **Bid Position (Buy) (`BID_ORDER_BOOK_POSITION`) - Default: 2**
  - **Purpose**: Specifies the position of buy orders within the order book, influencing the likelihood of order execution and price impact.
  - **Impact**: Adjusting the bid position determines the priority of buy orders relative to other orders in the order book. Higher positions increase the likelihood of order execution but may also result in higher transaction fees or slippage. Lower positions prioritise price but may experience slower order execution.

- **Ask Position (Sell) (`ASK_ORDER_BOOK_POSITION`) - Default: 2**
  - **Purpose**: Specifies the position of sell orders within the order book, affecting the speed and likelihood of order execution.
  - **Impact**: Setting the ask position determines the priority of sell orders relative to other orders in the order book. Higher positions increase the likelihood of order execution but may also result in higher transaction fees or slippage. Lower positions prioritise price but may experience slower order execution.

- **Order Refresh Time (`ORDER_REFRESH_DELAY`) - Default: 10**
  - **Purpose**: Specifies the duration for which open orders will remain active before being canceled and replaced, ensuring orders remain relevant to current market conditions.
  - **Impact**: Adjusting the order refresh time determines how frequently open orders are updated to reflect changes in market conditions. Shorter refresh times ensure orders are responsive to price movements but may trail price. Longer refresh times reduce price trailing but may result in orders becoming less competitive over time.

- **Kill Open Orders (`ORDER_KILL`) - Default: true**
  - **Purpose**: Determines whether to cancel all open orders after the signal window closes, preventing stale orders from affecting new trading cycles.
  - **Impact**: Enabling order kill ensures that open orders are canceled after the signal window closes, preventing them from being executed at outdated prices. Disabling order kill allows open orders to remain active between signal windows, potentially resulting in orders being executed at less favorable prices when the next signal window opens.

## Algorithm Tuning

The algorithm tuning section consists of advanced parameters for fine-tuning the trading algorithm's technical indicators and signal generation. Traders can adjust parameters such as WT channel length, RSI length, Bollinger length, and various guard settings. These settings allow traders to customise the algorithm's sensitivity to market trends, momentum, volatility, and oversold/overbought conditions. By fine-tuning these parameters, traders can optimise the algorithm's performance and adaptability to different market environments, enhancing the precision and effectiveness of their trading strategy.

- **WT Channel Length (`WT_CH_LENGTH`) - Default: 10**
  - **Purpose**: Adjusts the lookback period for the main wave component of the wave form, affecting how quickly the strategy reacts to price changes.
  - **Impact**: Modifying this length changes the sensitivity of the wave form to recent price movements. Longer periods smooth out fluctuations, potentially missing early signals but reducing false positives. Shorter periods increase responsiveness, capturing more immediate market shifts at the risk of increased noise.

- **WT Average Length (`WT_AVG_LENGTH`) - Default: 21**
  - **Purpose**: Defines the smoothing period for the signal line within the wave form, influencing the clarity and reliability of trade signals.
  - **Impact**: Adjusting this length affects the delay in signal crossovers. Longer averages provide more robust signals at the expense of timeliness, while shorter averages generate more timely but potentially less reliable signals.

- **WT SMA Length (`WT_SMA`) - Default: 3**
  - **Purpose**: Determines the length of the Simple Moving Average applied to the wave form, smoothing out short-term price fluctuations.
  - **Impact**: Shorter SMA lengths increase the oscillator's responsiveness, suitable for capturing short-term trends but potentially leading to more false signals. Longer lengths provide smoother outputs, filtering out noise but potentially causing delayed responses.

- **WT Sell Level (`OB_LEVEL_ONE`) - Default: 53**
  - **Purpose**: Sets the threshold for identifying sell conditions using the wave form, signaling potential sell opportunities.
  - **Impact**: Higher thresholds result in fewer sell signals, ensuring trades occur in more clearly overbought conditions, suitable for avoiding premature exits. Lower thresholds increase sensitivity, potentially capturing earlier sell signals but risking false positives.

- **WT Buy Level (`OS_LEVEL_ONE`) - Default: -53**
  - **Purpose**: Establishes a threshold for detecting buy conditions, indicating potential reversals and buying opportunities.
  - **Impact**: Lower thresholds result in more frequent buy signals, potentially capturing early entry points but risking false positives. Higher thresholds reduce the number of buy signals, ensuring trades occur in more deeply oversold conditions.

- **RSI Length (`RSI_LENGTH`) - Default: 14**
  - **Purpose**: Determines the calculation period for the Relative Strength Index (RSI) bound transformation, affecting its sensitivity to short-term price changes.
  - **Impact**: Longer RSI lengths provide smoother outputs, suitable for identifying longer-term trends but potentially resulting in delayed signals. Shorter lengths increase responsiveness, capturing short-term price movements but potentially leading to more noise.

- **RSI Buy Level (`BUY_RSI_LEVEL`) - Default: 30**
  - **Purpose**: Defines the maximum RSI value required to trigger buy signals, ensuring purchases occur in genuinely oversold conditions.
  - **Impact**: Lower buy levels lead to more frequent buy signals, potentially capturing early market reversals but increasing the risk of false positives. Higher levels provide more conservative entry points, reducing the risk of entering prematurely but potentially missing early opportunities.

- **RSI Sell Level (`SELL_RSI_LEVEL`) - Default: 70**
  - **Purpose**: Specifies the minimum RSI value needed to trigger sell signals, helping traders capitalise on market peaks before potential downturns.
  - **Impact**: Higher sell levels result in fewer sell signals, ensuring exits occur at higher RSI values and potentially maximising profits. Lower levels increase sensitivity, potentially capturing early sell signals but increasing the risk of premature exits.

- **Bollinger Length (`BB_PERIOD`) - Default: 50**
  - **Purpose**: Adjusts the period over which Bollinger Bands are calculated, influencing the indicator's sensitivity to price volatility.
  - **Impact**: Longer periods provide a broader view of price volatility, resulting in fewer but potentially more reliable signals. Shorter periods increase responsiveness, capturing short-term price movements but potentially leading to more false signals.

- **Bollinger Multiplier (`BB_STDEV`) - Default: 1.25**
  - **Purpose**: Sets the standard deviation multiplier for Bollinger Bands, determining the bands' width and sensitivity to price deviations.
  - **Impact**: Increasing the multiplier widens the bands, increasing the sensitivity to price movements but potentially leading to more false signals. Decreasing the multiplier narrows the bands, reducing sensitivity but potentially missing significant price moves.

- **Use RSI on Buy (`USE_RSI_BUY`) - Default: True**
  - **Purpose**: Enables or disables the use of RSI as a guard for buy decisions, allowing traders to adjust the strategy's aggressiveness based on RSI readings.
  - **Impact**: Enabling RSI on buy decisions adds a layer of confirmation to buy signals, potentially reducing the number of trades but increasing their quality. Disabling it may lead to more frequent buy signals but with increased risk.

- **Use RSI on Sell (`USE_RSI_SELL`) - Default: True**
  - **Purpose**: Enables or disables the use of RSI as a guard for sell decisions, allowing traders to adjust the strategy's conservatism based on RSI readings.
  - **Impact**: Enabling RSI on sell decisions adds confirmation to sell signals, potentially reducing the number of trades but increasing their quality. Disabling it may lead to more frequent sell signals but with increased risk.

- **Use Bollinger Bands on Buy (`USE_BBANDS_BUY`) - Default: True**
  - **Purpose**: Determines whether to incorporate Bollinger Bands as a guard into buy decisions, providing additional confirmation for trade entries based on price volatility.
  - **Impact**: Enabling Bollinger Bands on buy decisions adds validation to buy signals, potentially reducing the number of trades but increasing their quality. Disabling it may lead to more frequent buy signals but with increased risk.

- **Use Bollinger Bands on Sell (`USE_BBANDS_SELL`) - Default: True**
  - **Purpose**: Determines whether to incorporate Bollinger Bands as a guard into sell decisions, providing additional confirmation for trade exits based on price volatility.
  - **Impact**: Enabling Bollinger Bands on sell decisions adds validation to sell signals, potentially reducing the number of trades but increasing their quality. Disabling it may lead to more frequent sell signals but with increased risk.

## Various

The various section encompasses miscellaneous settings and options for additional customisation and functionality. Traders can enable or disable buying and selling operations, store balance information for external analysis, enable verbose mode for detailed logging, and control the display of chart shapes in the GUI. These settings provide traders with flexibility and control over various aspects of strategy execution, data analysis, and user interface preferences. By configuring these settings according to their needs and preferences, traders can tailor the strategy to their trading style and optimise their overall trading experience.

- **Buy Enabled (`BUY_ENABLED`) - Default: true**
  - **Purpose**: Allows the trader to enable or disable buying operations.
  - **Impact**: Controls whether the strategy can initiate buy orders, useful for temporarily stopping purchases during unfavorable conditions.

- **Sell Enabled (`SELL_ENABLED`) - Default: true**
  - **Purpose**: Allows the trader to enable or disable selling operations.
  - **Impact**: Controls whether the strategy can initiate sell orders, useful for temporarily stopping sales during unfavorable conditions.

- **Store Balances (`BALANCE_OUTPUT`) - Default: false**
  - **Purpose**: Determines whether to store account balance information on each tick for external analysis if required.
  - **Impact**: Enabling balance output allows traders to access account balances in a seperate json, providing the ability to use external tooling to monitor post-trade analysis.

- **Verbose Mode (`VERBOSE`) - Default: false**
  - **Purpose**: Enables additional logging in the console, helpful for diagnostics or detailed monitoring.
  - **Impact**: Enabling verbose mode provides more detailed information about strategy execution and market conditions, aiding in troubleshooting and performance analysis. Disabling verbose mode reduces console output, potentially improving performance and reducing clutter in the log files.

- **Display Chart Shapes (`DISPLAY_CHART_SHAPES`) - Default: true**
  - **Purpose**: Enables or disables the display of native chart shapes from the GUI.
  - **Impact**: Enabling chart shapes enhances visualisation of trade signals and market data on the GUI, providing a graphical representation of strategy performance. Disabling chart shapes simplifies the GUI interface, potentially improving performance on resource-constrained systems.

