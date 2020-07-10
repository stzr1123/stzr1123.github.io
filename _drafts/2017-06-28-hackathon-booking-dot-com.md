---
layout: post
title: Winning Booking.com's Munich Hackathon
category : hacking
comments: true
---

Over the past weekend I took part in Booking.com's first hackathon in Germany. Our implementation of DonkeyCheck, a hotel recommender system powered by NLP and user reviews, left us winning first place out of seven teams.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Congrats team DonkeyCheck: leveraging reviews to help customers make informed decisions 🏅<a href="https://twitter.com/hashtag/MunichHacks?src=hash">#MunichHacks</a> <a href="https://twitter.com/hashtag/PlanetBooking?src=hash">#PlanetBooking</a> <a href="https://t.co/bS0aNTBZ6C">pic.twitter.com/bS0aNTBZ6C</a></p>&mdash; Work at Booking.com (@PlanetBooking) <a href="https://twitter.com/PlanetBooking/status/879024564789010433">June 25, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

The purpose of the hackathon was simple: Booking.com opened its production API to us and we were to create the best idea we could come up with to make the experience of booking and traveling better. The idea could be based around the booking process, the trip itself or anything in between. We were also not required to use Booking's API nor were we limited by it.

Here I'll go over the main points which I think were key factors in determining our success in this competition. I'll also go over things which ultimately proved not to be absolute indicators of success.

## 1 - We were daring 🚵‍
I really think we made a point not to do anything we had heard being done before. To win we were ready to fail miserably. Up to the very last hour we'd be ready to fail. Our backend implementation had a high chance of not producing expected results from the start. This is because we were betting on the user reviews we'd be able to scrape to be any good for training a neural net to do NLP. Without it, we'd have nothing to show. A hackathon is the ideal environment to take this sort of risks and we sure did not shy away from it.

## 2 - The idea 👍
We felt our idea was new, relatable and simple. People travel alone to cities they don't know all the time. Most of us have felt unsafe at least once while doing this. This is particularly visible with the anxiety of not knowing beforehand the type of neighborhood our accommodation will be located in, specially when booking budget accommodation. The key point here is not necessarily if a place is objectively safe or not, but rather if it "feels" safe to a passing traveler. We thought that this can greatly contribute to the experience of our trip. We then turned this idea into a scalable product once we decided to leverage user reviews to answer this question.

## 3 - Methodology 🎢
When we were announced winners, the judges explicitly commented on our strong methodology over the weekend. Judges, who were software developers and product owners at Booking, would check in with teams every couple of hours to get some progress updates, understand faced difficulties, and bounce around ideas if necessary. We were transparent with the problems we faced, we were clear with the approaches we were taking, we respected each other's ideas, we used arguments to convince one another. We prioritized coding just as much as getting to know each other and playing ping-pong.

## 4 - Pitch 🙌
I'm quite confident we scored almost every point possible from the 5min pitch we had at the end of the hackathon. I started the pitch with a user story, Lin presented our app, Selver explained why we decided to use NLP, and Elias wrapped it all up with a flawless demo. We were product and customer centric in our presentation. Even though most teams had yet to present (and we didn't even know their ideas then), we had set the bar high for others.

## 5 - Implementation 🤖
We had working code. We had a hybrid app running on an iPhone with a beautiful minimalistic UI. We had a deep neural net trained on hundreds of thousands of user reviews. We had a very solid demo. Did it fetch data and performed computations asynchronously? No. Was it blazing fast? No. The neural net was trained on less than 200,000 reviews and about 6M words which is far from ideal (you'd want around 1-3M reviews for a decently good one). We also hardcoded parameters in our classification algorithm which we felt were performant enough. Did our app demonstrate that our idea can be done? Yes.

And those were, I believe, the most important factors which led us to take the first place at this hackathon. I had a lot of fun, learned a lot about myself, Booking.com, and others. As to what we'll do with DonkeyCheck, we'll have to wait and see 😁

# Not key indicators of success 🔥
To mention in passing things which were not key indicators of success,
* Having years of software development experience in your team
* An ironed out, asynchronous, concurrent, log N complexity, fully cached backend implementation with a deployment pipeline
* That cool idea that already exists in five apps
* A non-scalable idea

# Tech we used 📱
* [Ionic](https://ionicframework.com/) for the progressive app
* [gensim Doc2Vec model](https://radimrehurek.com/gensim/models/doc2vec.html) for the NLP
* Angular and Typescript for the frontend
* Python for the backend


<blockquote class="instagram-media" data-instgrm-version="7" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:658px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:8px;"> <div style=" background:#F8F8F8; line-height:0; margin-top:40px; padding:50% 0; text-align:center; width:100%;"> <div style=" background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAsCAMAAAApWqozAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAMUExURczMzPf399fX1+bm5mzY9AMAAADiSURBVDjLvZXbEsMgCES5/P8/t9FuRVCRmU73JWlzosgSIIZURCjo/ad+EQJJB4Hv8BFt+IDpQoCx1wjOSBFhh2XssxEIYn3ulI/6MNReE07UIWJEv8UEOWDS88LY97kqyTliJKKtuYBbruAyVh5wOHiXmpi5we58Ek028czwyuQdLKPG1Bkb4NnM+VeAnfHqn1k4+GPT6uGQcvu2h2OVuIf/gWUFyy8OWEpdyZSa3aVCqpVoVvzZZ2VTnn2wU8qzVjDDetO90GSy9mVLqtgYSy231MxrY6I2gGqjrTY0L8fxCxfCBbhWrsYYAAAAAElFTkSuQmCC); display:block; height:44px; margin:0 auto -44px; position:relative; top:-22px; width:44px;"></div></div><p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;"><a href="https://www.instagram.com/p/BVxjPV3lFha/" style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none;" target="_blank">A post shared by Esteban Zacharzewski (@estebanzachar)</a> on <time style=" font-family:Arial,sans-serif; font-size:14px; line-height:17px;" datetime="2017-06-25T19:26:14+00:00">Jun 25, 2017 at 12:26pm PDT</time></p></div></blockquote>
<script async defer src="//platform.instagram.com/en_US/embeds.js"></script>
