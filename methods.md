---
layout: default
title: Methods
weight: 8
---

A big part of programming is simply breaking down large problems into smaller and smaller instructions that can work together to create a solution. Let’s think of this using a real world example. Imagine you are playing baseball and its your turn to bat. This critical moment when you swing and hit the ball for a home run can be seen as many smaller moments that led to the big play. 

First you picked up a bat. Then you took a few practices swings. Then you walked up to the plate, you readied your stance, looked at the pitcher. Finally, you took a breath and swung! Each of these small steps can be seen as methods (small chunks of instructions) that led to your home run. 

We can look at this another way. When you play a video game and reach a new level, there may actually be _real_ methods that are called by the game. Perhaps the game contains a 'life count' method that counts how many lives you have left. Another method could tally up your current score. A third method may calculate your character's current state of health. Each of these methods would take input from your actions in the game, and go back and get information from the program to keep everything updated and accurate.

To understand methods a little better, let’s jump into writing one ourselves. Here’s a very simple method you can write yourself that merely puts information to the screen. You can write a method inside IRB (the Ruby Interpreter) without creating a new file. There is an online version as well at <a href="http://repl.it/languages/Ruby" target="_blank">Repl.it</a>). 

In your terminal type irb:

```ruby
               $ irb   # type irb to open the ruby interpreter
irb(main):001:0> def hello
irb(main):002:1> puts "Hello World!"
irb(main):003:1> end
=> nil
```

In Ruby, we define a method using the `def` keyword. The next word after def is the name of our method. This would be our _hello_ method, which takes no arguments (kind of like your parents at bedtime). We’ll explain arguments in a moment.

Like at the end of a movie or bedtime story, the word `end` in Ruby means the same thing as it does to you--that this is the _end_ of our method. Any code in between our def and end keywords will be run by the computer for this particular method. This code is our "block" we give the method to execute. 

In order to write and save several methods, it will be easier to create a file and run the code inside the file, so let’s do that. Exit the terminal by typing `exit`. 

Open up a text editor. I like using <a href="http://www.sublimetext.com/" target="_blank">Sublime</a>, but you can use any kind. There are several free text editors for download online. Create a new file and type in the method we wrote above.

```ruby
1. def hello
2.   puts "Hello World!"
3. end
```

Save this file as `hello.rb` to your desktop. Now you can run this file from your terminal. In your terminal, navigate to the Desktop directory using `cd`, the change directory command. 

If you don’t know how to find your file from the terminal console, I can help you with a simple trick. Just type the following. (This will take you to your root folder and then to your desktop).

```
Your-Computer-Name:$ cd
Your-Computer-Name:$ cd ~/Desktop
Your-Computer-Name:Desktop $
```

Now that we are in the Desktop directory, where our hello.rb file is stored, we can run our Ruby file using the ruby command! Type `ruby hello.rb` into the console. It may look something like this.

```
Your-Computer-Name:Desktop $ ruby hello.rb
Your-Computer-Name:Desktop $
```

If you had no errors and no output, then your program ran as expected. Great job! 

But wait, why didn’t it put "Hello World!" to the screen? Well, this is because our hello method was not _called_. We simply ran a program that contained our hello method, but we didn’t specifically _call_ upon that method to be run by the computer. We can fix this by updating our hello.rb file.

```ruby
1. def hello
2.   puts "Hello World!"
3. end
4. 
5. hello()
```

Now when we run hello.rb, our hello method is called on line 5. We call a method by simply writing the name of the method. The parenthesis are optional, because this method has no arguments. If there were arguments, or inputs into our method, we would put them inside the parenthesis. Now when we run our program, we should see output like this:

```ruby
Your-Computer-Name:$ ruby hello.rb
Hello World!
Your-Computer-Name:$
```

Congratulations! You just ran your first Ruby program with its very own method. It ran successfully and outputted "Hello World!" to the screen using Ruby’s built in `puts` method. 

Now let’s try writing a method that takes an argument. What if we want to multiply any two numbers together using our own method. We could write something like this.

```ruby
def multiply(num1,num2)
  num1 * num2
end
```

We define our method as multiply and _pass in_ two arguments using parenthesis (num1 and num2). Then we can simply use Ruby’s multiply operator (the * method) on both numbers. The result is returned since it is the last line in our method. (In Ruby, the last line of a method is returned by default.)

```ruby
multiply(2,3)
=> 6

multiply(4,2)
=> 8

multiply("Hi",3)
=> "HiHiHi"
```

Uh oh, looks like our method can multiply more than numbers! We can modify our code to ensure our users enter numbers, but let’s not worry about that now. How about another way to use arguments for a method. What if we want to calculate how many days old we are?

```ruby
def years_to_days_old(years)
  result = years * 365
  puts "You are #{result} days old!"
end
```

If we ran this method our input would be stored in the years variable. We would then multiply 365 days by our `years` input and store the result in our variable `result`. The puts method outputs our string to the screen, using interpolation to display the result in our answer string.

```ruby
years_to_days_old(10)
You are 3650 days old!
=> nil
```

String interpolation is when Ruby allows a piece code to exist inside a string. This can be a variable or even math, written with a pound sign and curly braces `#{ }`. Here are some examples to get the idea.

```ruby
x = 15
puts "This string has the #{x} variable inside."
=> This string has the 15 variable inside.

puts "This one is doing math: #{x + 5}"
=> puts This one is doing math: 20
```

We could add more functionality to the `years_to_days_old` method and remove the argument input. If we use Ruby’s `gets` method we can capture the input from a user’s response. We call chomp to remove (or chomp and eat) the new line character (like we did earlier). The `to_i` method turns the user’s string input into an integer. Our method might look something like this.

```ruby
1. def years_to_days_old
2.   puts "How old are you in years?"
3.   years = gets.chomp.to_i
4.   days = 365 * years
5.   puts "You are #{days} days old!"
6. end
```

Let’s run this from our IRB terminal. First, save the code above in a file called `age_in_days.rb` and place this in your desktop or your project folder. Now, when you open up your terminal or console, navigate to this folder and type `irb` in the command line. There, you can load the file and call the method by typing it. Here’s an example below.

```
/Documents/Ruby/my_code_folder >
/Documents/Ruby/my_code_folder > irb
>> load 'age_in_days.rb'
=> true
>> years_to_days_old
How old are you in years?
```

Now that you have a basic understanding of methods, see if you can write one yourself. You could write an adventure word game or create your own calculator. 

<br />
__Practice__

```
1) What is the name of the method below?
   def multiply(num1,num2)
     num1 * num2
   end

2) How many arguments does this method have?
   def meeting(place, time, day)
     ...
   end

3) What does this method return when called? (What's its output?)
   def calculus
     numbers = (25 * 37) / 42
     numbers / 12 * 25
     "Programming is not math"
   end

4) Write a method that takes a word as an argument. Make the method 
   return the word and the string “, is awesome!”.
```
