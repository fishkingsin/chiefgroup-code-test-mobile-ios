# iOS Mobile Engineer – Technical Test

# fork the sample repository

[chiefgroup-code-test-mobile-ios](https://github.com/fishkingsin/chiefgroup-code-test-mobile-ios)

## Business Requirement Summary

Looking at the design spec enclosed at the end of this document, you will see a market watchlist
of currency pairings. Your task will be to recreate this screen which will contain some dynamic
elements.
Obtaining the data

There are a few options, there is a publicly accessible API available here
(https://www.freeforexapi.com/Home/Api) however this has been less reliable recently.

Alternatively, you can sign up to a brokerage that offers API access such as Oanda
(https://developer.oanda.com). You should never have to pay any fees for forex pricing data.
Specific requirements:

- Use Swift
- Use VIPER + MVVM
- The app should available on both landscape and portrait mode
- The amount of forex pairs displayed will be determined by the amount available on the API
- Because the API doesn’t provide Sell/Buy prices, you can assume that the price returned from
  the API is the mid-price and create the sell/buy price by adding/removing 1-10 pips randomly
  from that price (the random element would simulate the variable spread that you would see from
  a real broker).
- The prices need to be regularly updated.
- When the prices update, the % change needs to also update, ordinarily this would be
  calculated from the day’s open price, but since the API doesn’t provide that, you can base the %
  change from the first price you receive once you launch the app. The UI should change to
  reflect the increase or decrease.
- Assume the account base currency is in USD:
  - Imagine you go long $10,000 USD worth units on each forex pairing at the first price you
    received.
  - The Equity is calculated by the current value of your total assets, it is also expected to change
    dynamically.
  - The Balance should be $10,000 USD \* Number of forex pairings available (Balance is only
    updated once positions are closed, for this exercise we will consider the positions will always be
    left open).
  - The Margin / Used values on panel can be hardcoded or simply showing a placeholder
    - Include Unit Tests where appropriate How we will judge the test:
      We will evaluate how closely the finished result matches the design. In terms of the code, providing tests, documentation, demonstrating architectural knowledge and error handling, using threading correctly where appropriate and especially correctly leveraging the functional, aspects of the language are all things that would be considered beneficial.

Design specification:

<img src="screen1.png" width="200"/>
<img src="screen2.png" width="200"/>

tips: please also read repository README.md
