---
layout: page
subheadline: "Drake"
title: "Databases"
teaser: "Today I added some information into the seeds.rb file and ran ` $ bin/rails db:seed ` and then `$ ran bin/rails s`. To my horror, all the information that I had had was gone! No errors showed up on local host and I felt at a loss since my understanding of databases is so limited. Thankfully with the help of my co-worker, we figured out a solution."
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

Here's what I learned:

If an error occurs with `$ bin/rails db:seed`, the error can be silent and not appear either on your console or on local host. It's almost like asking Rails what's wrong and she replies wistfully - nothing - but you know something is wrong. So you go ask Ruby by going into the Rails console and start running some tests;


`$ rails c`

`$ Book.all`
<br>
 `...Book Load (0.2ms)  SELECT "books".* FROM "books"
 => #<ActiveRecord::Relation []>`

<!--more-->

 Nothing there, at least that tells me that something is wrong, we just don't know what yet.

 Here's where we create a book on the console to be able to see what and where things go wrong;

`$ Book.create!(title: 'WinniePoo', description: %{<p> hello </p>}, image_url: 'lol.jpg', review: 5.0)`

(use bang method to throw an error, otherwise it'll fail silently once again) Bang method usually has a destructive side effect when running with a command. Bang is like the antithesis of the command. It is a powerful method that I just learned today! Bang method is unique to the function. (fix this)

>ActiveRecord::RecordInvalid: Validation failed: Image url must be a URL for GIF, JPG or PNG image.
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/validations.rb:78:in `raise_validation_error'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/validations.rb:50:in `save!'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/attribute_methods/dirty.rb:30:in `save!'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/transactions.rb:324:in `block in save!'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/transactions.rb:395:in `block in with_transaction_returning_status'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/connection_adapters/abstract/database_statements.rb:232:in `block in transaction'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/connection_adapters/abstract/transaction.rb:189:in `within_new_transaction'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/connection_adapters/abstract/database_statements.rb:232:in `transaction'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/transactions.rb:211:in `transaction'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/transactions.rb:392:in `with_transaction_returning_status'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/transactions.rb:324:in `save!'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/suppressor.rb:45:in `save!'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/activerecord-5.0.0.rc1/lib/active_record/persistence.rb:51:in `create!'
>	from (irb):6
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/railties-5.0.0.rc1/lib/rails/commands/console.rb:65:in `start'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/railties-5.0.0.rc1/lib/rails/commands/console_helper.rb:9:in `start'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/railties-5.0.0.rc1/lib/rails/commands/commands_tasks.rb:78:in `console'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/railties-5.0.0.rc1/lib/rails/commands/commands_tasks.rb:49:in `run_command!'
>	from /Users/quottly/.rvm/gems/ruby-2.3.1/gems/railties-5.0.0.rc1/lib/rails/commands.rb:18:in `<top (required)>'
>	from bin/rails:4:in `require'
>	from bin/rails:4:in `<main>'

Here it is! List of errors. Now we can get started on problem solving.

We went into the app/models/book.rb and I just completely removed the

```ruby
	validates :image_url, allow_blank: true, format: {
		with: %r{\ .(gif\ jpg\ png)\ Z}i,
		message: 'must be a URL for GIF, JPG or PNG image.'
	}
```

Since it has been causing me errors since the beginning. I ran `$ Book.create!...` again, and this time-success!

I was able to `$ bin/rails db:seed` and my page is showing the books and data once again :D

Every day I am reminded of how much I still have to learn.