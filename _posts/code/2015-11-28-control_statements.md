---
layout: page-fullwidth
subheadline: "Teach Yourself C"
title:  "Control Statements"
teaser: "Just finished reading the third chapter of 'Teach Yourself C' and it was interesting. Titled, 'More C Program Control Statements', many of it was very similar to what I have read in other Ruby programming books. However, there were some dissemiliarites that could potentially trip me up if I am switching between Ruby and C. This post is designed to give me (and hopefully others) a rundown and distillation of the control statements found in chapter three."
categories:
    - code
header:
   image_fullwidth: header_unsplash_leaf.jpg
---


* if / else statements *

~~~
if (num < 0) printf ("Number is negative.");
else printf("Number is non-negative.");
~~~

If *if* is true, if will execute and the *else* portion will be skipped. If the *if* is false, then it will be byepassed and the *else* will execute instead. This is a two way decision path and both cannot be true at the same time. (Exclusive OR operator)

Note: the *else* is always associated with the nearest *if* in the same block.

* for loop *

The *for* is super flexible and doesn't place a limit on the types of expressions that occur inside of it. There are three parts to the expression in a *for* loop; **initialization, conditional-test, and increment**. The **increment** portion is the expression that is evaluated each and everytime the loop iterates.

