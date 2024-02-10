---
layout: post
title: Side Projects
date: '2016-05-21 14:31:04'
categories: [iOS, app development]
---

I’m a huge fan of having side projects. I tend to have a handful in some sort of development at any given time. I find that side projects help me alleviate some of the boredom that can come along with a normal job. Instead of just boring old fixing defects for weeks on end, I get an opportunity to flex my muscles a bit. Side projects also give me an opportunity to learn new technologies and skills.

Working on side projects has been a bit tougher lately with life commitments.

Here are a few examples of side projects I’ve worked on.

## DS\_Store Cleaner

[DS\_Store Cleaner](https://www.ryangrier.com/portfolio/) was my first notable side project. I started this project a long time ago when I was a Java developer. It was earlier in my career. I was working with files on Mac OS X, Windows and Linux. Mac OS X creates and maintains (hidden) files call [.DS\_Store](https://en.wikipedia.org/wiki/.DS_Store) files, which are both annoying to deal with and — at one point in time — were a security risk.

The app was originally a small Java app. When I decided to distribute it, I used a tool, possibly just an Ant task, to create a Mac OS X wrapper for my Java app. Looking back, it was terrible. The original Java/hybrid binary I shipped stopped working right around 2010/2011.

This version of the app was actually mentioned in some old Mac magazines. I may even have a few of the issues laying around somewhere.

Fast forward to 2010/2011. I saw some reports that my app no longer worked with the latest version of Mac OS X. By that time, I had transitioned into a role of a fulltime iOS developer and decided to rewrite the app natively and submit to the AppStore.

I did exactly that. I rewrote the app in Obj-C and submitted it to Apple. They rejected the app. I don’t think that they liked me deleting these files that the Finder created. I submitted an appeal. I even found another app in the store that does almost the same thing. Apple called me to discuss the appeal, and let me know that they would never approve the app. I gave up and released the app via my website.

The app has done moderatly well. It’s always been free, so I’ve never seen a penny from it. But it was a great learning experience. I’ve thought about providing an update to the app, but it just hasn’t been been a priority yet.

## Voice360

[Voice360](http://ryan.grier.co/apps) started as a web project. I had been into the Xbox 360 at the time and tracking achievements. I found this nifty site called [360Voice](https://en.wikipedia.org/wiki/360voice) which would track your Xbox 360 game data and generate a daily blog entry for. The blog entry often included any games you may have played the day before and how many achievements you may have earned.

The creators of the site offered an API that developers could use. Around the same time all of this happened, the original iPhone was released. Originally, the iPhone didn’t allow for native apps. So, I decided to write a web app for the iPhone. I didn’t have an iPhone at the time, but I did have an iPod Touch. So, I developed a mobile-friendly site.

Fast-forward a few years. I got it in my mind to develop a native iOS app. So, I did just that. Not only did I develop a native iOS app, I also developed an Android and Windows Phone 8 app. What was I thinking? They didn’t do well at all. I think I sold exactly 1 copy on Windows Phone 8.

Voice360 has been retired. The service isn’t even available anymore. I killed the app before the service was shut down.

## MyCntdwn

[MyCntdwn](https://www.ryangrier.com/portfolio/) was my most successful side project. In fact this side project changed my career path.

This idea started when the iOS SDK was announced. I was looking for something to do with it. My brother suggested a countdown app. It sounded easy enough, so I got right to it. The App Store launched in July of 2008. I had MyCntdwn in the store in October of the same year.

This app led to other side projects and paying side gigs. It also eventually led to me changing from a full-time Java/J2EE developer to an iOS Developer in Fall of 2010.

I created iPad (only) and Android versions of the app. I’ve since pulled both of these from the stores. I wasn’t supporting them. And the iPad app will be supported with a new (Universal) version of MyCntdwn.

I’m still working on MyCntdwn. I swear. I really am. I’ve just been in a bit of a rut lately. The last update to the store was in Fall of 2013. Believe me, I’ve been working on it. I’m currently on my 4th or 5th attempt at version 4.0. This one’s gonna ship, I can feel it. I think I’m still another month or two away from it shipping. I was 75% done with the previous incarnation when my wife saw it, said she hated the new look and I scrapped the entire version. I wasn’t thrilled with the version and her not liking it “gave me permission” to just scrap it.

## Showers

[Showers](https://www.ryangrier.com/portfolio/) was a project that I thought of and wrote 90% of it in a weekend. I had the idea for an app that would include rain sounds, plus variable thunder sounds.

Showers was by no means a financial success. I never thought it would really be one. It was an experimental app for me. I got to learn quite a bit more about AVPlayer, weighted random numbers, Apple Watch and more.

This project was also initially rejected by Apple. The original UI was much simplier. The reviewer I got didn’t like that it was so simplistic. I added the settings/about screen and that seemed to make the review board happy.

I’ve made a few dollars from Showers. Last Summer, I decided to make the app free for everyone. It’s still got a handful of users. I think I’ll make an update to the app and fix a few of the crashing issues. I will probably end up removing the Apple Watch support. I never use the watch app, I don’t know if anyone else does. I may as well remove it.

## Beer Styles Guidelines

I’ve been a homebrewer for the past few years. It’s been a fun hobby. As part of that hobby, I’ve been trying to learn more about the various beer styles. Drinking new beer styles and examples is most of the fun. [Beer Style Guidelines: BJCP 2015](https://www.beerstyleguidelines.app) fits perfectly into that hobby.

There is a certification you can get for judging in homebrew competitions. It’s called the [Beer Judge Certification Program](http://www.bjcp.org/) (BJCP). For this program, you learn more about the various beer styles including origin, tasting notes and even commercial examples.

There are currently a few BJCP apps on the store. [BJCP 2015](https://itunes.apple.com/us/app/bjcp-styles/id293788663?mt=8) and [Beer Styles — BJCP 2015 & 2008 Style Guidelines for beer, cider & mead](https://itunes.apple.com/us/app/beer-styles-bjcp-2015-2008/id787305371?mt=8) were both available on the store when I built and released the app. Both are very good apps. I thought I could do better though. I think I’ve added some nice features to the app idea.

This one didn’t make any money, but I learned quite a bit while working on it. Not only things about iOS and Swift, but about homebrew and beer. I thought about making the app ad supported, but removed any ads at the last minute.

For this project, I also did all of the “artwork.” For better or worse, it’s all my own creation. In the past I have relied on my brother to help me out with that. With this project, I decided that I wanted to give it a shot myself.

I fully intend to release an update to the app. I’ve gotten the OK to include other beer style guides and intend on including them in an update. I just haven’t had the time that I need to do this properly. For such a small app, there’s quite a bit of work involved getting the beer styles in place in the correct format.

## More To Come

There’s a common thread throughout all of these side projects. I’ve learned quite a bit from them. They also give me a break from my day job. I’ve got a handful of side projects in the pipeline. None are ready for real users yet (and may never be).

I really like working on more experimental apps. I plan on doing more. If they are successful, I can continue to mature the apps. If they are failures, I often try to support them for a year or so and then move on to something new and exciting.

Side projects have always given me an opportunity to learn new and exciting things. While they may not all succeed, they have been great learning opportunites. A side project being successful or not shouldn’t diswade you from trying. I believe everyone should work on a side project or two. You never know, that experimental side project you’ve been working on may change your career.

