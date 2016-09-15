---
layout: page
title: "An Interesting Question Posed With Compilers In Mind"
subheadline: "Teach Yourself C"
teaser: "Yesterday I was talking to a friend about C and compilers. In Ruby, the need to compile a code is unheard of and the concept was completely foreign to me with C - once again reminding me why I am learning C in the first place. There is so much I am learning from C that I would never have learned from Ruby! And as much as it pains me to say it, learning Ruby first has some disadvantages. For one, Ruby *does* compile your code, it just does it behind the poorly lit alley so that no one can see it. Much of Ruby is done behind the scenes so you don't have to worry your pretty little programmer head about it - which makes it incredibly convenient but also misleading."
categories:

tags:
    - design
    - background color
    - header
header:
    title: header with text
    background-color: "#EFC94C;"
#    pattern: pattern_concrete.jpg
    image_fullwidth: unsplash_brooklyn-bridge_header.jpg
    caption: This is a caption for the header image with link
    caption_url: https://unsplash.com/
categories:
    - code
---

Even though I have almost finished chapter two of "Teach Yourself C", I have yet to run a C program (shameful I know!). The book is a grammar book - not one to help you set up all the programs involved with running C code. Fair enough. I phoned a friend for help, the biggest confusion was this compiler nonesense. I use Sublime and homebrew, so I assumed that if I just switched the Sublime language from Ruby to C, and run `$ C filename.c` that it'll all come out swimmingly! Right? Wrong.

So I learned that the compiling process is as follows (2016 version, assuming you already have homebrew installed);

`$ brew install gcc48`

```
==> Installing gcc48 from homebrew/versions
==> Installing dependencies for homebrew/versions/gcc48: gmp4, mpfr2, libmpc08, isl011, cloog018
==> Installing homebrew/versions/gcc48 dependency: gmp4
...
==> Installing homebrew/versions/gcc48 dependency: mpfr2
==> Downloading https://homebrew.bintray.com/bottles-versions/mpfr2-2.4.2.yosemite.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring mpfr2-2.4.2.yosemite.bottle.1.tar.gz

...
==> Installing homebrew/versions/gcc48 dependency: libmpc08
==> Downloading https://homebrew.bintray.com/bottles-versions/libmpc08-0.8.1.yosemite.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring libmpc08-0.8.1.yosemite.bottle.1.tar.gz
...
==> Installing homebrew/versions/gcc48 dependency: isl011
==> Downloading https://homebrew.bintray.com/bottles-versions/isl011-0.11.1.yosemite.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring isl011-0.11.1.yosemite.bottle.1.tar.gz
...
==> Installing homebrew/versions/gcc48 dependency: cloog018
==> Downloading https://homebrew.bintray.com/bottles-versions/cloog018-0.18.0.yosemite.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring cloog018-0.18.0.yosemite.bottle.1.tar.gz
...
==> Installing homebrew/versions/gcc48
==> Downloading https://homebrew.bintray.com/bottles-versions/gcc48-4.8.5.yosemite.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring gcc48-4.8.5.yosemite.bottle.1.tar.gz
```

Now that gcc is installed, I learned how to run the compiler process. First I make a C program with Sublime and let's call that program `filename.c` ;

`$ gcc filename.c -o filename`

The `-o` means 'output', so in essence I am calling gcc ( the compiler ) to take it's initial argument ( filename.c ) and make it into machine language which I have decided to name `filename`. This `filename` file - note that it is a new file that I have named the same as the original C file but without the .c because it is no longer an actual C file - is then the file that I run on my computer. To run the new and improved machine langauge file I type in;

`$ ./filename `

And tada! I am ready to start writing C programs!







