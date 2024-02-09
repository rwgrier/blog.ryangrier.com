---
layout: post
title: Swift Defer Statement
date: '2016-03-15 13:24:52'
tags:
- ios
- app-development
---

Swift 2.0 included a number of new language statements. I recently wrote about the [Swift Guard Statement]({%link _posts/2016/2016-03-08-swift-guard-statement.markdown %}). Defer is another statement new to Swift 2.0. Honestly, I don’t use defer as much as guard, but it can be extremely useful.

What defer does is not obvious at first. Defer will wait to execute a block of code until the current scope (loop, method, etc) is exiting. And it will execute that code whether the scope is exiting cleanly, from a guard, or while an error is being thrown.

Here’s the most basic of examples. The defer block exists before the main body of the code, but it’s not called until afterwards.

<figure class="figure">
{% highlight swift %}
func simpleDefer() {
	defer {
		print("Leaving.")
	}
		
	print("Main body of the function.")
}
{% endhighlight %}

<figcaption class="figure-caption">Simple Defer Statement</figcaption>
</figure>

This can be useful if, for example, there are resources you need to ensure are cleaned up before leaving the current scope.

You don’t need to limit yourself to a single defer statement. You can use multiple defer statements. When more than one are included, they will be called in reverse order. Think of them being included on a stack and popping them off one at a time.

Here’s a simple example of multiple defer blocks. You can see that the order they are defined and the order they are called is reversed.

<figure class="figure">
{% highlight swift %}
func multipleDefer() {
	defer {
		print("one")
	}
	
	defer {
		print("two")
	}
}
{% endhighlight %}

<figcaption class="figure-caption">Multiple Defer Statements</figcaption>
</figure>

As I’ve stated above, the defer statement isn’t just limited to exiting from methods. You can include them in loops. Look at this example. Everytime the loop is executed, the defer block is called at the end of each loop.

<figure class="figure">
{% highlight swift %}
func simpleLoopDefer() {
	var multiplier: Int = 1
	for i in 0..<5 {
		defer {
			print("loop count: \(i); multiplier: \(multiplier)")
		}
		
		multiplier += multiplier * i
	}
}
{% endhighlight %}

<figcaption class="figure-caption">Simple Loop Defer Statement</figcaption>
</figure>

If you’re coming from the world of Objective-C or Java, you can approximate the defer statement with a finally block from a throw statement. The syntax is a little different and in Objective-C and Java, you aren’t allowed to have multiple finally blocks. Here’s a Swift example of a defer block being used like a finally block.

<figure class="figure">
{% highlight swift %}
func throwsDefer() {
	defer {
		print("clean up from error and non-error states")
	}
	
	do {
		try methodThatCanThrowError()
	}
	catch {
		print("Why??? What did I do??")
	}
}
{% endhighlight %}

<figcaption class="figure-caption">Try Catch Defer Statement</figcaption>
</figure>

There is a caveat to using the defer statement. In a defer code block, you cannot transfer control outside of the current scope. You can’t call “return” out of a function, or “continue” out of a loop.

I believe that defer is one of the lesser used statements in Swift. I don’t think it will be used as often as guard. I could probably utilize defer more than I currently am. But it can be useful, so check it out.

GitHub Repo: [rwgrier/swift-defer](https://github.com/rwgrier/swift-defer)

