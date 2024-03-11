---
layout: post
title: Beer Style Guidelines v2024.1 (iOS / iPadOS)
date: '2024-03-11 12:00:00'
categories: [iOS, app development]
---

I know I [said that I wasn’t planning on any major updates]({%post_url /2022/2022-07-26-the-future-of-beer-style-guidelines %}) to [Beer Style Guidelines](https://www.beerstyleguidelines.app). But here I am, releasing a major update to [the app](https://apps.apple.com/us/app/beer-style-guidelines/id998139111). 

This is the first release since last August. 

But this release is only for [iOS and iPadOS](https://apps.apple.com/us/app/beer-style-guidelines/id998139111). The current [macOS](https://apps.apple.com/us/app/beer-style-guidelines/id998139111) version is still v2023.4. I am planning to make updates to the macOS version soon™. 

## What’s New?

The entire user interface has been rewritten. Previously, I was using [UIKit](https://developer.apple.com/documentation/uikit) for most of the UI. I had a smattering of [SwiftUI](https://developer.apple.com/xcode/swiftui/). Now, it’s basically reversed. It's mostly SwiftUI with a smattering of UIKit.

I started with a SwiftUI-only implementation. UIKit made a reappearance in a few places when I struggled for too long getting things working correctly. 

One example is the pageable detail view. I fought with SwiftUI's `TabView` ([doc](https://developer.apple.com/documentation/swiftui/tabview)) with the `.tabViewStyle(.page(...))` modifier for too long. I just couldn’t get it to behave like I was expecting. I finally gave up and went with a `UIPageViewController` ([doc](https://developer.apple.com/documentation/uikit/uipageviewcontroller/)) and never looked back. 

I also struggled getting my keyboard shortcuts working with SwiftUI's `ScrollView` ([doc](https://developer.apple.com/documentation/swiftui/scrollview/)). I have keyboard shortcuts to scroll to the top/bottom, up/down a few lines, up/down a page. With a `ScrollView`, you can scroll to items (with an id), but what I have is one large scrollable View without an id. I couldn't figure out how to scroll to a specific location without an id.  I know how to do this with a `UIScrollView` ([doc](https://developer.apple.com/documentation/uikit/uiscrollview/)). I wrapped the nested SwiftUI content in the `UIScrollView` and used the keyboard shortcuts the way I knew how. 

I'm not saying these two issues are impossible to solve in SwiftUI. I was just getting frustrated with them and it was easier for me to drop back into UIKit to solve the issue. I hope to find a SwiftUI solution to these soon. 

## New Text Rendering Engine

Internally, the style guidelines use Markdown for the storing the guide contents. When a guide section is selected, the markdown is loaded and rendered for the user. 

Previously, I was using [Down](https://github.com/johnxnguyen/Down) as the markdown engine. It was working well enough, but I wanted something that processed tables more naturally. With Down, I could use HTML, but I wanted to use the [GitHub table syntax](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables#creating-a-table). 

I found [MarkdownUI](https://github.com/gonzalezreal/swift-markdown-ui). That library allows for both markdown tables and parses directly to SwiftUI. So far it's been really nice to work with. 

## Bug Fixes

I believe I’ve fixed a few bugs that existed in the old app. I probably introduced a number of new bugs with this update. I’ve made a lot of changes within the app and I’m sure there are bugs somewhere. 

## What’s Next?

I’ll probably take a short break from the app. I’ve been pretty focused on this for the last few months. I need a little break. 

I am going to start working on an updated macOS version in the next week or two. A lot of it already works on macOS. Everything compiles and runs, but not all of the features are available on macOS. But I need to deal with some of the iOS-specific code I put in place. 

The yearly version of the [Brewers Association](https://www.brewersassociation.org) [Style Guide](https://www.brewersassociation.org/edu/brewers-association-beer-style-guidelines/) usually come out around now. When it does come out, I'll be busy getting that into the app. 
