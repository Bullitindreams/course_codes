# 第十八课: 简单的做市高频网格策略

## 策略原理

在当前盘口上分别挂买卖单，等待成交。 如果多头成交，就把之前的空头单子撤销，然后在成交价上方挂一个网格的价差止盈， 同时挂一个网格价差买入。
如果价格继续向下，那么就会成交多头的单子，同样在均价上方挂止一个网格价差止盈位，在下方继续挂买单。
如果成功止盈，就重新开始。如果多头或单子单边成交达到5个，就会在最后一个成交价下方设置一个止损点位(或者在均价下下方设置止损)。
如果发生止损后，策略就会暂停15分钟。


该策略跟网格策略一样，在震荡行情下会比较有效，但是如果发生单边趋势，或者波动比较大的时候，会容易发生止损。
适合低波动的币种。盈亏比不高，但是胜率会很高。我们下节课会把它修改成类似现货的止盈止损的网格策略。