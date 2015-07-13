---
title: How to sneak Clojure into your project/company?
layout: default
---

*(So far unordered and uncategorized.)*

*Please contribute with ideas of your own - [edit on GitHub](https://github.com/jakubholynet/trojan-clojure/blob/gh-pages/index.md) and send a pull request or ping [@HolyJak](http://twitter.com/holyjak) at Twitter. Thank you!*

# Resources

* [LispCast: Convince your boss to use Clojure](http://www.lispcast.com/convince-your-boss-to-use-clojure) (9/2014)

# Introducing Clojure[Script]

As [mikethompson described](http://clojurians-log.mantike.pro/general/2015-07-12.html) nicely at the Clojurians Slack channel (general, 2015-07-12 3.30am):

* its all about motivation
* people are motivated by vitamins (being better) and pain killers (stopping something from hurting)
* so the "story" told around Clojure / ClojureScript has to clearly explain what problems it solves and/or what "new and compelling powers it delivers".
*  "innovators" or "early adopters" motivate themselves.  The early majority require better arguments be put, and better explanations be made. They also don't want to have to struggle. They want it easy.

Next point, once you get someone interested in learning (ie. they are motivated):

* they have to "get going" fast.  In the shortest amount of time, they need to be writing code and see results.
* they have to get some early wins. Their program does what it is supposed to.
* they need it on a platter, initially

# Ideas

## ClojureScript

It may be easier to sneak it C.S. than Clojure:

* While backend is typically regarding as very important and tightly controlled, there is much more freedom in choosing your frontend tools and people are used to FE tooling changing very rapidly.
* There are "killer combinations" - e.g. C.S. with REPL + Om + core-async (especially w.r.t. Om Next, where the cool and powerful stuff is coming to C.S. before JS).
* JS + Immutable.js vs. ClojureScript: C.S. is superior as it has not only great immutable data, but also an extremely powerful library for working with the data and things such as core-async. On one project we had JS + React + some libs (no immutable data) and the app had 300kB (Omniscient + Immutable.js would add 100kB to it and still fall short of C.S.). On another we had ClojureScript + React + Om (much superior to plan React) + core-async and a few libs - and it too had only 300kB while being much more powerful.
* Tooling makes development very productive - see e.g. [Bruce Hauman - Developing ClojureScript With Figwheel](https://www.youtube.com/watch?v=j-kj2qwJa_E) (4/2015)
* Jon Pither: [Why ClojureScript Matters - The case for adding ClojureScript to your project](http://blog.juxt.pro/posts/why-clojurescript-matters.html) (6/2015) - no FE x BE split, powerful, exciting future

## Clojure

### Create an XMPP/Slack bot

Create a bot to automate checking Jira, deploying etc. See Erik Assum's 
[example XMPP bot](https://github.com/slipset/mybot) and [GitHub's almighty Hubot](https://hubot.github.com/).

### Use `lein try`

[`lein try`](https://github.com/rkneufeld/lein-try) is great for quickly trying out and experimenting with a Java library:

    lein try commons-codec/commons-codec "1.6"

    user=> (import '[org.apache.commons.codec.net URLCodec])
    user=> (.encode (URLCodec.) "1-_ _&")

### Use Incanter to analyze and visualize data

I used Incanter to fetch data from a DB via JDBC, transform it, and render various charts. Data are more and more important and the ability to play with them is thus increasingly useful.

#### Alternative: Use Gorilla REPL

[Gorilla REPL](http://gorilla-repl.org/) gives you an interactive "notebook" in a webpage where you can enter equations, execute Clojure code, render charts and more. See the screencast on its home page for a demonstration.

### Implement a utility app / tool in Clojure (optionally with a Java API)

Implement a tool/utility app that others can use via command-line or an exposed Java/REST/... API without necessarily telling them it uses Clojure at first. Just make sure that you won't get fired for doing it in an unapproved language.

F.ex. I created [clj_analytics_mongodiffer](https://github.com/jakubholynet/clj_analytics_mongodiffer) mostly in my free time (so I could not be blamed for wasting the employer's money) to ease the operations task of verifying that our staging and production Mongo DBs had approximately the same data.
