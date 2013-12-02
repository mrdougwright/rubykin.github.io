---
layout: default
title: Collections
weight: 7
description: Collections are basically lists, written as either hashes or arrays in computer programming.
---

In order to store data, we use collections. There are two types of ways we store our data collections. One is called an Array, the other is called a Hash. You can think about a collection of data like a trunk of toys. Let’s start with the Array _toy chest_ first.

<br />
__Arrays__

Arrays are ordered, indexed collections of data that can have various types. An ordered collection means that it is "in order". When you line up with your classmates at school in a lunch line, you are a collection of kids in an ordered line. Arrays are kind of like that. You can order the line of kids in many different ways. You could order from tallest to shortest. You could line up in oldest to youngest, or you could line up in shortest hair to longest hair, no matter which way you lined up the kids in the line, you’d still be in order and you’d still be in an Array.

Let’s say there was a line of kids: Adam, Billy, Molly and Sally. This line of kids is in alphabetical order, with Adam in front, followed by Billy, Molly and Sally. That means that Adam is number 1, Billy is number 2, Molly is number 3 and Sally is number 4. These are four kids in an ordered line. If we were to write this as an array, it would look like this:

```ruby
["Adam", "Billy", "Molly", "Sally"]
```
Arrays are noted using square brackets, with elements separated by a comma. So an array is in order, and it is also indexed. When a collection is indexed, it means that each item has a specific number that relates to its order in line. The tricky part to remember is that computers start their index at zero. This means that Adam’s index is 0, Billy is 1, Molly is 2 and Sally is 3.

Here’s what our array looks like with its index. Don’t worry, just because Adam’s index is zero, that doesn’t mean that our Wizard thinks he’s worthless. The Ruby Wizard loves everyone, except for Python. More on that in book 2.

```ruby
kids_array = ["Adam", "Billy", "Molly", "Sally"]
# kids_array index => [0,1,2,3]
```

If we want the first element in our ordered array, we look it up by the first index. The first index in any array is zero. We can find an element by its index using the `[ ]` method.

```ruby
kids_array[0]
=> "Adam"
```

You can think of the brackets like big monkey paws, they clamp down on both sides of the element (whatever the object) and hold it. If you type `kids_array[0]` you are asking Ruby to get the first spot. In this case, Ruby would tell you that Adam is at index zero.

We can also use the `[ ]` method to add or change an element in our array. For example, if Sally left to another school and Terry replaced her spot, we could remove Sally and replace her with Terry by using the `[ ]` method on the correct index number.

```ruby
kids_array = ["Adam", "Billy", "Molly", "Sally"]
kids_array[3] = "Terry"
kids_array
=> ["Adam", "Billy", "Molly", "Terry"]
```

We can even add a new member to our array, like so.

```ruby
kids_array[4] = "Zoe"
kids_array
=> ["Adam", "Billy", "Molly", "Terry", "Zoe"]
```

Arrays can contain numbers, strings and even other arrays!

```ruby
number_array = [1,2,3,4,5]
string_array = ["Frank", "Suzy", "Doug", "Jane"]
mixed_array = [number_array, "a string", 13]
```

If we had an array _inside_ another array, we can use the square brackets in a similar way to access our data. In the example below, in order to grab the number 2, we use square brackets to access the first element in our array (which is our 2nd array). We then use another bracket to access the number two.

```ruby
lots_of_arrays = [[1,2],"string","test"]
lots_of_arrays[0][1]
=> 2
```

Ruby gives us some cool methods to call on arrays, like `sort`. When we call the sort method on our string_array, Ruby sorts our array alphabetically. In Ruby, whenever we use the sort method, the computer understands we want to see the entire array alphabetized.

```ruby
string_array.sort
=> ["Doug", "Frank", "Jane", "Suzy"]
```

However, unless we call sort! on the array, the order will not change permanently and our array will stay in its original state. When we ask to sort without an exclamation mark, only the result is sorted (not the actual array). When we call `sort!` with the exclamation mark, the _actual_ array is sorted in the new alphabetized order.

```ruby
string_array
=> ["Frank", "Suzy", "Doug", "Jane"]

string_array.sort!
=> ["Doug", "Frank", "Jane", "Suzy"]
```

Before we get into more examples about arrays, it’s important to mention one of Ruby’s widely used array methods--the shovel. The shovel is written with two less-than symbols `<<` that are used to insert items to the end of an array. Let’s take the example above and add Bill to our string array.

```ruby
string_array
=> ["Doug", "Frank", "Jane", "Suzy"]
string_array << "Bill"
=> ["Doug", "Frank", "Jane", "Suzy", "Bill"]
```

We could have added Bill with the push method as well.

```ruby
string_array.push("Bill")
=> ["Doug", "Frank", "Jane", "Suzy", "Bill"]
```

The shovel method is favored by Rubyists and it’s good to know how it works. More examples on arrays below.

<br />
__Practice__


```
1) Put the following kids in an array. Joe, Sally, Tom, Mary, Doug. Now
sort them alphabetically using a standard Ruby method. What's the
resulting array?

2) With your kid_array from question 1, separate the boys and girls into
their own arrays. Then put your two new arrays into one array called
“group”. What is the least amount of lines required to write this code?

3) Now you should have one “group” array with two arrays nested inside.
How might we reverse the order of each array?
Hint: Ruby methods tend to be named by what they do.

4) Our class group has added one student, Tiffany. Add her to the girls
list in our group array. What does our array look like now?

5) Imagine our list of boys and girls is much larger than just three. If
each class can only have an equal number of boys and girls, how might a
teacher ensure her lists are equal? Hint: You can use the count method to
count the number of elements in an array.
```

<br />
__Hash__

The next type of collection in Ruby is the _Hash_. A hash is an unordered list of key value pairs. A hash is more like a messy room than an array, which is very organized. With a hash, our list of items come in pairs placed in any order. In these collections, we use curly brackets `{ }` wrapped around pairs of information separated by a comma, `{ “like” => “this” }`. The item to the left of the arrow `=>` is the _key_ and its _value_ is the element on the right.

Hashes are extremely useful when we have multiple numbers of similar items in a list. For example, if you used a hash to organize your toy chest, it might look something like this:

```ruby
toy_chest = {"sea_monkeys" => 12, "dolls" => 5, "legos" => 514}
```

Each of these items is located in our toy chest, and the number of them is represented in the hash. So we have three keys (sea_monkeys, dolls and legos) with their corresponding values (12, 5 and 514). To access information in this hash, we can use brackets like we did for arrays.

```ruby
toy_chest["sea_monkeys"]
=> 12

toy_chest["dolls"]
=> 5

toy_chest["legos"]
=> 514
```

To add an item to our toy chest hash, we can simply use brackets in a similar way that we did above to retrieve information.

```ruby
toy_chest["toy_cars"] = 7
=> 7

toy_chest
=> {"sea_monkeys" => 12, "dolls" => 5, "legos" => 514, "toy_cars" => 7}
```

By writing "toy_cars" in brackets next to toy_chest, we’ve actually called a method on our hash, giving it a new key value pair of `"toy_cars" => 7`. To remove an element, we can call the `delete` method. Don’t worry too much about methods right now, we just want to show you how easy it is to handle data in your array or hash collections.

```ruby
toy_chest.delete("sea_monkeys")
=> 12

toy_chest
=> {"dolls" => 5, "legos" => 514, "toy_cars" => 7}
```

There are several other ways to add, remove and manipulate data in our hash collection. But before we understand these methods, we need to learn about methods in general. Check out some examples of using a Hash below, and then, onward to the next chapter!

<br />
__Practice__

```
1) Create a hash for the Wizard’s magic bag. Inside the bag, we’ll put
3 frogs, 5 herbs, and 10 scrolls. Set the hash to the variable "bag".
What does your hash look like?

2) Remember, hashes consist of key value pairs of any data, not just
numbers. Let’s add a wizard’s spell and its result (which the wizard
can never seem to remember). Add a spell to our wizard’s bag with the
key: "shazam" and the value "turns subject into a frog". Now what's
in our bag?

3) Our wizard has a change of heart and decides he never wants to turn
anyone into a frog. How can we remove the spell "shazam" from our
wizard bag?

4) Our wizard has recently acquired 3 different types of potions.
3 orange potions, 5 blue potions and 7 red potions. How might we add
another hash of potions to our bag? Hint: remember that we can have
collections within a collection.

5) Now that our bag has four keys (frogs, herbs, scrolls and potions),
we can use these keys to access our data. In order to make a new spell,
our wizard needs 2 frogs, 3 herbs, 1 scroll and 2 blue potions. How can
we remove these items from our hash? Hint: We can set the value of a key
item to itself, minus how many items removed.
```