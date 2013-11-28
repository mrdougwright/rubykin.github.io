---
layout: default
title: Variables
weight: 4
---

At their simplest, variables are merely storage containers. They help us hold information. You create your own variables, starting with a lowercase letter followed by an equal sign and its value (usually a number or a string, but sometimes more complex code can be stored in a variable). You’ve seen this before in math.

```
x = 12
The value of x is?
=> 12
```

In programming, variable storage is slightly different due to the way memory storage is created. In an effort to _not_ waste memory, we don't store duplicate information. In the following example, each variable (X, Y and Z) will point to the same place in memory because they store the same value, twelve.

```
x = 12
y = x
z = 12
```

In order to store the value 12, the computer creates a location in memory with an address, let's assume the address is ABC12. In this sense, a variable is like an X on a treasure map, guiding you to the right location. 

Yet variables don't _actually_ store their information--they point to it. Or in another way, variables store memory addressess that store information. In the example above, each variable points to the same memory address that stores the number 12. This way the computer doesn't need to create three different memory locations for one value, it can use ABC12 for all three.

```
x = 12  => mem address: ABC12
y = x   => mem address: ABC12
z = 12  => mem address: ABC12
```

Now that you know how variables don't store information (they store memory addresses) see if you can figure out the end value of X:

```
y = 5   => y points to memory address AB1, which contains the value 5
x = y   => x points to memory address AB1
y = 7   => y now points to memory address CD1, which contains 7
```

The trick here is to understand that X does _not equal_ Y. Remember, X only _POINTS_ to the value stored in the memory address that Y points to (AB1). No matter what happens later to Y, the only thing X needs to remember is the location of AB1 (which will always be 5 while this program is running). 

When we change the value of Y to 7, we are actually telling the computer to create a new memory address that contains the value 7 and point to it. X does not change its original address, so the value of X remains 5.

There is a built-in Ruby method called `object_id` that shows the id of the Ruby object. This can be correlated to a kind of unique memory address. Let’s look at the following example using this method.

```
y = "test" => y.object_id => 7021
x = y      => x.object_id => 7021
```

At this point, only one memory address needs to be created, since the stored value ("test") is the value for both X and Y.

```
y = "new"  => y.object_id => 8333
x equals?  => x.object_id => 7021
```

Once we change the value of Y, we create a new memory location with a new value stored ("new"). X does not equal "new", it still equals the value stored in the original memory address that it pointed to at the time we set X equal to Y.

When we change variables and add new information, Ruby creates more memory locations with specific addresses--if none of the current addresses are holding the same information.

Don't worry if this is all too confusing. You don't actually _need_ to fully understand this concept to program. As we move along through the other core concepts of coding you will begin to see how variables work within the bigger picture.

<br />
__Practice__

```
1) Store the value of 54 / 3 into the variable x. What is the value of x?

2) Give the value of x to y, a new variable. Now make x equal to itself 
divided by 3. What’s the value of x? What’s the value of y?

3) What if we performed some math on our variables? If we set x to 12, 
what’s x divided by 3?

4) What’s the value of x now?
```