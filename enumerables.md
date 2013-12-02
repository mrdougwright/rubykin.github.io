---
layout: default
title: Enumerables
weight: 9
description: The Enumerable is a built-in Ruby module that allows you to iterate (go over) the elements in a collection. Here we review four of the basic enumerables.
---

The Enumerable module is a collection of built-in Ruby methods that allow you to scan, sort, search and manipulate collections. Remember that collections come in two forms, hashes and arrays. We’ll cover four of the basic enumerables in this chapter:

  * each
  * each\_with\_index
  * select
  * map

<br />
__Each__

You can think of the `each` method as one that operates a block, or a specific piece of code, onto each element in your collection. For example, if we had a collection of toys we might store these in an array. If we wanted to print each toy on the screen, we can call the each method. In the example below, we create the toys array with our collection of toys, then we call each specific toy individually.

```ruby
toys = ["car", "ball", "super hero action figure", "stuffed animal"]
toys.each { |toy| puts toy }
# Now each toy will be put to the screen:
 car
 ball
 super hero action figure
 stuffed animal
```

Let’s dig into the each method to see what we did. Since this method belongs to the Array class, we can call it on our toys array. We then give our `each` method a block of code to be executed or carried out and performed. In this case, we are using the `puts` method. In our `|pipes|` we define a temporary variable `toy` and call the puts method on each toy that is passed to our block.

Our each method knows to look at each element (our four toys) inside the array. This is called iterating over the array. (Iterating over the array is just a fancy way of saying look at each toy in the collection). Now we store the value of each array element inside our |pipes| and call the puts method on each element. We could have written the same code like so:

```ruby
toys.each do |toy|
  puts toy
end
```

The curly brackets are a way of writing `do` and `end` in one line. You don’t have to use them, but it is a shortcut that you can use if you want! Either way works, and Ruby will look to execute the code inside of our `do-end` or `{ }` block. Now, let’s look at how we might use the each method on a hash.

Imagine we had more than one toy in our collection. (If your parents are teaching you how to code in Ruby, you probably have a lot more than one toy in your collection. Lucky you!) We might use a hash to better represent or organize our toy box. Using each, we can print the toy and the number of toys in our collection.

```ruby
toys = {"car" => 1, "ball" => 3, "super hero action figure" => 2,
"stuffed animal" => 8}
toys.each { |key, value| puts "#{key}: #{value}" }
car: 1
ball: 3
super hero action figure: 2
stuffed animal: 8
```

When using the each method on a hash, Ruby knows that each element in the array has a key and a value. We could have used anything in our |pipes| to name our key and value pairs ( such as |x, y| ), but it’s easier to read when we identify our key and value by their names. We then call the puts method again on each element, use our friend interpolation ( the #{ } ) to place our variable values in our string, and finally put the string of the toy, and number of toys, to the screen.

<br />
__Each\_with\_index__

This enumerable method works much like each, except that it captures the index of the specific array its called on as well. Remember that an array is an ordered collection that uses an index (sorting system) to organize the data or information in the array. An array with five items has five indexes, from 0 to 4, and each index notes the location of each element.

```ruby
my_array = ['ball', 'bat', 'hat']
my_array[2]
=> hat

my_array[0]
=> ball
```

In the example above, each item in the my_array can be called by its index. The ball is located at index 0, the bat at index 1, and our hat at index 2. If we only want to print every other item, we might use the each_with_index method like this:

```ruby
my_array = ['ball', 'bat', 'hat', 'uniform', 'shoes', 'lucky glove']
my_array.each_with_index do |item, index|
  if index % 2 == 0
    puts item
  end
end
```

Remember that a modulo is a way of looking at the remainder (left over part) of a number. So here, we put the item to the screen if the index of the item has a remainder of zero when divided by 2. Since the indexes 0, 2, and 4 give no remainder when divided by 2, we only call the puts method on items at these particular indexes.

We could use the `even?` method and curly braces to simplify our enumerable method.

```ruby
my_array.each_with_index { |item, index| puts item if index.even? }

ball    #item at index 0
hat     #item at index 2
shoes   #item at index 4
```

Ruby's `even?` method allows us to skip the modulo part altogether. `Even?` will return true if the number it is called upon is an even number. Here is a way to see how the computer executes (carries out) each step in the each\_with\_index method.

```ruby
my_array = ['ball', 'bat', 'hat', 'uniform', 'shoes', 'lucky glove']
my_array.each_with_index { |item, index| puts item if index.even? }

|'ball', 0| if 0 is even?, then puts 'ball'
true => puts 'ball'

|'bat', 1| if 1 is even?, then puts 'bat'
false

|'hat', 2| if 2 is even?, then puts 'hat'
true => puts 'hat'

|'uniform', 3| if 3 is even?, then puts 'uniform'
false

|'shoes', 4| if 4 is even?, then puts 'shoes'
true => puts 'shoes'

|'gloves', 5| if 5 is even?, then puts 'gloves'
false
```

The method starts out with an item and its index from the array. It then performs the block of code we specified between the {curly brackets}. In this example it will only put the name of the item if the index is an even number. Otherwise, the if statement will return false and Ruby will not put anything to the screen for that particular block of code.

<br />
__Select__

Okay, that might have been a little complicated to understand, but trust us, it will get easier with a little practice. Let’s look at the select method to see how it iterates (looks over the stuff) in a collection. Select works by looking at the block of code passed in, and then only returns the element if the block evaluates to be true.

```ruby
 $ [1,2,3,4].select { false }
=> []

 $ [1,2,3,4].select { true }
=> [1, 2, 3, 4]
```

In the above example, the `select` method looks at each element in the array (1,2,3 and 4) and _returns_ that element if our block of code is true. Since our block of code is the _false_ boolean, the select method does not evaluate to true and returns nothing but an empty array. In the next line we pass `true` to the block and the select method returns every item in the array.

Here’s an example of how we might use the select method in a more useful way. Imagine you have a collection of test scores and you want to select only those scores above 80 points.

```ruby
test_scores = [23,80,34,99,54,82,95,78,85]
test_scores.select do |score|
  score > 80
end
=> [99, 82, 95, 85]
```

Here we use select to look at each element in the array. This value will be temporarily stored in the `score` variable. Then each particular score is checked to see if it is greater than 80. Each of the scores that are greater than 80 will be collected and returned as an array.

```ruby
test_results = {"Bobby" => 80, "Jane" => 95, "Adam" => 99,
"Doug" => 65, "Sue" => 89, "Kim" => 91}

good_students = test_results.select do |student, score|
  score > 80
end
```

Here we have a test_results hash that contains a student’s name and their test score. We can use the select method to grab each student and their score, for every student that scored higher than 80 points. If we were to run this, our good_students hash would look like this:

```ruby
$ good_students
=> {"Jane"=>95, "Adam"=>99, "Sue"=>89, "Kim"=>91}
```

You can imagine a program that runs simple select methods for hundreds of students in many classes in order to group students by their grades. Ruby is useful for sorting, counting, classifying and organizing data. It would take a person many hours to organize hundreds of students by grade and name, but a computer can do it almost instantly!

<br />
__Map__

Last but not least, let’s check out the map method. So far we’ve seen how different methods affect elements from our collections. With map, we can select certain elements and modify them at the same time. Let’s jump into an example.

```ruby
["dog", "cat", "snake", "mouse"].map { |animal| animal.capitalize }
=> ["Dog", "Cat", "Snake", "Mouse"]
```

Here we have an array of animals. We decide we want to capitalize each animal name. So we call map on the array and another built in Ruby method, `capitalize`, on each item in the array. The capitalize method takes a string and makes its first letter capitalized.

Cool, right? Map essentially finds and manipulates the data in the array, or maps your block of code to each specific element in that array. To permanently alter an array with the map feature in Ruby, simply add the exclamation point to modify the existing array.

```ruby
animals = ["dog","cat","snake","mouse"]
animals.map! { |animal| animal.capitalize }
=> ["Dog", "Cat", "Snake", "Mouse"]

animals
=> ["Dog", "Cat", "Snake", "Mouse"]
```

At this point you understand two fundamental collections in programming languages: arrays and hashes. After diving into the Enumerable module we revealed four of the most common methods used on these collections; each, each\_with\_index, select and map. Now it’s time to test your knowledge with a few more examples.

<br />
__Practice__

```
1) What numbers will the following code output?
   [1,2,3,4,5].each { |num| puts num if num.odd? }

2) What would this each method output from this string?
   "ThisdmakesdmoredsensedwithoutdD's".split("d").each { |l| puts l }

   Note: We are method chaining in the above example. The string is
   being split into smaller separate strings at the parameter passed in.
   Then the each method is called on that array.

3) What does select do for this hash?
   food = {
     "apple" => "fruit",
     "carrot" => "vegetable",
     "tomato" => "fruit"
   }
   food.select do |item, category|
      category == "vegetable"
   end

4) What will map do?
   numbers = [1,2,3,4,5]
   numbers.map { |num| num * 5 }

5) Now what is the value of numbers?
```
