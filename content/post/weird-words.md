---
title: "Just some weird words"
date: 2019-05-28T06:48:00+02:00
draft: false
---

I have five plants. My favorite plant is the one in my Groot flowerpot. Groot is my favorite character from Guardians of the Galaxy! I also have two succulents, one bonsai and one other plant which I don't know the name of. Groot is sitting on my desk, looking at me, while the other four plants are standing on my sill. Do you have plants?

What's that weird text about? I'm glad you asked that (quietly to yourself, who is weird now?). So yesterday I had a coding challenge in my Udemy course to _Make a function that takes in any text and counts how many words there are total AND list the words from most used to least. Be sure to lowercase everything in the string._

That's what that weird text is about. Just writing it to use it for a function feels even more weird, trust me. Anyway, I must admit that I had a hard time making this function. [Nick](https://twitter.com/nickchuckwalter), the creater of the [Udemy course](https://www.udemy.com/share/1012RsAEoedVdUR3w=/) I'm taking, had introduced us to the the different components (dictionaries, arrays, counting, loops, etc.) in previous lessons but we've never really used it all together so far.

So, in the first place I simply had no idea what to do. But he at least gave us some hints on what to do when:

_1. Lowercase all words_
_2. Turn the String into an array of strings_
_3. Turn that array into a dictionary with the words as keys and count as value_
_4. Sort that dictionary into an array_

Nick also explicitly said that he wants us to learn how to search the internet for stuff we don't know yet. What is what I would've done anyway but is still a great advice. At work we have a rule to search the internet for at least 10 to 30 minutes if you're not sure about a solution to a problem. This is great because you teach things to yourself this way and you don't bother other people with stuff you can easily find after three minutes on your favorite search engine.

So, this search-the-internet-thing seems to be quite normal for developers. Let me tell you, it apparently doesn't feel like common sense to a lot of marketing people to simply search for stuff you don't know. And yes, this feels hard sometimes but of course I'm always happy to help. With some lmgtfy links of course.

Of course this took me longer than three minutes. No, I didn't managed to solve this 100% on my own. But I understand it now, after searching for it and puzzling things together. And that feels good, too.

But enough of weird words, you're here for some code.

**My code:**

```Swift
import Foundation
import UIKit

func wordCount(input: String) {
    var text = input.lowercased()
    text = text.replacingOccurrences(of: "\n", with: " ")
    text = text.replacingOccurrences(of: ",", with: " ")
    text = text.replacingOccurrences(of: ".", with: " ")
    text = text.replacingOccurrences(of: "?", with: " ")
    text = text.replacingOccurrences(of: "!", with: " ")
    text = text.replacingOccurrences(of: "  ", with: " ")
    
    let words = text.components(separatedBy: " ")
    var wordDIctionary : [String : Int] = [:]
    
    for word in words {
        if wordDIctionary[word] == nil {
            wordDIctionary[word] = 1
        } else {
            wordDIctionary[word] = wordDIctionary[word]! + 1
        }
    }
    
    print("\(wordDIctionary.count) words")
    
    let sortedWords = wordDIctionary.sorted { (word1, word2) -> Bool in
        return word1.value > word2.value
    }
    
    var rank = 1
    for word in sortedWords {
        print("\(rank). \(word.key) - \(word.value)")
        rank += 1
    }
}

wordCount(input: """I have five plants. My favorite plant is the one in my Groot flowerpot.
Groot is my favorite character from Guardians of the Galaxy!
I also have two succulents, one bonsai and one other plant which I don't know the name of.
Groot is sitting on my desk, looking at me, while the other four plants are standing on my sill.
Do you have plants?""")
```

**What xCode made of it:**

```
42 words
1. my - 5
2. the - 4
3. is - 3
4. i - 3
5. plants - 3
6. one - 3
7. have - 3
8. groot - 3
9. on - 2
10. other - 2
11. plant - 2
12. favorite - 2
13. of - 2
14. name - 1
15. and - 1
16. galaxy - 1
17. character - 1
18. which - 1
19. know - 1
20. sitting - 1
21. four - 1
22. are - 1
23. also - 1
24. you - 1
25. at - 1
26. flowerpot - 1
27. bonsai - 1
28.  - 1
29. do - 1
30. two - 1
31. desk - 1
32. guardians - 1
33. looking - 1
34. from - 1
35. in - 1
36. me - 1
37. while - 1
38. don't - 1
39. succulents - 1
40. standing - 1
41. five - 1
42. sill - 1
```

That's it. It felt quite hard building it, but it was fun to see it slowly coming together and giving me results.
But seriously, do you have plants?