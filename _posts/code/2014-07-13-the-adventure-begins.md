---
layout: page
sidebar: right
subheadline: Templates
title:  "The Adventure Begins"
teaser: "I couldn't help but feel bittersweet as we drove out   of my driveway towards the airport, leaving my family waving at the doorstep of the house. Going on big trips is always bittersweet for me, I always hate  saying goodbye to those I love but at the same time I can't wait for another  adventure to begin. For me, there is nothing like new sites to see and new  experiences to be had, all the while meeting new and interesting people."
breadcrumb: true
tags:
    - post format
categories:
    - traveling-code
    - code
image:
    thumb: gallery-example-2-thumb.jpg
    title: gallery-example-2.jpg
    caption: Unsplash.com

---


And so it has begun! My friend Charlotte and I have boarded our flight for    Lima, the capital of Peru. Saying goodbye to my family and extended family brought tears to my eyes.
<div id="container">
<br>
<center><img src="http://i.imgur.com/9AljWer.png"  alt="My own cat picture" height="300" width="300" style="margin:10px 10px">
</center>
</div>


Like most other people on the internet, I'm obsessed with my cat. She is my   pride and joy, even if she can be a bit peevish sometimes. I swear, with the   rate of cat pictures being uploaded daily, the percentage of Mr. Whiskers   pictures might surpass the amount of porn to be found on the web.

<!--more-->

Since I am going to miss my little feline buddy, I decided to practice some of   my new coding skills, using the few tools I have in my tool kit. In the   following code (with the help of Chris Pine's example as a template) I created a   little virtual cat that I can take care of while I'm away from my living, breathing fuzzball. I named the program Thea, after my precious fuzzball.


**The items I used in my recently aquired tool kit:**
*variables
*loops
*recursion
*creating a new class
*defining methods

And...that about sums up my entire tool kit. Hopefully one day that list will   be longer!

My most recently aquired tool is _defining a class_. A brand new and exciting   concept. This time I initialized the ````class Pet````
Note that class remains lowercase while the new class that you are initializing   is capitalized. One thing that was stressed in Chris Pine's book is the   difference between `new` and `initialize`. It's not a horribly confusing   concept but I want to go over it real quick. `new` comes first. You cannot   initialize something that has not yet been created! `new` creates the objet   that the computer will then `initialize`. `new` creates the object only, it is   never used again while `initialized` needs to be defined because you need to   explain to your poor computer what you want to do with this brand new object.   You can only use `new` to _create_ a new object, if you use `initialize` in   order to create a new object, the computer will freak out, looking for some    nonexistant object to start up, and will spit out a panic-stricken error code.   Yes, personalizing the computer and its languages makes it easier for me to   understand, hopefully it does for you too!


This one `class` is 155 lines long and it only takes one to initialize it and  to get it running.

Within the `class` I have defined over seven different methods;
* `initialize`
* `feed`
* `play`
* `walk`
* `put_to_bed`
* `code`


In each `def` (define) I clearly lay out the groundworks for how I want the   computer to respond in different scenarios. In this code I only have two   possible environments; asleep and not asleep. I can only imagine this makes it   easier to keep track of all the possiblities and possible behaviors. I   definitely suggest if you try writing this code for practice and you're new   like me, start with only two different possible scenarios until you're able to   effortlessly keep track of all the different possibilities.


There's one thing that confused me when I first read the template and started   writing my own program. What the heck does " `@variable` mean? In the first 5   lines of code there is this new symbol that I've never used before: "`@`". Much   confused. I decided to look it up and explain it to other newbies: the `@` signifies an instance variable of the specific class. It is important because it only functions within the class and you use it to tell the computer that you want something done in that particular instance. It's also cool because it is the same variable but at different defined instances you assign it a different value.


Here's a quick snippet from one of the `def` methods:

```ruby
def feed
  puts "Thea purrs as you pick up her food bag."

  puts "She winds in between your legs as you put a handful of food into her food bowl."

  @stuffinbelly = 5

  passageoftime

  peeve

end

```


I think in the big picture this is an amazing thing about Ruby. This is line 13 to 20 of the code. I have in no way defined the variable `passageoftime` or `peeve`. I don't  define them until line 91 and line 125. To me, this is so not intuitive.  Imagine going up to someone and being like "Remember that blubber story?" and   then laugh. That person is going to look at you like you've lost your freaking   mind because s/he has no context or no idea what you could possibly be   referring to. Later that day you walk up to that same person and tell him/her  a hilarious story about how you were living with some Inuits up in Alaska and you   thought the blubber they offered you was ice cream until you took your first   bite. Now this person has context and can laugh with you. But this is only after you have taken a random variable of "blubber" and put it into a context.   It doesn't need to work this way with Ruby! You do the same thing with   Ruby and she will know to laugh earlier in the day even before you told the   blubber story just because you told it later that day. It's as if Ruby is living in a world where she processes your code so fast that time doesn't   exist in a linear fashion. Whether something happens in the past or in the   future doesn't matter to it, as long as it is all in that one instance of code.   If this isn't cool to you, then well, you lack imagination and excitement in   your life...

![Taking the fuzzball for a swim and a walk](http://i.imgur.com/bIMAIO2.png)


A new thing I learned while writing this code is the (method/function?)   `private`. It means that the following code and its functions can only be   modified in the code itself and the user running the program can't access it.   It's like the hidden part of the code that is running behind the scenes and   makes the interface run smoothly.


Here's the loop that I threw into my code!

```ruby
def ask question
  thea = Pet.new 'Thea'
  while true
    puts question
    reply = gets.chomp

    if reply == 'feed'
      thea.feed
    elsif reply == 'walk'
      thea.walk
    elsif reply == 'put to bed'
      thea.puttobed
    elsif reply == 'pick up'
      thea.pickup
    elsif reply == 'code'
      thea.code
    elsif reply == 'play'
      thea.play
    else
      puts 'I\'m sorry, but that is beyond virtual Thea\'s capabilities.'
    end
  end
end
```


I love the concept of `while true`. I'm sure a lot could be written about just   that one concept but I'm tired and this kid behind me keeps hitting my seat  and crying. Has anyone ever been on a flight without any kids? I feel as if that  is as rare as finding a wild unicorn.
Anyways I used this loop here in order to keep the program continuing until it   terminates on its own either because the virtual cat becomes too hungry or too   peevish. My cat can become a monster when she is cranky and peeved by us   humans messing with her, so I decided that the program would end if she became   too upset with the human interacting with her. No one likes a grumpy, cranky   cat, unless of course you're the owner of Grumpy Cat and you're making it rain   from all the royalties.
One thing that I really enjoy about this loop is it's incredibly simple and   that you can keep piling on the `elsif`. Truly, as many as you want. As long   as the `if` gets a counter `else` and you put the correct number of `ends` all   is good in the computer world.


The link to my full code can be found [here on github](https://github.com/dukeran/thea)! I'll also write a post   about how I got github to work for me, since it's not user friendly to those  who are new to the tech world.


```ruby
puts 'Congratulations! A baby Thea has been born! You can do a lot of cool
  things with this interactive, virtual Thea while you\'re away. You need to
  take good care of her and make sure she goes to the bathroom and eats well.

  Here are some of the things you can do with Thea:
    1. feed
    2. walk
    3. put to bed
    4. pick up
    5. play
    6. code - you can even practice your coding while she\'s around!'
puts nil
puts 'What would you like to do with Thea?'

```


P.S. I would like to note that I am going to miss my family more than
my cat but it felt weird writing a code in which I fed my sister and
would have to take her to go to the bathroom. <3 you Lanjing!