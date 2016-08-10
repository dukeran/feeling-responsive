---
layout: page
subheadline: Templates
title:  "Upcoming Trip to South America"
teaser: "I am counting down the days until I board my flight to the captial of Peru!! I wrote a small program that will display my statement of purpose, my itinerary, and how many more days I have left until my return flight. Since Archer is one of my favorite TV shows, I often run my programs under the name of Woodhouse and he is incredibly helpful. In this blog post I've linked my incredibly simple program to github so you guys can take a look!
The beginning was easy. I tried to use a little bit of everything I've learned in the first ten chapters of _Learn to Code_ by Chris Pine."

breadcrumb: true
categories:
    - code
tags:
    - traveling-code
    - code

image:
    title: gallery-example-1.jpg
    caption: Unsplash.com
    caption_url: http://unsplash.com
author: mo
---


I used my first array:

```ruby
options = [['Statement of Purpose'],
           		['Itinerary'           ],
           		['Days Left '       ]]
```
<!--more-->

I have to admit, I'm still a little confused on what exactly an array is. Chris Pine usually does an excellent job explaining things so I'm not sure if I'm just unusually thick or if array's are actually a hard concept for a newbie to understand right away.

After doing a little research, it seems to me that an array is listing of objects which all share a common element. The computer is able to see them as individual units but also as a singular group unit which is valuable when you're dealing with a large amount of objects. EXAMPLE two different groups of objects and the comp has to deal with them in seperate ways.

Here comes Woodhouse!!

```ruby
puts 'Hello Miss, my name is Woodhouse and I am here to help you with your trip.
Please choose from the following options'
puts nil
op_num = 1
options.each do |op|
    name = op[0]
    beginning = op_num.to_s + '. ' + name
puts beginning.ljust(30)
op_num = op_num + 1
end
puts nil
def ask question
    puts question
    reply = gets.chomp.downcase
    if reply == 'statement of purpose'
            STATEMENT OF PURPOSE
        elsif reply == 'itinerary'
        puts 'long list of itinerary'
        elsif reply == 'days left'
        puts 't-lift off'
    else
        puts nil
        puts 'Miss, please refer to the options above and choose one of the following.'
        ask question
    end
end
puts nil
ask 'Miss, which would you like to know about?'
```

I love the `def` function, which is just short for 'define'. IF there is one thing I'm certain about, is that programmers will find the laziest way to type/do everything. As James explained it to me, the define function is like creating a written contract with your computer. You tell it that under these circumstances I want you to do the following... And you explain in detail exactly how you want it to behave. I love it! It allows for so much creativity. So the `def` alerts the computer/program that you're are about to give it its contract. The `ask` is the actual command that you define and will use in the future, while `question` is the variable that you'll define after the contract is written. In the code I wrote above, the `'Miss, which would you like to know about?'` is how I decided to define the varibale `question`.

Another thing that I would like to point out to other newbie coders of Ruby is that `elsif` is a subset of the `if` function, and that `else` is the counterpart to the `if`. You can fit as many `elsif`s as you want under `if` but you can't keep piling on the `else`s after the `if`. One `if` and one `else` within a loop. I learned that after much frustration.

The second part of the code is the following:

```ruby
puts 'Would you like to know about anything else?'
replytwo = gets.chomp.downcase
    if replytwo == 'yes'
        ask 'Miss, which would you like to know about?'
    elsif replytwo == 'no'
        puts nil
        puts 'Very well Miss, have a good day.'
        puts nil
    else
        puts nil
        puts 'Please choose one of the options mentioned above.'
        ask 'Miss, which would you like to know about?'
end
```

This was actually the hardest part of the code. I spent more time on this part than I should have because I kept crashing my computer. I made the mistake of putting in

```ruby
while
        true
    if reply == 'yes' ...etc
    ```

Which made my computer have a panic attack as it tried to compute the huge motherload of tasks I had just given it. To repeat the loop infinatum. Impossible, so my computer took the easy way out and committed suicide every time. Poor thing. I just removed the `while true` and it fixed everything.


