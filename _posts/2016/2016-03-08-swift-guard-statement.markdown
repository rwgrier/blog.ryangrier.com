---
layout: post
title: Swift Guard Statement
date: '2016-03-08 01:47:09'
categories: [iOS, app development]
---

Swift 2.0 added the guard statement to the language. Guard is not new with Swift, it’s been around for a while in other programming languages, such as Haskell and Erlang.

Guard statements are very simple and effective. They ensure the check you are performing is true before continuing on. If the result of that check is false the else statement executes, which usually exits a function.

Here’s a very simple example:

<figure class="figure">
{% highlight swift %}
func submitForm() {
	guard (validationResults == .valid) else {
		return
	}
	
	// Build form request and submit.
}
{% endhighlight %}

<figcaption class="figure-caption">Simple Method With Guard</figcaption>
</figure>

All this does is check the hasValidData variable to see if it’s true. If not, the function exists. This can easily be done with an if statement, like this:

<figure class="figure">
{% highlight swift %}
func submitForm() {
	if (validationResults != .valid) {
		return
	}
	
	// Build form request and submit.
}
{% endhighlight %}

<figcaption class="figure-caption">Simple Method With If</figcaption>
</figure>

Here’s a less simple example. I can’t say more complex, because it’s slightly contrived just to give a taste of how this could go. The guard statement does a few things here. It checks the optional (UITextField.text property) for a value, unwraps it and assigns it locally. If that check fails, the validation fails and the method exits gracefully.

<figure class="figure">
{% highlight swift %}
func validateFormGuard() {
	guard let username = usernameField.text, let password = passwordField.text else {
		return
	}
	
	guard username.lengthOfBytes(using: String.Encoding.utf8) > 3 else {
		validationResults = .invalidUsername
		return
	}
	
	guard password.lengthOfBytes(using: String.Encoding.utf8) > 3 else {
		validationResults = .invalidPassword
		return
	}
	
	guard usernameExists(username) else {
		validationResults = .usernameExists
		return
	}
	
	validationResults = .valid
}
{% endhighlight %}

<figcaption class="figure-caption">Validation Method With Multiple Guards</figcaption>
</figure>

This could also be done with if statements:

<figure class="figure">
{% highlight swift %}
func validateFormIfs() {
	if let username = usernameField.text, let password = passwordField.text {
		if username.lengthOfBytes(using: String.Encoding.utf8) > 3 {
			if password.lengthOfBytes(using: String.Encoding.utf8) > 3 {
				if !usernameExists(username) {
					validationResults = .valid
				}
				else {
					validationResults = .usernameExists
				}
			}
			else {
				validationResults = .invalidPassword
			}
		}
		else {
			validationResults = .invalidUsername
		}
	}
}
{% endhighlight %}

<figcaption class="figure-caption">Validation Method With Multiple Guards</figcaption>
</figure>

If you are checking a lot of properties and conditionals, the if statements can become more nested and can get into a [Pyramid of Doom](http://blog.scottlogic.com/2014/12/08/swift-optional-pyramids-of-doom.html) scenario. The guard statement cleans this up and gives you more readable code.

Guard statements aren’t just for easy function exits. You can use them in loops, where if you don’t meet the conditional, proceed onto the next item in the loop (using continue instead of return).

Guard is an extremely useful mechanism in Swift. It allows you to clean up your code. If you’re writing code in Swift, check them out.

GitHub Repo: [rwgrier/swift-guard](https://github.com/rwgrier/swift-guard)

