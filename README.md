ParallelDots-JS-client-API
===============================

A js client wrapper for [ParallelDots' APIs](https://www.paralleldots.com/text-analysis-apis).

Installation
------------
Install with [npm](http://npmjs.org/)

```javascript
npm install paralleldots-client
```

API Keys
----------------
Sign up to create your free account from [ParallelDots](https://www.paralleldots.com/sign-up).
[Log in](https://user.apis.paralleldots.com/login) to your account to get your API key.

Supported APIs:
---------------

- [Semantic Similarity](https://tinyurl.com/k23nqs9)
- [Sentiment Analysis](https://tinyurl.com/km99mzb)
- [Taxonomy](https://www.paralleldots.com/text-classification)
- [Named Entity Extraction/Recognition ( NER )](https://tinyurl.com/k9yglwc)
- [Keywords](https://tinyurl.com/kujcu8o)
- [Intent](https://tinyurl.com/n568bqw)
- [Emotion](http://blog.paralleldots.com/technology/deep-learning/emotion-detection-using-machine-learning/)
- [Abuse](https://www.paralleldots.com/text-analysis-apis#abusive)
- [Multilingual Sentiment Analysis](https://www.paralleldots.com/multilingual-sentiment-analysis) ( The function encodes the input text )
	- Portuguese ( pt )
	- Chinese ( cn )
	- Spanish ( sp )
- [Sentiment Social](https://www.paralleldots.com/text-analysis-apis#sentiment)
- [Custom Classifier](https://www.paralleldots.com/custom-classifier)
- Usage


Examples - [Full Documentation](https://www.paralleldots.com/docs/)
-------------------------------

```javascript
const pd = require('paralleldots-client');

// Be sure to set your API key
pd.apiKey = "YOUR_API_KEY";

// Calls to the API return promises

pd.usage()
	.then((response) => {
		console.log(response);
	})
	.catch((error) => {
		console.log(error);
	})

pd.sentiment('Team performed well overall.')
	.then((response) => {
		console.log(response);
	}).catch((error) =>{
		console.log(error);
	})

pd.abuse("I was not very impressed with the band's performance this year")
	.then((response) => {
		console.log(response);
	})
	.catch((error) => {
		console.log(error);
	})

pd.semantic('Global warming set to exceed Paris agreement’s 1.5C limit by 2040s, according to draft UN report','There is a tipping point’: UN warns climate change goals laid out in Paris accord are almost out of reach')
	.then((response) => {
		console.log(response);
	})
	.catch((error) => {
		console.log(error);
	})


pd.ner('When Michael Jordan was at the peak of his powers as an NBA superstar, his Chicago Bulls teams were mowing down the competition, winning six National Basketball Association titles and setting a record for wins in a season that was broken by the Golden State Warriors two seasons ago.')
	.then((response) => {
		console.log(response);
	})
	.catch((error) => {
		console.log(error);
	})

pd.emotion('I am trying to imagine you with a personality.')
	.then((response) => {
		console.log(response);
	})
	.catch((error) => {
		console.log(error);
	})

pd.intent('How do I cancel my ticket from the app?')
	.then((response) => {
		console.log(response);
	})
	.catch((error) => {
		console.log(error);
	})

pd.keywords('For the Yankees, it took a stunning comeback after being down 2-0 to the Indians in the American League Division Series. For the Astros, it took beating Chris Sale to top the Red Sox.')
	.then((response) => {
		console.log(response);
	})
	.catch((error) => {
		console.log(error);
	})

pd.taxonomy('Deutsche Bank CEO sees far fewer than 4,000 Brexit-related moves: paper')
	.then((response) => {
		console.log(response);
	})
	.catch((error) => {
		console.log(error);
	})

pd.taxonomy('Deutsche Bank CEO sees far fewer than 4,000 Brexit-related moves: paper')
	.then((response) => {
		console.log(response);
	})
	.catch((error) => {
		console.log(error);
	})

pd.multilingualSentiment('Barcelona es una ciudad hermosa')
	.then((response) => {
		console.log(response);
	})
	.catch((err) =>{
		console.log(err);
	})

pd.sentimentSocial('I left my camera at home')
	.then((response) => {
		console.log(response);
	})
	.catch((error) => {
		console.log(error);
	})
```

To import and use a single module
-------------------

Example

```javascript
const sentiment = require('paralleldots-client/apis/sentiment');
sentiment('Team performed well overall.','<YOUR_API_KEY>')
	.then((response) => {
		console.log(response);
	}).catch((error) =>{
		console.log(error);
	})
```
 Available APIs: abuse | customClassifier | emotion | intent | keywords | multilingualSentiment | ner | semantic | sentiment | taxonomy | usage

Note : You must pass your API key as the last parameter for single usage.