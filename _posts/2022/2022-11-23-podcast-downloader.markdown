---
layout: post
title: Podcast Downloader
date: '2022-11-23 01:06:40'
tags:
- app-development
---

Since I [stopped working on Beer Style Guidelines]({%post_url /2022/2022-07-26-the-future-of-beer-style-guidelines %}), I have been looking for something to work on.

I've tinkered with a few things here and there. Nothing really stuck until recently. I just finished a small project. I wrote a small app to download podcast episodes.

I have two music (electronic mixes) podcasts that I listen to. I've been listening to these podcasts for over 10 years. I decided that I wanted to download all of the podcasts and import them into the Music app.

I initially looked for apps where I could download all available episodes of a podcast and couldn't find anything I liked. So, I did what most nerds do, I wrote my own.

The podcast downloader that I wrote is written in [Swift](https://developer.apple.com/documentation/swift). It's a [Swift Package](https://developer.apple.com/documentation/xcode/swift-packages) that I run via a [command-line interface](https://en.wikipedia.org/wiki/Command-line_interface).

I got to play with a few new libraries. I used [FeedKit](https://github.com/nmdias/FeedKit) to parse the RSS feed. I used [ID3TagEditor](https://github.com/chicio/ID3TagEditor) to edit [ID3 tags](https://id3.org/Home) on the downloaded [MP3](https://en.wikipedia.org/wiki/MP3) files. &nbsp;Finally, I used [ConsoleKit](https://github.com/vapor/console-kit) to log messages and loading progress to the terminal. It was fun to play with some different libraries in different domain spaces.

For a minute, I thought about open-sourcing the project. But I think it could be used indiscriminately. I wouldn't want anyone wasting bandwidth downloading all podcasts. I was a bit nervous about doing this myself. I decided to send recurring donations to the podcast authors. Prior to performing a full download, I had done a lot of one-episode testing. I also ensured that if the process failed somewhere, episodes wouldn't be downloaded again.

The entire project took me about two weeks of tinkering. It's probably not the best-written code I've produced, but I'm happy with the outcome.

I now have all of these music podcast episodes that I've enjoyed over the years in [Apple Music](https://www.apple.com/apple-music/). I can listen to them again whenever I want.

I'm happy that I was able to work on a new project. I even finished it. Even though this project will likely never be released anywhere.

I'm not sure what I'll work on next, but I am really happy with how this one turned out.

