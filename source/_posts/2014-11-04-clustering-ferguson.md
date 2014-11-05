---
layout: post
title: "Clustering Ferguson"
date: 2014-11-04 16:41:00 -0500
comments: true
categories: 
---

For my most recent project at [Metis](http://www.thisismetis.com/), I analyzed tweets with #Ferguson or #FergusonOctober from October 11-13, also known as the organized Weekend of Resistance where activists from around the country traveled to Ferguson to stand up against police brutality and to demand justice for the murder of Michael Brown and other innocent lives lost at the hands of the police.  I wanted to see what I could learn from clustering the tweets that I gathered.

After collecting about 300,000 tweets (re-tweets included) through Twitter's API and Tweepy in Python, I separated the re-tweets from the unique tweets and created 75 clusters out of the 50,000 unique tweets, using MiniBatchKMeans in Python's sklearn module. In each cluster, I looked at the most important words by looking at 2-gram phrases/words with the highest [tf-idf](https://en.wikipedia.org/wiki/Tf%E2%80%93idf) values. In this post, I will concentrate on the 3 biggest clusters.

-> {% img /images/Cluster1.jpg %} <-

Tweets in this cluster include:

> \#FergusonOctober: Protesters march on police station in St Louis http://t.co/KnUKM4fDzF

> Hundreds outside the police station. #FergusonOctober #BlackLivesMatter http://t.co/XHXeSKFjw4

> People gathered outside the police station chanted his name and badge number #fergusonoctober #policingthepolice

The first cluster had around 14,000 tweets, and looking at the words with the highest tf-idf values, this cluster seems to focus on the police department. This is not surprising at all considering the entire movement is standing up against police brutality, and this weekend in particular focused on Ferguson's police department.  Furthermore, the Weekend of Resistance had a variety of events ranging from talks to sit-ins to protests, so this cluster was for tweets that focused on the march to the police station.

-> {% img center /images/Cluster2.jpg %} <-

Tweets in this cluster include:

> Young Nigel waits for the rest of the #FergusonOctober marchers to catch up. http://t.co/p41U76eQOp

> The story behind this AMAZING photo of young Nigel http://t.co/jUc55Xb2Eq #FergusonOctober #ferguson http://t.co/o1T5BtQtZt

The second cluster contained about 5,000 tweets. The name "Nigel" came up a lot in it. Not knowing off the top of my head who Nigel was, I Googled the name and came across [this story and photo](http://www.dailykos.com/story/2014/10/11/1335898/-The-story-behind-this-AMAZING-photo-of-young-Nigel).  I remember this photograph circling around the internet, but didn't know the name of the child was Nigel, so it was interesting to see this showing up in one of the biggest clusters.

-> {% img /images/Cluster3.jpg %} <-

Tweets in this cluster include:

> Dr. Cornel West arrested during #Ferguson protests: http://t.co/VLIaTzMmck

> \#cornelwest arrested & in police van now in act of civil disobedience #moralmonday #fergusonoctober http://t.co/hGDsrycAr4

The third cluster also had about 5,000 tweets. This cluster focused around Dr. Cornel West.  West is an important figure in the anti-racism movement, so it is expected that people would tweet about his involvement, and even more about his arrest. Through this clustering, I also learned that many people misspell Dr. West's first name.

My time on this project was limited - if I had more time, there are many things I would tweak/change, including:

* removing @usernames to exlucde direct conversations between users
* adding retweets to the current clusters (without reclustering) and measure sizes changes
* adding retweets and reclustering to see if there would be changes in clustering
* trying different clustering techniques (e.g. DBSCAN) and comparing results
* focusing only on the hashtags, aside from #Ferguson and #FergusonOctober
* analyzing tweets by day and/or time to see if certain topics were talked about on certain days or times of the day than others

Code for this project can be found [here](http://www.github.com/dmelass/fletcher).