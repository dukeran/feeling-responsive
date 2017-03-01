---
layout: page
subheadline:  "Experiences Interning"
title:  "Making Mistakes"
teaser: "Today, I learned about databases and migrations. It seems like such a big thing for many intro books to gloss over but gloss over it they do. And there might be good reason to, it's complicated stuff! Even now as I type this I am not quite sure what databases are or how migrations work. However, I do know that naming conventions with Ruby is a tricky business and I learned that lesson the hard way today."
categories:
    - code
tags:

header: no
---


Working on MobiDick, I decided to create a personal bookshelf which I decided to name 'Pershelf', a nice, easy, and explanatory name (or so I thought). I ran

`$ bin/rails generate scaffold Pershelf`

`$ bin/rails db: migrate`

Everything so far okay. I modified the app/controllers/concerns/current_pershelf.rb folder and continued to the next step;

`$ bin/rails generate scaffold LineItem book:references pershelve:belongs_to`


`$ bin/rails db:migrate`

<!--more-->

Aaanddd now the problems begin. I spent a few hours going through test trying to figure out what went wrong, over and over again finding myself with an 'Undefined variable' error. I saw that some files were labeled 'pershelve' and immediately assumed that Ruby had incorrectly tried to pluralize then put the noun into singular form and messed up miserably so I went through all the files trying to rename everything to 'pershelf' and then would put the plural as 'pershelfs'. That definitely did not work. It wasn't until a co-worker of mine told me to look at the /db/schema.rb to take a look at how the database was set up. There it was! There error was as bright as day.

I would never have thought to look at the database and once we realized that it was clearly human error that caused the issues, my co-worker walked me through the steps of fixing the error;


<div id="container">
<center><img src="http://i.imgur.com/s5e11uw.png"" height="600" width="600" style="margin:20px 20px">
</center>
<p>
</p>
</div>


I learned four important lessons today;

Ruby can, in fact, pluralize like a pro (I would love to see how ruby learned to do it so well!)

Maybe coding while sick and with fever is not the best way to code

Keep track of your spelling conventions!

I learned how to fix errors in the database!


pluralization of ruby in rails when generating scaffolding

When you use rails to build scaffolding, it will expect certain conventions