# mcafee-bot

When [@officialmcafee](https://twitter.com/officialmcafee) posts his coin of the day, buy it ASAP.

# How it works

* Read @officialmcafee's tweets in real time.
* Determine whether the tweet is a coin of the day announcement.
* If so, determine what coin it is.
* If it's on bittrex, buy it.

## IT DOES NOT SELL!

That is left as an exercise for you.

# Installation

## Prerequisites

Before you even try to install this, you need to have the following things installed:

* [git](https://git-scm.com/)
* [node.js](https://nodejs.org/en/)
* [yarn](https://yarnpkg.com/en/)
* libtesseract-dev (NEW)

```sh
# OSX
brew install tesseract --with-all-languages

# Linux (Ubuntu)
apt-get install libtesseract-dev tesseract-ocr
```

I don't know what to tell you Windows people.  Perhaps consider running [Ubuntu under VirtualBox](https://www.lifewire.com/run-ubuntu-within-windows-virtualbox-2202098).

## Cloning

```sh
git clone git@github.com:DimensionSoftware/mcafee-bot.git
cd mcafee-bot
yarn
```

## API Keys

You have to go to both twitter and bittrex to get your own API keys.
Once acquired, I recommend putting them in `secrets.env`.

* Twitter:  https://apps.twitter.com/
  * Create an application.
  * You can leave callback URL blank.
  * After that's done go to **Keys and Access Tokens** and make some access tokens.
* Bittrex:  https://bittrex.com/Manage#sectionApi
  * **Read Info** should be **ON**.
  * **Trade Limit** should be **ON**.
  * **Trade Market** doesn't matter.
  * **Withdraw** should be **OFF** for your safety.
* Binance:  https://www.binance.com/userCenter/createApi.html (Coming Soon)
  * **Read Info** should be **ON**
  * **Enable Trading** should be **ON**
  * **Enable Withdrawals** should be **OFF**

# Usage

```sh
source secrets.env  # You have to get your own API keys from twitter and bittrex!
bin/repl
```

This will drop you into a node.js repl with an instantiated bot you can command interactively.

```javascript
// The bot.
bot

// How much BTC are you willing to spend per purchase?
bot.btcSpend = 0.25

// To get ahead of the pump, 
// what multiplier do you want to add to the current price when putting in the buy order?
// bid == price + (price * bot.adjustment)
bot.adjustment = 0.20

// If you want to see it read tweets:
bot.verbose = true

// If you want it to shut up (which is the default):
bot.verbose = false

// Make the bot connect to twitter and monitor tweets.  VERY IMPORTANT!
bot.init()
```

It is now waiting for @officialmcafee to tweet his coin of the day.

# Tweets

* https://twitter.com/officialmcafee/status/947845669213147136
* https://twitter.com/officialmcafee/status/945655402276024320
* https://twitter.com/officialmcafee/status/945293044252905472
* https://twitter.com/officialmcafee/status/944929837671690241
* https://twitter.com/officialmcafee/status/944555048880746497
* https://twitter.com/officialmcafee/status/944206175100424193
