---
title: "Advent of Code Day 1: A new challenge"
date: 2024-12-02 14:00
tags:
  - yearofdone
---
_The full code for my solutions can be found at my [Advent of Code Github repository](https://github.com/Wigsinator/advent-of-code)._

First off, a little preface: Advent of Code is a yearly event run by Eric Wastl. He creates short coding challenges with fun theming, usually resulting in you putting in the work to save Christmas, just in time. It's a great way to flex your muscles and push yourself. They release every day at midnight eastern time, and they track a leaderboard of the top 100 finishers. Given that it is, again, releasing at midnight, and the fact that it's a language I'm not super familiar with, I'm under no illusions that I'm very unlikely to ever place. Which is a bit of a good thing, because it means I can release my code basically immediately upon completion.

Early on, one of the big Advent of Code challenges is just parsing your input. I did a bit of research into this, and found [Alex Chao's Advent of Code Go](https://github.com/alexchao26/advent-of-code-go) repository, from which I gratefully took a lot of the skeleton code. This gives me a skeleton with one of Go's big advantages for input parsing: the embed package. With this, I'm easily able to just read in my input as a string at compile time, which I can then split apart and cast as needed. Extremely, extremely helpful. 

Day 1's challenge involves a comparison of 2 lists, part 1 checking the differences between their values in sorted order, and part 2... I'll get to part 2 in a sec.

### Part 1

Day 1 Part 1 is pretty trivially easy, which, you know, to be expected. Run a sort on each of them, then iterate through both simultaneously, summing the absolute difference between each element on the list. Go doesn't seem to have an absolute value function for integers, so I just checked which is bigger before taking the difference. Shouldn't really matter. Sorting has a worst case of `O(nlogn)`, after that we're iterating once through both lists, so it's just another `n` clock cycles. Part 1 is done in `O(nlogn)` due to the sorting complexity.
### Part 2

Day 1 Part 2 is also pretty trivially easy, but I struggled for a stupid reason: I didn't read the prompt well enough and forgot to multiply the similarity scores by the actual values. In my defence, it was 1 am. Calculating the similarity scores is a sum of each value in the first list multiplied by the number of times it appears in the second list. 

My solution is simple: Iterate once through the second list, creating a map with a count of how often each element appears in that list. From there, we iterate though the first list, adding the multiplied value to our combined sum. Pretty simple stuff.

I'll be honest, at first, I wasn't satisfied. I didn't like how I had to iterate through the second list, because there are elements in there that won't appear in the first list! Looking at those is suboptimal! Ultimately, though, iterating through each list once is a clean `O(n)` time, and because the map gets are `O(1)`, that's a damn good time. In theory, I thought about searching through the second list as I went through the first, only looking for elements when I needed them. But the list is unordered, so each search would need to search through the whole list, making the worst case (Every element in the first list is unique) have a time complexity of `O(n^2)`. That's WAY worse. Searches can be faster if the list is sorted, but as I previously said, sorting takes `O(nlogn)` time, which is slower than my current time. And even then, the searches would only be cut down to `O(logn)` at best, which means that, if List 1 is the worst case scenario, we have `O(nlogn)` again. On the whole, it's pretty much always more efficient to just take the loss on a few clock cycles and a bit of space as compared to trying sort and search on the fly. So I'm pretty happy with what I've got.