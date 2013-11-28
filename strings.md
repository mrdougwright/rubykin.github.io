---
layout: default
title: Strings
weight: 3
---

In Ruby, we can also perform some math-like operations using our friends, the strings. For example, we can multiply a string like so:

```ruby
"repeat " * 3 
=> "repeat repeat repeat "
```

In the above example we have a string: `"repeat "` that we multiply ` * ` by three. Remember, the string is anything between the quotes. This is how the computer knows its a string (not a number). When it performs the ` * 3 ` method it actually just copies the string three times and pastes the result together. Sort of like this:

```ruby
"repeat " + "repeat " + "repeat "
=> "repeat repeat repeat "
``` 

In fact, you can write either of these lines of code and the result will be the same. Much in the same way that writing ` 3 + 3 + 3 = 9 ` yields the same result as ` 3 * 3 = 9 `. When the computer adds strings together we call it concatenation.

```ruby
"Cat and " + "Dog"
=> "Cat and Dog"
```

In the example above, there are two strings, one is `"Cat and"` and the second string is `"Dog"`. By giving the command to add the two strings, we are able to join both strings together using the magic of concatenation. (Concatenation is just a fancy old Latin word for join together, or chain together...Kind of like you chain your bike to the bike racks.)

Ready to try it out? 

Now, open Terminal again (or <a href="http://repl.it/languages/Ruby" target="_blank">Repl.it</a>) and try multiplying and adding a few strings yourself to get the hang of it.

Now try adding a number with a string. It didn’t work did it? Remember that joker `"9"` string from our previous example in [chapter 1](/what-is-programming.html)? Ruby doesn’t see this as the actual number 9. Instead it sees a string because, to Ruby, anything that is inside the quote isn’t just a word or a number anymore, everything inside the quotes is a string. That's why when we try to add a string with a number, Ruby gives us an error:

```
"9" + 9
=> TypeError: can't convert Fixnum into String
```

In the above example, we would see `"9" + 9` and think the answer is 18. But for Ruby, she doesn’t see it like that, for Ruby she sees `"STRING" + 9`.

This doesn’t mean we can’t do this sort of equation, it just means we need to use a trick to make sure Ruby understands what we want. Of course, there are lots of interesting methods or _actions_ we can perform to get Ruby to do what we want. One of the most fun parts about learning to use programming languages like Ruby, is being able to figure out all the different ways to communicate with the computer to get things we want! We’ll look at some of those _actions_ more a bit later, but for now, you could solve the above problem by using the _to integer_ method, or `to_i`, which simply converts a string to an integer:

```ruby
"9".to_i + 9
=> 18
```

When you want Ruby to add a number to a string, just type the string and then `.to_i + ` followed by a number and Ruby will give you the correct answer.

Remember those ` \n ` characters from the first chapter? This is what the computer uses to note a _new line_ in your string. So the following string:

```ruby
print "One line.\nAnother line.\nAnd another.\n"
```
Would print like this:

```
One line.
Another line.
And another.
```
In this way, Ruby can store sentences or even whole files inside just one string. Now that you have a better understanding of strings, check out some examples below.

<br />
__Practice__

What is the result of each of the following?

```ruby
1) puts "What is the result" + " of " + "this operation?"

2) "This string minus" - "That string"

3) "1234.55".to_i

4) "1234.55".to_f

5) "Not a number".to_i

6) puts "1\n2\n3\n"
```

```
6) Why might it be useful that the _to integer_ (to_i) method return zero on
strings that can’t be represented as numbers?

7) What do you think the length method does? 
"Count".length

8) How about the split method?
"Count".split("")

9) What do you think slice does?
"Count".slice(2)
```

Want to see more cool String methods? Just call _methods_ on the String class! Type this into IRB:

`IRB$ String.methods`

```ruby
# some of the built-in Ruby methods for String
[:try_convert, :allocate, :new, :superclass, :freeze, :===, :==, :<=>, 
:<, :<=, :>, :>=, :to_s, :included_modules, :include?, :name, :ancestors, 
:instance_methods, :public_instance_methods, :protected_instance_methods, 
:private_instance_methods, :constants, :const_get, :const_set ...
```
