---
layout: page-fullwidth
title:  ".Compact Verse .Reject"
teaser: "While working on a parser at my intern develop job, I came across the following code written by someone else that I asked my boss about. My boss pointed out that the first line doesn't actually mean anything and that the second line has some redundancy. In this following post, I am going to outline our general discussion, Socrates and Plato style."
categories:
    - code
header:
   image_fullwidth: header_unsplash_leaf.jpg
---


```ruby
def lecture_time_formatter(string)
	string.split(/\n/).join(",")
	string.split(/\n/).compact.reject(&:blank?).uniq.join(",")
end
```

*Me*	Is the `string.split(/\n/)` defining what is there or is it a function?

*James*		`.split` is a function, while `string` is a string object. `.split` is a method defined on **strings** that then takes a single argument, the substring to split on. Splitting strings will return an array of substrings, split by the character defined in the argument.

For example:

"Hello there Kerrie!".split(" ") # => ["Hello", "there", "Kerrie!"]

(`# =>` reads as "will return" or 'returns')


`.compact` is a method that's defined on arrays (and other things too, but in this case we care about arrays) and `.compact` returns the array without nils

e.g. ["hello", nil, nil, "there", nil, "kerrie"].compact # => ["hello", "there", "kerrie"]

`.reject` is a method defined on arrays that we've talked about (it's like the reverse of `select`)

only thing worth noting is that `reject(&:blank?)` is syntactic sugar (i.e. a more convenient way of writing) `reject{|x| x.blank? }`

`.uniq` is a method defined on arrays that we've never talked about but as you can imagine, returns a subset of the array that it's called on with 1 of each unique element

e.g. [1, 2, 3, 4, 5, 5, 5, 5, 5, 5, 6, 6, 7].uniq # => [1, 2, 3, 4, 5, 6, 7]

And, finally `.join` is a method that takes an array of things, calls `.to_s` on each to turn them into a string if they aren't a string, and then connects them with the argument

For example: ["My", "age", "is", 20.3].join(" ") # => "My age is 20.3"

or

["My", "age", "is", 20.3].join(" LOL ") # => "My LOL age LOL is LOL 20.3"

*Me* 	That makes sense

*James* 	So, the original two lines you gave me basically state that you take a string, split into lines, get rid of any nils, get rid of any blanks, get rid of duplicates, and then join them with commas.

There's a subtlety to why there's `.compact.reject(&:blank)` is that `split` will have a nil if there's two dilineators in a row. `compact.reject(&:blank?)` is actually redundant and could just be `.reject(&:blank?)`

That is: `string.split(/\n/).compact.reject(&:blank?).uniq.join(",")` is exactly the same as `string.split(/\n/).reject(&:blank?).uniq.join(",")`

Ok, quiz time, why are they equivalent?

*Me* 	Because compacting and rejecting will do the same thing won’t it? Compacting is getting rid of the ‘spaces’ to make it a pretty string while rejecting is getting rid of the ‘Nils' ... but the nils = spaces

*James* 	You're on the right track but I want you to state something specific about the return values of a certain function in order for me to know you fully understand it.

Note that:

`["a", "", "b", "", "c"].compact # => ["a", "", "b", "", "c"]`

*Me*	 So if you wrote `string.split(/\n/).compact.uniq.join(“,”) you’d return an array with empty strings in it

*James* 	Correct, well it's actually even more interesting than that now that I think about it.

*Me* 	So, then what exactly does compact do?

*James* 	`.compact` removes `nils`
`["a", "", nil].compact # => ["a", ""]`

*Me* 	So a `" "` isn’t actually nil?

*James* 	Correct. Actually for that matter:

`array.compact.reject(&:blank?)` is the same as `array.reject(&:blank?)`

*Me* 	There is something special about a subset of the bigger part of what we wanted to remove from the main set

*James* 	Yes. Bingo. `.compact` is the same as `.reject{|x| x == nil}`

*Me* 	Got it, and then `.reject` will reject whatever you define but `.reject` can’t take zero arguments

*James* 	so we can restate what we're saying as:

`.reject{|x| x == nil}.reject{|x| x.blank?}` is the same as `.reject{|x| x.blank?}`

*Me* 	so reject has to take at least one argument

*James* 	"Reject requires at least one argument" is an accurate statement

*Me*	 While compact doesn’t require an argument because its argument is inferred within the method.

*James* 	That's not a statement that I can't evaluate the correctness of because it doesn't fit the jargon of this field, but I don't think it's dangerous for you to think it.

So why is `.reject{|x| x == nil}.reject{|x| x.blank?}` is the same as `.reject{|x| x.blank?}`

*Me* 	For some reason i’m hesitating in saying that it is because if x == blank than x == nil

*James* 	You're so close `blank` is not an object `x == blank` is not meaningful

*Me* 	Is there a connection between an emptry string and the nil value?

*James* 	Only in passing, there is a method, defined both on `""` and on `nil`, that returns the same value when called on both, that is the way in which they are related.
(not, but `" "` is not "the empty string", only `""` is)

*Me*	 In some way, `.reject{|x| x.blank?}` includes `.reject{|x| x == nil}` in its set

*James* 	Yes, that is correct, buy *why*

*Me* 	`.blank?` returns the same value on an empty string and nil

*James* 	YES!

* 	*	*

In other words, to sum everything up in a programmer's jargon;

Here's how I would describe it, for the jargon:

`array.compact.reject(&:blank?)` is the same as `array.reject(&:blank?)` because, since `nil.blank?` returns true, any element of `array` that's removed by `compact` would also be removed by `.reject(&:blank?)`

In my more familiar math jargon:

`array.compact.reject(&:blank?)` is equivalent to `array.reject(&:blank?)` because the set of elements that are identified for removal by `compact` is a subset of the set of elements that are identified for removal by `.reject(&:blank?)` as `compact` only removes `nil` and `nil.blank? == true`

You can see how the first one is describing it in terms of actions - things that are removed would've already been removed and the second is describing it in terms of relationships between return value sets but they're both accurate and true.




