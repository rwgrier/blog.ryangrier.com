---
layout: post
title: Swift Labeled Statements
date: '2016-06-29 18:00:41'
tags:
- ios
- app-development
---

I’ll be honest. I didn’t know that Labeled Statements were a thing (let alone in Swift) until a few days ago. I discovered them while reading [Pro Swift](https://gumroad.com/l/proswift) by [Paul Hudson](https://twitter.com/twostraws) for the [Philly CocoaHeads Book Club](http://www.meetup.com/PhillyCocoaHeads/).

Labeled statements allow developers to label control statements. Here’s what a for loop would look like with a label:

<!--kg-card-begin: markdown-->

    fancyLabel: for each in array {    
        ...
    }

<!--kg-card-end: markdown-->

An if statement with a label looks very similar.

<!--kg-card-begin: markdown-->

    anotherLabel: if known == test {    
        ...
    }

<!--kg-card-end: markdown-->

Lastly, a switch statement looks like this:

<!--kg-card-begin: markdown-->

    switchLabel: switch(myEnum) {    
        ...
    }

<!--kg-card-end: markdown-->

As you can see the syntax for a label is _label_ followed by a colon (:) and then the statement as normal.

Ok. So, what can I do with this?

These can be thought of as glorified goto statements. You can use continue or break statements to change the control flow to a labeled statement or break out of a labeled statement.

This can be handy for breaking out of nested loops. Typically, breaking from a nested loop will only break out of the nested loop. Control will remain in any outer loops. By adding a label to the outer loop, you can effectively goto or break from that outer loop.

Here are two examples.

A nested for loop using continue:

<!--kg-card-begin: markdown-->

    fancyLabel: for each in array {    
        for eachSubItem in subArray {        
            switch statement {        
            case one:            
                continue fancyLabel        
            ...        
            }    
        }    
        ...
    }

<!--kg-card-end: markdown-->

Here’s an example of break being called in a nested for loop:

<!--kg-card-begin: markdown-->

    fancyLabel: for each in array {    
        for eachSubItem in subArray {        
            if statement {            
                break fancyLabel        
            }        
            ...    
        }    
        ...
    }

<!--kg-card-end: markdown-->

If you have a complex method that contains nested for loops, a labeled statement will allow you to break from an outer loop and continue on with execution of the method.

Paul had some nice examples in the book. I’m not going to re-publish those here. Instead, I’ve come up with my own poor/contrived example here:

<!--kg-card-begin: markdown-->

    func findNeedle() -> Coordinates {
        var x: Int = 0, y:Int = 0
    
        searchHaystack: for row in haystack {
            for each in row {
                if each == needle {
                    break searchHaystack
                }
    
                y += 1
            }
            
            x += 1
            y = 0
        }
        
        doStuffWithResults()
    
        return (x, y)
    }

<!--kg-card-end: markdown-->

This example will loop through a associated array looking for a value. When it finds the ‘needle’, it will exit out of the nested for loops and continue on with the method.

This is a really simple example on how to use labeled statements. I’ve tried to think of a better example, but nothing really felt good. I feel like the examples I come up with could be written better without the labeled statement at all.

I don’t think these will be entirely useful in practice. In essence they are glorified goto statements and using them feels like a bad code smell to me. If you need to use them, you can probably refactor your code to avoid them. But it’s nice to know that they exist.

