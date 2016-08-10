---
layout: page
#
# Content
#
subheadline: "Boolean Values"
title: "The Fundamentals of Ones and Zeros"
teaser: "Thanks to a friend of mine, I've recently been doing a lot of Kata on __Codewars__. If you've never done katas on Codewars before, I would _highly, highly, highly_ recommend it. It's a great site where your competitive nature can get the best of you as you compete with other friends for 'honor'. There are eight levels of difficulty and each kata is a creative coding problem that you solve for honor points. The beginner's level, level 8, is a good overview of incredibly basic coding concepts. Once you enter your solution you are able to see how others solved the same kata."
categories:
  - code
tags:

header: no
image:
    title: mediaplayer_js-title.jpg
    thumb: mediaplayer_js-thumb.jpg
    homepage: mediaplayer_js-home.jpg
    caption: Photo by Corey Blaz
    caption_url: https://blaz.photography/
mediaplayer: true
---


--> http://www.codewars.com

My username is __dukeran__ if you want to add me!

#####_special note: if the same solution was posted by more than two people then I will not site the code._

After going through Chris Pine's _Learn to Program_  book, here is the solution I came up with:

```ruby
	def boolean_to_string(b)
  		if b == true
    "true"
  		else b == false
    "false"
  end
end
```
This is a straightforward code which works just fine but doesn't utilize the fundamental concept of Boolean values.

<!--more-->
It wasn't until I saw other answers and started doing some research that I learned more about it. It started when I saw the most popular answer and was instantly confused:

```ruby
def boolean_to_string(b)
  b ? "true" : "false"
end
```
At first I cocked my head and then wiped my glasses. First of all, what does the ```?``` mean? and why don't you have to specifically tell ruby that `if b = true...` How does ruby automatically know to test for true and false?

The program above may seem painfully simple to any programmer worth their salt but to a newbie in the field, it was a confusionfest - especially when it comes to Ruby. I find that as a Linguistics major with no background in coding, many expert programmers assume that these fundamentals are pure common sense. This is not the case for most non-programmers and I want to break everything down step by step.

#####George Boole, the Foundation Layer
Let's start with George Boole because I always find coding processes/fundamentals easier to swallow when the human element is added to make it a bit more personal. George Boole (1815-1864) was an Eglishman who is credited with laying the foundations for the informational age - the period that marked the shift from Industrial Revolution to what we have today with an economy based on information computerization. Without much formal teaching, he taught himeslf algebra and calculus using mathematics books. He became a prominent member of society and began publishing his own academic articles, lending insight into linear differential equations, invariant theory, and symbolic logic. Also, I learned that Boole is famous for using the term "Universe of Discourse" which is an important and fundamental concept to the linguistic study of pragmatics and semantics!!
In an attempt to systematize and categorize Airstotelian logic in order to be ableto extend its range of application, Boole created the beginnings of  Boolean logic.

#####So What is the Difference Between Boolean logic and Aristotelian Logic?

Aristotelian logic, or term logic, begins with the fundamental assumption that propositions are composed of two terms. The term is a part of speech which carries no truth value but instead represents something such as "man" or "cat". The proposition is what consists of two terms, the "affirmed" or "denied" and the subject which is capable of true or false. Finally, the syllogism is the inference, or conclusion, that one can make from the premises.
Propositions can be either **Universal and affirmative**, **Particular and affirmative**, **Universal and negative**, or *Particular and negative**.


Fun Fact: Mary Everest Boole, his wife, was also a self-taught mathematician and was a strong advocate for teaching children Science at a young age and to make mathematics fun for the young. She often helped George Boole on his academic papers and attended conferences with him as well, unheard of for women of the time. She supported the idea that arithmetic was more anthropomorphic instead of purely abstract.

need to have a question mark to denote the boolean theory!!
