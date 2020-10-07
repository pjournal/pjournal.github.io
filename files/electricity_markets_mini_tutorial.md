# Mini Tutorial about Electricity Market Prices

This tutorial is designed to provide only the essentials of electricity markets of Turkey. Check references for more detail.

+ Electricity markets are designed with **"balance"** in mind. Balance means electricity production should be equal to electricity consumption as much as possible at all times. (This is a physical constraint, otherwise system faces brownouts/blackouts.)
+ To preserve balance, markets are developed. These are Day Ahead Market - DAM (Gün Öncesi Piyasası - GÖP), Intraday Market - IDM (Gün İçi Piyasası - GİP) and Balancing Power Market - BPM (Dengeleme Güç Piyasası - DGP).
+ Electricity market (in Turkey) is hourly. Almost all trades happen in [Energy Exchange of Turkey (EXIST / EPIAS)](https://www.epias.com.tr/).

## Day Ahead Market - DAM

+ At each day, at Day Ahead Market, consumers (utilities, retailers, traders etc.) (e.g. CK Boğaziçi Elektrik, Enerjisa AYESAŞ) and producers (e.g. Enerjisa Üretim, Borusan Enbw) put orders (bids and offers) for the next day's hourly electricity plan. They state quantity and price for each hour of the next day. Entering orders is finished at noon.
+ These orders are processed in a clearing mechanism. Clearing mechanism provides next day's consumption/production plan from matching offers and market prices. These prices are called Market Clearing Price - MCP (Piyasa Takas Fiyatı - PTF). Since there are 24 hours in a day, there are 24 MCPs.
+ MCPs are settled in a single session and they do not change.

## Intraday Market - IDM

+ It is not expected to predict next day's hourly consumption perfectly. Therefore, intraday market is introduced.
+ Unlike DAM, there is continuous trading at IDM. It is much like a stock exchange. Prices can change in mere seconds or in higher frequency.
+ It is an opportunity to correct participants forecasts by trading their excess or missing MWhs.
+ Hourly weighted average prices are reported as Weighted Average Price - WAP (Ağırlıklı Ortalama Fiyat - AOF)

## Balancing Power Market - BPM

+ It can be thought as last minute sale/purchase of electricity to balance a participant's account (i.e. electricity bought from market vs consumed electricity). BPM is not a market where participants actively trade electricity, it is just for balancing.
+ Last minute purchase is always more expensive and last minute sale is always cheaper. Therefore, it is not (usually) desirable to be subject to BPM.
+ If there is a system-wide need for extra electricity production (i.e. actual demand > predicted demand), then it is called an Enerji Deficit (Enerji Açığı). If the situation is the opposite (i.e. actual demand < predicted demand), then it is called an Energy Surplus (Enerji Fazlası).
+ Market operator may order some electricity production facilities (i.e. hydro plants, natural gas plants) to increase or decrease production.
+ A single price per hour is reported as a result of balancing. It is called System Marginal Price - SMP (Sistem Marjinal Fiyatı - SMF).
+ SMP is always higher than MCP if system has Energy Deficit, and lower if there is Energy Surplus.
+ Market operator also penalizes the operations in BPM by 3%. This is called Imbalance Price. Negative (Deficit) Imbalance Price is calculated as max(MCP,SMP)*1.03 and Positive Imbalance Price is calculated as min(MCP,SMP)*0.97.

## Example

1. Suppose you are a large industrial company with a considerable consumption (e.g. 50-150 MWh / hour) with some uncertainty in your consumption (production plan changes, last minute orders etc.).
2. For instance let's say you bought 100 MWh for 10:00-10:59 slot for the next day from DAM. Let's say MCP is 100 TL / MWh. You paid 100*100 = 10,000TL for your consumption of the hour.
3. Though as time approaches you revised your forecast to 110 MWh for that hour. Therefore you buy electricity from Intraday Market. Suppose you bought 10 MWh for 110 TL / MWh on average. You paid an additional 1100 TL.
4. Your consumption turned out to be 120 MWh! Suppose SMP is 120 TL / MWh. Since you have an energy deficit, market operator sold you electricity at the Negative Imbalance Price (120*1.03 = 123.6 TL / MWh) for the extra 10 MWh. You paid an additional 1236 TL.
5. Your total bill is 12,336TL. If you could have predicted your consumption perfectly you would pay only 120*100 = 12000TL. Your loss is 336TL (or 336/120 = 2.8TL / MWh) from a single hour.

In real life these losses can be millions in a month.

## References

+ [EXIST Tutorials](https://www.epias.com.tr/en/day-ahead-market/introduction/)
+ [EXIST Video Tutorials](https://www.youtube.com/channel/UCASXs_GvnskJzzYDe0SmnCQ)
