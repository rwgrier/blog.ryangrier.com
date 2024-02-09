---
layout: post
title: Fibonacci Sequence
date: '2016-03-25 04:00:00'
---

I wrote my first post covering the Fibonacci Sequence two years ago in [April 2014]({%post_url /2014/2014-04-09-fibonacci-sequence %}). The original post was written with Objective-C sample code and only considered one possible solution. A few months later, to my surprise, Apple had a session at WWDC called [Advanced Swift](https://developer.apple.com/videos/play/wwdc2014/404/) which covered some of the approaches used below. I thought this would be a great time to provide an update to the original post but with a bit more detail.

The [Fibonacci sequence](http://en.wikipedia.org/wiki/Fibonacci_number) is a special sequence of numbers. The first two numbers are 0 and 1. The numbers in the sequence after that build on these first two numbers. The pattern is the next number in the sequence is the sum of the two previous numbers.

The Fibonacci sequence begins like this: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, etc…

A few years ago I was interviewing at multiple companies. One interviewer asked me how I would generate a Fibonacci number at a given index.

For example: Given 0: return 0; Given 1: return 1; Given 2: return 1; … Given 20: return 6765.

I started by writing a method that would solve the problem through brute force using [recursion](http://en.wikipedia.org/wiki/Recursion), but it wasn’t really what the interviewer was looking for. I fumbled through the question and didn’t get an offer from that company.

## **Recursion**

Let’s take a look at what I was trying to do during this interview.

The code would look something like this in Swift:

<div class="py-3">
	<div class="card shadow-sm">
		<img class="img-fluid" src="/public/images/2016/fibonacci-sequence-2/recursion.png">
		<div class="card-body mx-auto">
			<small>Recursive Fibonacci</small>
		</div>
	</div>
</div>

Look at how many times that method is called for a relatively small index (20). 21,891 times! That’s not really a good way to do it.

I then took it one step further. I had it calculate the first 29 Fibonacci numbers. This process resulted in the recursive method being called 2,692,507 times, which took about 8 minutes (in Xcode Playgrounds). That’s just not scalable. Let’s try another approach.

## Memoization

During the interview, I had thought that we could cache some of the results. This would allow us to access Fibonacci numbers that had been generated much faster. I wasn’t aware at the time that this technique is called [memoization](https://en.wikipedia.org/wiki/Memoization).

This technique will help optimize the calls once a result has been generated. Since this is a recursive approach which depends on previous calculations, this approach is _much_ more efficient. Let’s look.

I tweaked the code in our recursion example to include memoization. You can see that the code isn’t that much more complex. The caching was easy enough to add. The bonus here is that if we call `fibanocciaAtIndex` for a given index more than once, the answer is immediately returned.

<div class="py-3">
	<div class="card shadow-sm">
		<img class="img-fluid" src="/public/images/2016/fibonacci-sequence-2/memoized-1.png">
		<div class="card-body mx-auto">
			<small>Memoized Fibonacci First Run</small>
		</div>
	</div>
</div>

This time when I calculated the same relatively small index (20), the call count is _much_ smaller, only 21 times.

<div class="py-3">
	<div class="card shadow-sm">
		<img class="img-fluid" src="/public/images/2016/fibonacci-sequence-2/memoized-2.png">
		<div class="card-body mx-auto">
			<small>Memoized Fibonacci Second Run</small>
		</div>
	</div>
</div>

I then had it calculate the first 29 Fibonacci numbers. The results were calculated much faster and with fewer calls. This is a huge improvement over the pure recursive appraoch.

## Golden Ratio — Binet’s Fibonacci Number Formula

Is there another approach? One where you don’t need recursion? Of course there is. I didn’t figure out this approach until well after that interview, which prompted the original blog post.

I did more research into the Fibonacci Sequence and discovered that you can calculate these numbers using the [Golden ratio](http://en.wikipedia.org/wiki/Golden_ratio).

The Golden ratio is defined mathematically as:

<div class="py-3">
	<div class="card shadow-sm">
		<img class="img-fluid" src="/public/images/2016/fibonacci-sequence-2/golden-ratio.png">
		<div class="card-body mx-auto">
			<small>Golden Ratio</small>
		</div>
	</div>
</div>

Or φ ≅ 1.618034…

It turns out you can use the Golden ratio to calculate numbers in the Fibonacci sequence. This is [Binet’s Fibonacci number formula](http://mathworld.wolfram.com/BinetsFibonacciNumberFormula.html):

<div class="py-3">
	<div class="card shadow-sm">
		<img class="img-fluid" src="/public/images/2016/fibonacci-sequence-2/binet-formula.png">
		<div class="card-body mx-auto">
			<small>Binet’s Fibonacci Number Formula</small>
		</div>
	</div>
</div>

This is a much cleaner approach to the original recursive approach above. Instead of dealing with recursion, which can be tricky, this is a straightforward method to calculating Fibonacci numbers.

Here’s what that looks like in code:

<div class="py-3">
	<div class="card shadow-sm">
		<img class="img-fluid" src="/public/images/2016/fibonacci-sequence-2/binet-formula-code.png">
		<div class="card-body mx-auto">
			<small>Binet's Fibonacci Number Formula Code</small>
		</div>
	</div>
</div>

## Large Numbers

In my original post, I had some thoughts about how to handle larger numbers. Unfortunately, I never made any progress there. I think once I posted the original blog post, I lost interest in dealing with really large numbers. There are a few interesting projects like [OSXGMP](https://github.com/githotto/osxgmp) and [BigInteger](https://github.com/kirsteins/BigInteger) that may work here. I’m including them for reference, in case you’re interested in larger numbers.

## Conclusion

There are probably other ways to figure out a Fibonacci number at a given index. I’ve gone through three methods above. I wouldn’t recommend the first approach. Recursion with memoization is probably the cleanest of the approaches and doesn’t require a lot of math.

Just for fun, I’ve put these code samples up of GitHub. The project includes both Swift examples (in Xcode Playgrounds) and Objective-C examples (written using [CodeRunner 2](https://coderunnerapp.com/)). Feel free to get them and play with them.

GitHub Repo: [rwgrier/fibonacci-sequence](https://github.com/rwgrier/fibonacci-sequence)

Thanks to Keith Elliott

