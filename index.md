---
title: How to sneak Clojure into your project/company?
layout: default
---

*(So far unordered and uncategorized.)*

*Please contribute with ideas of your own - [edit on GitHub](https://github.com/jakubholynet/trojan-clojure/blob/gh-pages/index.md) and send a pull request or ping [@HolyJak](http://twitter.com/holyjak) at Twitter. Thank you!*

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
