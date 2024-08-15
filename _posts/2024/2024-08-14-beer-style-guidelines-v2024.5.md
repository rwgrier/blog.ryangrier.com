---
layout: post
title: Beer Style Guidelines v2024.5 (macOS / iOS / iPadOS)
date: '2024-08-14 20:00:00'
categories: [iOS, macOS, app development]
---

I recently released [Beer Style Guidelines](https://apps.apple.com/us/app/beer-style-guidelines/id998139111) v2024.3 for macOS,  iOS, and iPadOS. This is a minor update to the app. But there’s one important change. 

I’ve removed the [Telemetry Deck SDK](https://telemetrydeck.com). 

Telemetry Deck is what I've used for years to track analytics within the app. 

Over the last few months, I’ve been getting emails from Telemetry Deck letting me know that I’ve been going over my free limit each month. After some investigation, I discovered that I had a bug in my analytics code where it was over-reporting events. By a lot. Whoops. 

I initially decided to start digging in and looking for the issue. However, after I thought about the issue for a bit, I realized that I don’t really use the analytics that I was reporting. I may have logged into the Telemetry Deck site (or app) four or five times in the last year. I get an email from Apple every week with some very high reporting. And I think the information in the email from Apple is good enough for Beer Style Guidelines. 

I decided to remove Telemetry Deck. The update for this removal went out a little while ago. I’ve also updated the [Privacy Policy](https://www.beerstyleguidelines.app/privacy/) on the [Beer Style Guidelines](https://www.beerstyleguidelines.app/) website to reflect this change. 

This isn’t to say that I’ll never use an analytics reporting tool again. But for _this_ project, I don’t rely or even check on the analytics. 