---
title: "About structs, enums and plants"
date: 2019-05-27T06:48:00+02:00
draft: false
---

The last lessons covered structs, enums and switches. Although the explanation about differences between classes and structs was not perfect, I at least got something out of it: structs require less code to initialize objects. And less code is a good thing I guess.

Also, enums and switches are great, especially when using them together. In the following example (yes, it's about plants _again_) I had set the ```size``` to type ```String``` at first. Which works fine of course but, thinking ahead, is not something you want when your users are able to choose the size of anything. Because you'll have a hard time processing the results afterwards if everyone enters _what they think_ the size might be. Big, large, gigantic, skyscraperesque or even small may all refer to the same thing - it's just a matter of perspective.

Same goes for stuff like ```color``` for example but I'll leave it like this in my example code. If your users are allowed to enter anything as a color there will be results like my values ```orange-ish``` or ```green, white and violet```, These values for ```color``` may be correct from your users perspetive. But they are, as mentioned previously, hard to process, evaluate or work with in any scenario afterwards.

So this is where enums really shine. You basically just give your user the choice between a given amount of *hard* values. You want to use this for stuff that you need to differentiate afterwards. If you want to build an app to categorize plants for example, you want people to be able to filter their collection. Maybe after type (think of succulents, roses, whatever), after size (small, medium, large) or even color (white, green, red, you get it...).

But enough of me pretending to actually know anything about coding, pros and cons of different types or plants (not at all, lol). Here's my code for the current challenge. I think it was about building a struct, an enum and putting a switch somewhere. I kinda got lost in my plant-jungle while building this:


**My code:**
```
enum size {
    case small
    case medium
    case large
}

struct plant {
    var name : String
    var color: String
    var potColor : String
    var isSucculent : Bool
    var size : size
    
    func whoAreYou() {
        if name !=  "Groot" {
            if isSucculent {
                print("Hi my name is \(name), I live in a pot which is colored \(potColor) and I'm a succulent.")
            }
            else {
                print("Hi my name is \(name), I live in a pot which is colored \(potColor) and I'm not a succulent.")
            }
        }
        else {
            print("I am \(name).")
        }
    }
    
    func whatsYourSize() {
        if name == "Groot" {
            print("I am \(name).")
        }
        else {
            switch size {
            case .small:
                print("I'm \(name), a \(size)-sized plant.")
            case .medium:
                print("I'm \(name), a \(size)-sized plant.")
            case .large:
                print("I'm \(name), a \(size)-sized plant.")
            }
        }
    }
    
}

var plant1 = plant(name: "Groot", color: "green", potColor: "brown", isSucculent: false, size: .small)
var plant2 = plant(name: "Walter", color: "green", potColor: "orange-ish", isSucculent: true, size: .medium)
var plant3 = plant(name: "Cassandra", color: "green, white and violet", potColor: "white", isSucculent: false, size: .large)
var plant4 = plant(name: "Bernie", color: "green and brown", potColor: "white", isSucculent: false, size: .small)
var plant5 = plant(name: "Alice", color: "green", potColor: "orange-ish", isSucculent: true, size: .large)

plant4.whoAreYou()
plant2.whoAreYou()
plant5.whoAreYou()
plant1.whoAreYou()
plant3.whoAreYou()

plant3.whatsYourSize()
plant5.whatsYourSize()
plant4.whatsYourSize()
plant1.whatsYourSize()
plant2.whatsYourSize()
```

**~~Xcode's~~ My plants Output:**
```
Hi my name is Bernie, I live in a pot which is colored white and I'm not a succulent.
Hi my name is Walter, I live in a pot which is colored orange-ish and I'm a succulent.
Hi my name is Alice, I live in a pot which is colored orange-ish and I'm a succulent.
I am Groot.
Hi my name is Cassandra, I live in a pot which is colored white and I'm not a succulent.

I'm Cassandra, a large-sized plant.
I'm Alice, a large-sized plant.
I'm Bernie, a small-sized plant.
I am Groot.
I'm Walter, a medium-sized plant.
```


Next up on my Udemy course is a coding challenge. I have no idea what this is going to be about but it's surely going to be fun. At least if I can involve my little wooden friend. I am...