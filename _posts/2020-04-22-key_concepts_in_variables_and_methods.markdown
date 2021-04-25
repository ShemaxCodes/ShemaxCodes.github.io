---
layout: post
title:      "Key Concepts in Variables and Methods"
date:       2020-04-22 15:31:02 +0000
permalink:  key_concepts_in_variables_and_methods
---


Variables and Methods allow us to create references to data. They're very common and you'll use them pretty often, if not each time you code in Ruby. Let's break it down with some examples. 

# What are Variables?

Everything in Ruby is an object. However, a variable itself is not an object, but a placeholder for an object. They are sometimes called pointers or identifiers, but we want to stick with the term "variable." 

Here is an example of a variable. Here, I assigned "Jashema" to the` first_name` variable and "Panapa" to the `last_name` variable. So, later on in my program, instead of literally typing "Jashema" each time I want to use my first name, I can now refer to my `first_name` variable or `puts first_name` anywhere in my code and it will output "Jashema." 
 
```
#Variable Syntax
first_name = "Jashema"
last_name = "Panapa"
```

Variable types do not have to be declared. The same variable can be reassigned to an object of another data type.
# Syntax
Variables are pointed to an object using the equal sign. They must start with a lowercase letter or underscore.
Spaces aren't allowed when creating variables, as you see here. If a space is needed in between two words, use an underscore.  Remember, variables are case-sensitive

```
first_name = "Jashema"
last_name = "Panapa"
birth_month = "November"
age = 24

```

# What are Methods?

Methods define or tell a thing that your program can do. Variables teach our program about data, while methods teach the program a "behavior" it can use. One way that I learned from Flatiron that made it simpler to understand is to think of it like this - variables are like nouns and methods are like verbs. Variables and methods go hand in hand. Let's look at an example. 

Say that we're at Hogwarts, and Hermoine wants to say "hello" each to Ron, Harry, Hagrid, Dumbledore, and Professor McGonagall. That's five people. If I set it as a variable and only use the variable: 

`phrase = "Hello"`

I would have to type that variable five times, such as this just to get my point across. 

puts phrase
puts phrase
puts phrase
puts phrase
puts phrase 

That's a bit redundant and this is where methods come in and are useful. Remember, methods teach the program behaviors and they are like verbs. So, I can create or build a method using the `def `keyword that will tell my program exactly what I want it to do. What I want: for Hermoine to say Hello five times. 

```
def greeting
      puts phrase
      puts phrase
      puts phrase
      puts phrase
      puts phrase 
end 
```

Now, when I want Hermoine to greet each person, I will only have to call my method, instead of typing puts phrase 5 times, like this: 


greeting 

This will output:

=> "Hello"
=> "Hello"
=> "Hello"
=> "Hello"
=> "Hello"
# Syntax

How do you define a method? Using the same code as above, you can define methods in Ruby with the `def` keyword. This begins or opens the method. 

def greeting   #This is the Method Signature. The method name (greeting) begins with a lowercase letter.
      puts phrase #Method Body - what you want the method to actuallly do (the behavior)
    
end #How to Close your Method 

