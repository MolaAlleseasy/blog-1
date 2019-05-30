---
title: "9 apps to rule them all"
date: 2019-05-30T06:48:00+02:00
draft: false
---

I'm excited because my girlfriend and I are going to Israel for 10 days soon. We made the concious decision to not bring our laptops in order to really have some time off. I'm really looking forward to having time for ourselves, being a bit more disconnected and not staring at my screen all day.

But I'm also slightly concerned regarding my learning schedule. I feel like I'm making progess and I'm looking forward to learning Swift and trying out new things every day. The only thing is, I can only do it on my MacBook. 

I thought about alternatives like installing Linux on my old Chromebook or buying a preowned iPad to at least being able to use Swift Playgrounds, the kind-of offical Swift learning app I guess? I even thought about bringing my MacBook. But I want to focus on recharging _my_ batteries, not my laptop's one. We're also just bringing hand luggage with us and a 15" device is anything but small and light.

Do I have any alternatives? As mentioned in the first article I wrote about me learning Swift, I already tried out Mimo in the past. It's a cute little app which is okay-dokay for repitition but not really about _writing_ code, which is what I need to do if I want to improve my skills.

So I had this idea. Mimo is not the only app on the AppStore which promises to improve my Swift knowledge and skills. What if I just pick a selection of apps, try them for the 10 days and maybe rate them in different categories. Sounds like it should help me to get better with Swift, sounds like fun, sounds like it could even be useful for other beginners.

There we go! I picked ~~nine~~ (seven tbh) apps to ~~rule~~ rate them all which I will test in different categories.

## Which apps will I test?

Here is a screenshot of the _Learn Swift_ folder on my iPhone which contains the apps I will test for learning Swift:

[apps]: /9-apps-to-rule-them-all.jpg "Screenshot of the Learn Swift folder on my iPhone which contains nine apps about learning Swift"

* LearntoCodewithSwift
* Design+Code
* ProgrammingHub
* Py
* SwiftBites
* Code Swift
* Mimo

Somewhat out of competition are these two apps:
* Swift Compiler
* Udemy

## How will I test the apps?

I will try to stick to my schedule of learning and practicing one hour every morning.
I'll probably also test them in between during the day or while we are moving across the country via bus or train.
What I haven't decided yet, is if I'm gonna test them in a row, one app a day or just randomly with no order at all, mixing them up.


## What categories will I test and rate the apps in?

I have decided to test and rate five different categories (by now):
* Content
* Accesibility
* Usability
* Engagement
* Price

### Content
In this category, I'll rate the amount of content that is available in the app. I'll also rate this based on the quality of the content and how it's structured. Do they include the bigger picture in the lessons? Is it structured in lessons at all?

### Accessibility
Accessibility in this context means to me how accessible the content is. I made the concious decision to separate this from the overall content category. The difference to _content quality_ for me is that you can have high quality content which is not very accessible. And the other way round of course, too.

The category accessibility rates how easily I can digest the content, understand everything and apply it practicaly. Especially the last point, the ability to apply the content of an app practicaly, is very important.

### Usability
This category is all about how the app itself is structured and how it's build around the content. Am I able to easily find what I want and what I need? Is there a possibility to track my progress? With usability I will rate how the app creates a supportive learning environment that enables me to really make progress.

### Engagement
In this category I'll rate how the app keeps me engaged with learning and improving. Is there a system that incentivices learning? Are there any challenges that really challenge me and make me want to solve the given problem? Can I track my progress? Do I have something like a personal assistant or at least a mascot which motivates me?

### Price
This one obviously rates how much I have to pay for the good stuff. You can download all apps I chose for the test for free on the AppStore. I assume that most of them have in-app purchases and I'm willing to find out how much bang I get for my bucks.

## Do I have a system to rate them and store the information?
Yes, this question may sound weird. But for a reason. I just wanted to show the "system" I built to rate the different apps. This is what this article really is about, because this is still a documentation of me learning Swift. So, of course I built it in Swift, based on my current skill level and some search engine magic.

If you want to know how it's done, just check the following code and my comments:

```Swift
// #############################################################################
// Building my own system to rate different apps to learn Swift
// #############################################################################

// The following enum provides a consistent rating for all categories

enum rating : String {
    case OneStar = "one star (★☆☆☆☆)"
    case TwoStars = "two stars (★★☆☆☆)"
    case ThreeStars = "three stars (★★★☆☆)"
    case FourStars = "four stars (★★★★☆)"
    case FiveStars = "five stars (★★★★★)"
}

// Every app in my test will be an object of the class App
// Every object of class App has to have a name and can have ratings and reasons for these ratings for different categories

class App {
    var name : String = "Who am I?"
    var content : [rating : String]? = [.OneStar : ""]
    var accessibility : [rating : String]? = [.OneStar : ""]
    var usability : [rating : String]? = [.OneStar : ""]
    var engagement : [rating : String]? = [.OneStar : ""]
    var price : [rating : String]? = [.OneStar : ""]
    
    // The following function lets me rate the content of an app
    // It sets the input as the value for the variable of the object I used to call the function 
    // Then it's prints out what I have just entered along with the name in order to let me check my input
    
    func rateContent(stars: rating, input: String) {
        self.content = [stars : input]
        print("You have rated \(name) with \(stars.rawValue). The reason is: <<\(input)>>")
    }
    
    // The following function lets me rate the accessibility of an app
    // It sets the input as the value for the variable of the object I used to call the function 
    // Then it's prints out what I have just entered along with the name in order to let me check my input
    
    func rateAccessibility(stars : rating, input : String) {
        accessibility = [stars : input]
    }
    
    // The following function lets me rate the usability of an app
    // It sets the input as the value for the variable of the object I used to call the function 
    // Then it's prints out what I have just entered along with the name in order to let me check my input
    
    func rateUsability(stars : rating, input : String) {
        usability = [stars : input]
    }
    
    // The following function lets me rate the engangement of an app
    // It sets the input as the value for the variable of the object I used to call the function 
    // Then it's prints out what I have just entered along with the name in order to let me check my input
    
    func rateEngagement(stars : rating, input : String) {
        engagement = [stars : input]
    }
    
    // The following function lets me rate the price of an app
    // It sets the input as the value for the variable of the object I used to call the function 
    // Then it's prints out what I have just entered along with the name in order to let me check my input
    
    func ratePrice(stars : rating, input : String) {
        price = [stars : input]
    }
    
    
}

var App1 = App()
App1.name = "Mimo"

var App2 = App()
App2.name = "Code Swift"

App1.rateContent(stars: .ThreeStars, input: "It has some but not too much content about learning Swift.")

App1.ratePrice(stars: .FiveStars, input: "The app is free, that's great!")

App2.rateContent(stars: .TwoStars, input: "Just some basic content about Swift.")

App1.content
App2.content

App1.price
```

And this is what the results currently look like:

```
You have rated Mimo with three stars (★★★☆☆). The reason is: <<It has some but not too much content about learning Swift.>>
You have rated Code Swift with two stars (★★☆☆☆). The reason is: <<Just some basic content about Swift.>>
```

As mentioned in the comments of my code, I simply print out whatever I put in the for function. I find this useful to get some feedback on my input in order to check if I entered everything correctly.

Maybe, some day in the future, I'll be able to take some of this code or at least the ratings and create an app about learning Swift which summarizes apps, courses, podcasts, events and all the other resources out there. I'll put that on my list, next to _rabbit_.