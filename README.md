# FG-ExpenseBot Twitter Application (bot)

This Twitter application monitors financial allocations/expenditures from the publicly available data at [opentreasury.gov.ng](https://opentreasury.gov.ng/) and makes it accessible to the public via the website and Twitter.

## Getting Started

### Setup Local Environment

You will first need to setup your local environment and ensure that all configuration files are correctly configured.

1. Clone the repo.
2. In your terminal, run `npm install`.
3. In your terminal, run `cp .env.example .env`.
4. Get the required keys and tokens from your Twitter app and populate the .env file accordingly. Note, you will need an Account Activity API environment for the webhook.

```
TWITTER_CONSUMER_KEY=
TWITTER_CONSUMER_SECRET=
TWITTER_ACCESS_TOKEN=
TWITTER_ACCESS_TOKEN_SECRET=
TWITTER_WEBHOOK_ENV=
```

### Running Local Environment

To get a local development server up and running there are a few steps to follow. Note: the PORT should be the same as the one in the .env file.

1. In your terminal, run `./node_modules/ngrok/bin/ngrok http <PORT> to start a session for port forwarding.
2. Once the session starts, copy the https url (e.g. https://650f0a2c12f0.ngrok.io) and populate the .env file. Note, you will need to update this value everytime you start a new session as the URL is never the same with every new session.

```
BASE_URL=
```

3. In your terminal, run `npm run dev`.


## Analysing Twitter Content

This is how the bot will analyse Tweets, Twitter users, or their content:

- find Tweets containing tags and mentions of the app's Twitter handle "ExpenseNG" keyword
- find comments to its tweets
- find tweets with techniques outlined in the [Twitter API Docs](https://developer.twitter.com/en/docs/tutorials/consuming-streaming-data)

## Tweets, Retweets and Likes

This is how the bot will engage other Twitter users:

- Tweet messages referenced from opentreasury.gov.ng and/or expenseng.com
- respond with likes and/or Retweets when tagged in Tweets
- respond with likes or Retweets for comments in reply to its Tweets
- add hashtags and mentions of other Twitter users in its tweets, if such users are directly mentioned in original data at opentreasury.gov.ng
- have a maximum like/Tweet/Retweet rate tbd according to Twitter rules for automation
- even when mentioned, users may prevent the app from liking or Retweeting their Tweets with a keyword

## Off-Twitter Matching

Twitter content may be displayed off of Twitter in the following way:

- find comments to its tweets
- comments with specific keywords like `"ExpenseNGShare"` may be featured on [ExpenseNG.com](https://www.expenseng.com/)

## License

MIT License

Copyright (c) 2020, Team Granite HNGi7. All rights reserved.
