---
layout: page-fullwidth
title: "Variables"
subheadline: "Kata Wars"
teaser: "Working on Kata every morning with your coffee is good for the soul. After going through three tutorial books on Ruby, Sinatra, and Ruby on Rails (one each respectively) I still struggled with my first kata from Code Wars."
header:
    image: homepage_typography.jpg
    background-color: "#262930"
    caption: This is a caption for the header image with link
    caption_url: https://unsplash.com/
image:
    thumb:  homepage_typography-thumb.jpg
    homepage: homepage_typography.jpg
    caption: Image by Antonio
    caption_url: "http://www.aisleone.net/"
categories:
    - code
---
###Hardcore Parcour

The name of the kata is Stringy Strings and it has very straightforward instructions;

>write me a function stringy that takes a size and returns a string of alternating '1s' and '0s'.

>the string should start with a 1.

>a string with size 6 should return :'101010'.

>with size 4 should return : '1010'.

>with size 12 should return : '101010101010'.

>The size will always be positive and will only use whole numbers



I have to admit, I was at quite a loss - a feeling that was incredibly frustrating.

<!--more-->

You're given the following:

def stringy(size)
 (insert your code here)
end

I first thought about how to approach the problem in the most simple way possible. How could I break it down so that the string starting at one?

my first thought was to start at: '''base = "1"''' and go from there. I recalled the first method I internalized;

(1..size).each do |number|

because size is within the parenthesis, Ruby knows that size is going to be a variable for a number. The "number" put into "| |" symbolism is giving a variable name to what is inside the parenthesis.
I figured that for every other number I would want a "1" and then a "0" so with this dichotomy I figured I could equate it to even and odds. For every odd I would assign a "1" value and for every even I would assign a "0" value. Mind you, I was writing anything that came to mind and erasing and cleaning up things as I went. At this point I removed the base = "1" since I would be no longer needing it if my array started at 1 and I could assign a "1" on the 1 value.

after running a few tests, I came up with the following:

```ruby
def stringy(size)
  (1..size).each do |number|
  if number.odd?
    puts "1"
  else
    puts "0"
  end
  end
end
puts stringy(5)
````

This did not work quite how I wanted it to:

```ruby
1
0
1
0
1
1...5
```

First of all, what was with the `1..5`? I was confused and so I asked a friend. Ruby, when not given a specific task, will regurgitate as much as she can, trying to give you as much information as possible unless specified otherwise. Since nothing was specified between the end of the `if`, `else` and the `end` of the defining method, then ruby told you the parameters of what she did was between 1 and 5, hence the 1..5. Another thing to note is that Ruby gave us the 1's and 0's we were looking for, but not in a consecutive line. It turns out that ruby will print out each variable on its own line unless specifically told not to.

The next round I specifically told ruby to print the variables on the same line:

```ruby
def stringy(size)
  string = ''
  size.times do |number|
    if number.even?
      string = string + '1'
    else
      string = string + '0'
    end
  end
  string
end
```

Also, what is significant about this code compared to the last code I tried is that in the first code I applied a function to the range and in the second code I used a method and applied it to a variable. For example in the first code `(1..size).each do |number|` the `.each` applies to the inclusive range, applying the function to each number in the range.
In the second code in the third line `size.times do |n|`, the `.times`  function means that the method will perform that function as many times as you specify in the `n` variable.
In this case, there isn't much difference between the two except that `.times` can be applied to a stand-alone variable while `.each` _has to_ apply to more than one variable. It is perfectly acceptable to write `  (1..size).each do |number|` in the second code on line 3 in place of what is there.


A few other solutions were:

```ruby
def stringy(size)
  (1..size).map { |number| number.even? ? '0' : '1' }.join('')
end
```

In this case I learned something knew. I hadn't seen the `.map` function before. `.map` applies a function onto every single member of that range. The curly brackets are a shorthand for `do`/`end`, allowing the entire method to be on one line, shortening the code. The `?` is calling up the Boolean method (see previous post) and the `:` act as an OR method.




