# 49 Years of Music - A Data Driven Study of Lyrics
## Using a combination of web scraping, API calls, and Data Science to map out changes in lyrics from 1978 to 2018
Please read the accompanying [Medium Article here.](https://medium.com/@carlsharpe_71327/49-years-of-lyrics-why-so-angry-1adf0a3fa2b4)

There are two Jupyter notebooks in this repository. They are:
* 49 Years of Music - Collection and Analysis.ipynb, which contains the business question, understanding, data preparation, modelling (part of), evaluation (part of), and deployment of the data (similar to the old school [CRISP-DM model)](https://jenstirrup.com/2017/07/01/whats-wrong-with-crisp-dm-and-is-there-an-alternative/)
* Aggression Classifier.ipynb, which houses the code required to build an ANN to detect aggression.


The inks to the rest of the data you'll need are here:
* [Bad Words List](https://medium.com/r/?url=https%3A%2F%2Fwww.freewebheaders.com%2Fbad-words-list-and-page-moderation-words-list-for-facebook%2F)
* [Kaggle Cyber Aggression Dataset](https://medium.com/r/?url=https%3A%2F%2Fwww.kaggle.com%2Fdataturks%2Fdataset-for-detection-of-cybertrolls)


### Background
I love music. I really enjoy watching the changes and reboots and revamping and resampling of sounds over time. I also enjoy hearaing brand new sounds that haven't been used before as well as updates to classic songs crossed over with jarring beats from things like Dubstep and the like,

I also have a bias to the 90s. The power zone of my teen years, I tend to state, without evidence, that this was 'the best' time for music. Naturally many people disagree, and I find that their teens/early 20s tend to be the zones they hone in on. Music is a psychological and emotional experience. Most of us discover who we are during those years. So it would stand to reason that we identify often identify the songs that make up the soundtrack of that period as 'the best music.'

Nevertheless, I've decided to try to prove/disprove my point with data science. Well, data science combined with web scraping and a lot of API calls to genius.com and then a Bag of Words model and then some other things. I walk through all of it in this longish article. I'm hoping it helps you in your quest for knowledge whether it be data collection (I used requests and BeautifulSoup), data preparation (done with  Spacey), and finally, an ANN with Keras to assess aggression. At the very least, if nothing else, makes for an enjoyable sidebar to your day.

### The Data

#### The Seeds
Firstly, I went to billboard.com and looked for a representative list of all songs from a given year. I found that there's a top 100 list that goes back to 1970 (thus our article title) so I decided to use that as a baseline for grabbing song titles and artists to populate our initial list. www.bobborst.com has a bunch of the missing data so I collected from there as well.

#### The Lyrics
I then took the data that we got from billboard.com and bobborst.com ran API look ups at genius.com to extract the lyric information possible for each song. Some of titles/artists don't match up exactly, so we'll get some misses every year. But we still should be able to get some solid representative data across each year. I put the resulting combination of song titles, artists, and lyrics into a pandas dataframe.

### The Data Preparation
I used SpaCy to prep the data and evaluate the characteristics of the data to ensure that any biases that were obvious could be detected.
# The Analysis
I extracted total words and unique words per song to assess the increase in complexity.
I used a profanity word list from freewebheaders.com to check for profanity in each song and then plotted the frequency of occurrences.
Finally, I built an ANN in Keras that predicts the aggression in a song's lyrics.

Enjoy!
