# Twitter Bot

A Node JS Twitter bot that periodically searches for tweets and then like, reply and follow automatically.
It can be used for advertisement, promotions etc. But please use it carefully to avoid spam.

* Bot saves tweets ids already processed to avoid interact with the same ones again.
* Bot randomly selects each time from the list TWEETS_TO_REPLY one tweet to reply.
* Bot automatically adds the original tweet's user handle to the reply, as a mention.
* Bot logs to the console the tweet's id's that were processed each time.

## Configuration

These are the configuration settings you should change accordingly to what you need. Twitter API keys must be entered. You have to create a Twitter app accessing [Twitter Application Management website](https://apps.twitter.com/). From there you can get the four keys to enter in the configuration.

```javascript
// Set Twitter API keys
var TWITTER_CONSUMER_KEY = '';
var TWITTER_CONSUMER_SECRET = '';
var TWITTER_ACCESS_TOKEN = '';
var TWITTER_ACCESS_TOKEN_SECRET = '';

// Database file
var DB_FILE = "bot_db.txt";

// Set interval time. Try to use a not so small interval to avoid Twitter to lock your account.
var INTERVAL = 3*60*60*1000; // 3 hours

// Set Twitter search phrase. You can use hash tags or simples text. Hash tags works better. Separate with OR or AND.
var TWITTER_SEARCH_PHRASE = '#AGoodHashTag OR #AnotherOne OR #MyGreatSearch';

// Set max number of tweets to get on the search results each time
var TWITTER_SEARCH_MAX_RESULTS = 20;

// Set tweets to reply
var TWEETS_TO_REPLY = [
	"Write something to reply.",
	"Bot will randomly pick one of the tweets to send.",
	"Try to be very natural and human like on the replies.",
	"Use the main Twitter handle you want to promote in all options. @MyHandle",
	"Create 5 to 10 replies. The more options the more natural bot will look."
];
```

You can also tweak the Twitter query to better suit your needs. I'm querying for most recent tweets in English. But you can change the result_type and lang.

```javascript
var query = {
    q: TWITTER_SEARCH_PHRASE,
    result_type: "recent",
    lang: 'en',
    count: TWITTER_SEARCH_MAX_RESULTS
}
```

## Installation

You should have [Node](https://nodejs.org/en/) installed on your system.
I'm using the [Twit](https://github.com/ttezel/twit) module for Twitter API access.
But don't worry, you just have to run this command to install all dependencies.

```
npm install
```

## Usage

Just run the following command and bot will start and stay in memory running until you want stop it, by typing CTRL+C.

```
npm start
```

## Contributing

* Create something great, make the code better, add some functionality,
  whatever (this is the hardest part).
* [Fork it](http://help.github.com/forking/)
* Create new branch to make your changes
* Commit all your changes to your branch
* Submit a [pull request](http://help.github.com/pull-requests/)

## Contact

Feel free to get in touch.

* Website: <http://cetorres.com>
* My company (Cacira): <http://cacira.com>
* Twitter: [@cetorres](http://twitter.com/cetorres)
