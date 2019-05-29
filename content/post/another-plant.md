---
title: "Guess I'll have to buy another plant now"
date: 2019-05-29T06:48:00+02:00
draft: false
---

So the lesson yesterday mainly covered what's new in Swift 5. There are raw strings now, string interpolation, how Swift is great to process error results and some more things. The good thing for me is that I'm just starting with Swift 5 so I hopefully gonna learn this stuff anyway.

What's exciting is the ABI stability of Swift. What this basically means, as far as I understood it, is that iOS developers dont' have to include the Swift runtime when building an app. This means xCode takes less time to finish a build, the file size decreases and loading times for apps using Swift on Apple devices should actually decrease. Hopefully this also opens up possibilities for Swift on other platform like Linux, Windows or Android.

But ABI stability sounds great! And although I'm more than late to the party, this still feels like a great time to start learning Swift. Especially because with the ABI stability, there will probably be less dramatic changes to upcoming versions of Swift from now on.

So instead of following any challenge, I just decided to practice a little bit on my own. So yes, here is yet another _function_ about plants. And yes again, I'm not tired of this whole _I am Groot_ thing yet.

**My code:**

```
enum place {
    case desk
    case sill
}

struct Plant {
    var name : String
    var age : Int
    var place : place


func whereAreYou () {
    if name == "Groot" {
        print("I am \(name).")
    } else {
        switch place {
            case .sill:
                if age != 1 {
                print("My name is \(name), I'm \(age) year old and I'm standing on the \(place).")
                } else {
                print("My name is \(name), I'm \(age) years old and I'm standing on the \(place).")
                }
            case .desk:
                if age == 1 {
                print("My name is \(name), I'm \(age) year old and I'm standing on the \(place).")
                } else {
                    print("My name is \(name), I'm \(age) years old and I'm standing on the \(place).")
                }
        }
        }
    }
}

var plant1 = Plant(name: "Groot", age: 1, place: .desk)
var plant2 = Plant(name: "Walter", age: 3, place: .sill)
var plant3 = Plant(name: "Cassandra", age: 3, place: .sill)
var plant4 = Plant(name: "Bernie", age: 4, place: .sill)
var plant5 = Plant(name: "Alice", age: 2, place: .sill)
var plant6 = Plant(name: "Unknown", age: 0, place: .desk)

plant1.whereAreYou()
plant2.whereAreYou()
plant3.whereAreYou()
plant4.whereAreYou()
plant5.whereAreYou()
plant6.whereAreYou()
```

**The output:**

```
I am Groot.
My name is Walter, I'm 3 year old and I'm standing on the sill.
My name is Cassandra, I'm 3 year old and I'm standing on the sill.
My name is Bernie, I'm 4 year old and I'm standing on the sill.
My name is Alice, I'm 2 year old and I'm standing on the sill.
My name is Unknown, I'm 0 years old and I'm standing on the desk.
```

I should have probably coded something else for an _unknown_ name or _0_ years old into it for this particular plant I don't own already. I just added it for fun to make the switch use all cases. But yeah, I guess I'll have to buy another plant for my desk now. Are there any other cute comic heroes that make a great flowerpot?