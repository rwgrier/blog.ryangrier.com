---
layout: post
title: Swift Defer Statement
date: '2016-03-15 13:24:52'
tags:
- ios
- app-development
---

Swift 2.0 included a number of new language statements. I recently wrote about the [Swift Guard Statement]( __GHOST_URL__ /swift-guard-statement/). Defer is another statement new to Swift 2.0. Honestly, I don’t use defer as much as guard, but it can be extremely useful.

What defer does is not obvious at first. Defer will wait to execute a block of code until the current scope (loop, method, etc) is exiting. And it will execute that code whether the scope is exiting cleanly, from a guard, or while an error is being thrown.

Here’s the most basic of examples. The defer block exists before the main body of the code, but it’s not called until afterwards.

<figure class="kg-card kg-image-card"><img src="https://miro.medium.com/max/1400/1*4fQHsDxnT7GgQL0X9kyrFA.png" class="kg-image" alt loading="lazy"></figure>

This can be useful if, for example, there are resources you need to ensure are cleaned up before leaving the current scope.

You don’t need to limit yourself to a single defer statement. You can use multiple defer statements. When more than one are included, they will be called in reverse order. Think of them being included on a stack and popping them off one at a time.

Here’s a simple example of multiple defer blocks. You can see that the order they are defined and the order they are called is reversed.

<figure class="kg-card kg-image-card"><img src="https://miro.medium.com/max/1400/1*FnwA9pAXlxRIlWwxZnASGg.png" class="kg-image" alt loading="lazy"></figure>

As I’ve stated above, the defer statement isn’t just limited to exiting from methods. You can include them in loops. Look at this example. Everytime the loop is executed, the defer block is called at the end of each loop.

<figure class="kg-card kg-image-card"><img src="https://miro.medium.com/max/1400/1*diDBgFX6xLr6uLuo8mnT7g.png" class="kg-image" alt loading="lazy"></figure>

If you’re coming from the world of Objective-C or Java, you can approximate the defer statement with a finally block from a throw statement. The syntax is a little different and in Objective-C and Java, you aren’t allowed to have multiple finally blocks. Here’s a Swift example of a defer block being used like a finally block.

<figure class="kg-card kg-image-card"><img src="https://miro.medium.com/max/1400/1*_kpWrgjtj-sKoKNczda2KA.png" class="kg-image" alt loading="lazy"></figure>

There is a caveat to using the defer statement. In a defer code block, you cannot transfer control outside of the current scope. You can’t call “return” out of a function, or “continue” out of a loop.

I believe that defer is one of the lesser used statements in Swift. I don’t think it will be used as often as guard. I could probably utilize defer more than I currently am. But it can be useful, so check it out.

GitHub Repo: [rwgrier/swift-defer](https://github.com/rwgrier/swift-defer)

