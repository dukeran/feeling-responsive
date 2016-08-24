2015-11-22-beginning-C.md

layout: page
subheadline: "Teach Yourself C"
title: "Review of the Preface"
teaser: "Today I have started reading through the 'Teach Yourself C' Third Edition by Herbert Schildt to gain a depper understanding of how programming works. Since Ruby is a 'high-level language' I am missing a lot of the fundamentals of how and why the program executes the way it does. As Herbert Schildt wrote in his preface page x, 'a high-level language buffers the programmer from the computer. A high-level languagee typically supplies various control structures, input and output commands, and hte like, which make programming easier and faster. However, the elements of a high-level langauge may not relate directely to the way that the computer ultimately carries out the program. This separation often causes programs written using a high-level language to be less efficient than those written in assembly language.'' I have to admit, I have definitely noticed that I write much less efficient code than others and this isn't only because I am new to programming - no, not understanding how things such as arrays and hashes organize themselves in assembly langauge are a much bigger factor. So, like an overly curious zealot, I've decided to go through and read every textbook within reach to remedy the situation, starting with 'Teach Yourself C', a middle-level language book!
header:
    image_fullwidth: "header_typewriter.jpg"
    caption: Image by Florian Klauer
    caption_url: "http://florianklauer.de/"
image:
    thumb:  typewriter-thumb.jpg
    homepage: homepage_typewriter.jpg
categories:
    - code
comments: true
show_meta: false
---



As I read through the book, at any point where I have a question, or where I don't fully understand the concept, I write a note or a small question on the margins of the pages. I mark these pages and at the end of the chapter I either reserach the question or find someone who can answer it, then I go back to the margins and write the answer. Each question I have, I will try to address here and hopefully if my understanding is wrong, someone could correct me!

First question that I had was, what is the difference between C and C++. The preface makes a few good points, saying that C++ is a language that is an extension of C, so that every compiler/text-editor that uses C++ can use C, but not necessarily the other way around. C++ is basically a superset of C, and that C++ has more capabilities. C++, unlike C, C++ is an object-oriented programming language (OOP) which makes it more versatile for different things. My main question was, if C++ is an OOP language, then what would C be classified as? Unfortunately, the answer was not as satisfying as I'd like, my friend told me that C is considered a non-OOP langauge, which is all great and everything unless you consider that OOP came after non-OOP languages so therefore the name is more of an afterthought. The second best answer was that C is a 'procedural language' which is slightly more comforting.

My next question was about the differences between 16 bit, 32 bit, and 64 bit environments?
The 32 bit vs 16 bit vs 64 bit is the number of bits that are in one 'word' in the processor (aka the assembly language). A 16 bit computer can only do math with numbers up top 2^16 in one step, which means that if the number is bigger than 2^16 it would take more than one step, increasing the time it would take to perform the function, and it can only address up to 2^16 words of memory -> 64kb of memory, which, if the file is saved in an area that is bigger than 64kb of memory, it would also take longer to access. As computers became more advanced/able to store more information, it was important to increase the speed at which the processor was able to access data. So 16 bit went on to 32 bit, with a 32 bit computer being able to do math with numbers up to 2^32 in one step, which means it can address up to 2^32 of memory which is equivalent to 4GB of memory. Intel stopped selling 32 bit chips around 2006, now almost all computers use the 64 bit environment. 64 bit computers can do....you guessed it! 2^64 computations in one step. That equals a stupidly large number of memory, somewhere around 18 petabytes.

Speaking of kb, mg, and petabytes, I think my next blog post will be about what the differences between these large numbers are and what they actually mean for computing.

Cheers!



