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

If *if* is true, if will execute and the *else* portion will be skipped. If the *if* is false, then it will be bypassed and the *else* will execute instead. This is a two-way decision path and both cannot be true at the same time. (Exclusive OR operator)

Note: the *else* is always associated with the nearest *if* in the same block.

* for loop *

The *for* is super flexible and doesn't place a limit on the types of expressions that occur inside of it. There are three parts to the expression in a *for* loop; **initialization, conditional-test, and increment**. The **increment** portion is the expression that is evaluated each and every time the loop iterates.

Note: when there is no expression in the conditional portion of the *for*, the compiler assumes that the condition is true, and the loop will run continuously.


* while loop *

The *while* loop will continue to loop for as long as the expression is true;

~~~
while(expression) statement;
~~~

If the expression is false, nothing inside the while loop will run.

* do loop *

~~~
do {
	statements
} while(expression)
~~~

The curly brackets are not mandatory if only one statement is being repeated, but it is good practice to always include them in a * do loop*. Like the *while*, the *do* repeats itself while the expression is true and only stops once the expression is false. What makes the *do loop* different, however, is that it will ALWAYS execute the code within the loop at least once, since the machine doesn't analyze the truth value of the expression until after the block of code.

It is important to remember that any of C's loops may be nested with another loop!

