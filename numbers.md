---
layout: default
title: Numbers
weight: 2
---

Numbers! Yay, Math is fun. 

Remember math? So does Ruby. Ruby uses the same adding, subtracting, multiplication and division that you do. 

```ruby
2 + 2 = 4
9 - 3 = 6
2 * 3 = 6
4 / 2 = 2
```

Ruby can also perform logical operations, such as greater than (>) and less than (<).

```ruby
4 > 2 => true
3 < 2 => false
3 >= 3 => true
0 <= 1 => true
```

You can try these simple commands yourself, but first you need to have Ruby installed on your computer.
If you’re using Mac OS X, Ruby is already installed. Hooray! Just open up Terminal and type IRB  (or irb) and hit enter. To find terminal you can click the magnifying class in the top right corner of your screen, then type Terminal and click the first result. Next, type the letters "IRB" into the screen and hit enter. Once it opens, you can try some of the commands we looked at above. For example, you can try things like 4 < 2 or 4 > 1 to see that Ruby understands the same commands as you.

If you’re using Linux, open up a shell and type irb and hit enter.
And if you’re on Windows, open fxri from the Ruby section of your Start Menu.

As a third option, check out <a href="http://repl.it/languages/Ruby" target="_blank">Repl.it</a>. This is a pretty fantastic tool that allows you to type code into your browser. No installation required!

So, what is IRB anyway?
IRB stands for Interactive Ruby Shell. An Interactive Ruby Shell is like a little secret fort located inside your computer. You can use your IRB to play around with Ruby and learn different Ruby commands. Now, open up your IRB and try typing some of the calculations above to see what the computer returns.
Ruby can also handle exponents. 

Exponents tell a number how many times it should be multiplied. For example, 2 times 2 equals 4, 4 times 2 equals 8. So, 2**3 means 2 times 2 times 2, or 8. Three multiplied by itself twice equals 9. 3 times 3 equals 9. Don't worry about exponents if they are unfamiliar to you. They are not necessary to learn programming!

```ruby
2 ** 3 => 8
3 ** 2 => 9
```

In addition to these standard math operations, the computer has something called the modulo operator, which is represented using a percent symbol: %. Whenever you see the % the computer knows you are looking for the modulo operator. The modulo’s job is to finds the remainder after dividing one number with another. The remainder is what is left over, or remains when you divide one big number by a smaller number. 

So, 9 divided by 3 would result in a modulo of zero because there is no remainder. Since 3 divides evenly into 9 there are no numbers left over, and that is why 9 modulo 3 is 0. Now, let’s try it again with a different set of numbers. If we looked at 9 modulo 2, we would have a remainder, or a modulo operator of 1, because 9 divided by 2 equals 8 leaving a remainder of 1.

```ruby
8 % 2 => 0
9 % 2 => 1
9 % 5 => 4
```

If exponents and modulos are too complex to understand right now, don't worry. Again, they are not a requirement for programming. It's important at this stage to simply understand that the computer can do simple math for you. Check out some examples below.


Example

Try these problems in your head, or on paper.

```ruby
2 + 3 + 5
10 - 3
9 / 3
4 * 2
4 ** 2
```

Now for some harder ones.

What is the result of 10 % 4 ?

A wizard has a bag of 5 numbers, but he doesn’t know what they are. 
He needs to find out which of the 5 different numbers are even? 
How might you use modulo to help him?