---
title: "I am Groot"
date: 2019-05-26T06:48:00+02:00
draft: true
---

[groot]: /i-am-groot.jpeg "Classes are fun!"

So, yesterday the Swift challenge was to find something in my room and make a class of it. I just stocked up on plants, so I obviously had to choose them. Beside four normal flowerpots, which are orange(-ish) and white, I also have on Groot flowerpot. Cute little Groot always sits in front of me at my desk, dreamy looking at me with his big eyes while holding his wooden head in his tiny wooden hand.

![Picture of a Groot flowerpot][groot]

Yes, this is cheesy. Yes, I think he's adorable.

Anyway, the challenge was only about setting up a class and initializing different objects of it. Not a hard challenge, so why not add a fun twist to it? I wanted my plants to tell me if they're Groot or not.

**So this is what my code looks like:**

```Swift
    class plant {
        var size = ""
        var color = ""
        var potColor = ""
        var isGroot = false
        
        func iAmGroot() {
            if isGroot {
                print("I am Groot.")
            }
            else {
                print("I'm just a regular plant.")
            }
        }
    }
    
    var plant1 = plant()
    plant1.size = "small"
    plant1.color = "green"
    plant1.isGroot = true
    plant1.potColor = "brown"
    
    var plant2 = plant()
    plant2.size = "medium"
    plant2.color = "green"
    plant2.isGroot = false
    plant2.potColor = "orange-ish"

    var plant3 = plant()
    plant3.size = "large"
    plant3.color = "green, white and violet"
    plant3.isGroot = false
    plant3.potColor = "white"

    var plant4 = plant()
    plant4.size = "medium"
    plant4.color = "green and brown"
    plant4.isGroot = false
    plant4.potColor = "white"
    
    var plant5 = plant()
    plant5.size = "large"
    plant5.color = "green"
    plant5.isGroot = false
    plant5.potColor = "orange-ish"

    plant1.iAmGroot()
    plant2.iAmGroot()
    plant3.iAmGroot()
    plant4.iAmGroot()
    plant5.iAmGroot()
```

**And here's the output:**

```Swift
I am Groot.
I'm just a regular plant.
I'm just a regular plant.
I'm just a regular plant.
I'm just a regular plant.
```

After seeing the results I thought this is ridiculous, because the chance that real Groot would've said something else is quite small anyway.
But that's it. These little fun things really help me learning Swift. And what Groot's clearly means in this case is that *Learning about classes is fun!*


![Picture of a Groot flowerpot][groot]
Isn't he adorable? And although the other four plants are not Groot, I still love them and take good care of them, of course! 
