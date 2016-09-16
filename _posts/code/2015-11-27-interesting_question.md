---
layout: page
subheadline: "Teach Yourself C"
title:  "Interesting Question About Compilers"
teaser: "As a segue from the previous post, an interesting question was posed while discussing compilers with my friend. The premise is that the C book I am using is damn near ancient in the tech world - 1997. C is timeless but the equipment that deals with C is not. Compilers have evolved quite dramatically over the 19 years since publication and so some of the details and explanations that Schildt give about compilers is outdated to say the least."
categories:
    - code
tags:
    - code
image:
title: unsplash_eagle.jpg
caption_url: https://unsplash.com/

---


There is one paragraph on page 45 which states, "Because of the way a C compiler generates code, the *else* requires far fewer machine instructions than an additional *if* and is, therefore, more efficient".

In other words;

```c
if (choice ==1) printf("%f", num / 3.28);
if (choice ==2) printf("%f", num * 3.28);
...
```
takes the compiler a lot longer to compile into machine instructions than the following;

```c
if (num2 == 0) printf("Cannot divide by zero.");
else printf("Answer is: %d.", num1 / num2);
...
```
However, that was over 15 years ago. The question that was posed and that I will somehow find out is;

If i were to write two *if* statements that were the exact opposite of each other, would the compiler be able to optimize the machine code and change the two *if*s to a logical *if*/*else* statement?

