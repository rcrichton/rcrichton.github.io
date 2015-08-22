---
layout: post
title: "Reactive Programming: What finally clicked for me"
---

I've been looking into Reactive Programming a bit and what really seems to be missing at the beginning of most tutorials is a clear, precise definition of what Reactive Programming actually a means. After reading a few great tutorials I think this has finally clicked for me.

Think of the word reactivate. What does it mean? **A reaction is a response to some previous event**. Events occur over time, so they come in streams. **Streams of events can be chained together so that events in one stream form a reaction on another**, and that stream can cause an reaction on another, and another, and so on... Reactive Programming is exactly that. You chain together these streams of events so that when an event occurs (such as a mouse click) it causes **a chain reaction of events which automatically affects other parts of the system** (eg. executing an API call, which causes a response event, which causes the UI to be updated). 

To chain together and process events it is often useful to use functional programming constructs. Functions like [`map()`](https://github.com/Reactive-Extensions/RxJS/blob/master/doc/api/core/operators/select.md), [`filter()`](https://github.com/Reactive-Extensions/RxJS/blob/master/doc/api/core/operators/where.md) and [`concatAll()`](https://github.com/Reactive-Extensions/RxJS/blob/master/doc/api/core/operators/concatall.md) exist is reactive libraries to allow you to more easily work with streams of events and to chain them together.

Want to learn more? There are some great tutorials out there that explain these concepts in more detail. One of the best I has seen for Reactive Programming [can be found here](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754) and to learn some functional programming constructs that helps with reactrive programming [this tutorial takes time but is really great](http://jhusain.github.io/learnrx/). I recommend them both. 

So, what do you think? Has this helped your understanding? Did I get something wrong? Let me know in the comments section below.

PS. So what's all this fuss about **Observables**? Observables are just something that you can watch (observe) for events. So, really they are just streams of events that you can listen to and be notified when event occur!
