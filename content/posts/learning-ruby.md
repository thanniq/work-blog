+++
author = "Thanni"
title = "Learning Ruby: Methods & Functions"
date = "2023-11-21"
description = "Learning Ruby"
tags = [
    "Ruby",
]
categories = [
    "Tutorial",
]
series = ["BackEnd Development"]
+++

Methods are a way to encapsulate and provide names for ruby expressions. It helps avoid code duplication, so we can keep calling the same methods when we need them.

<!--more-->

_This note is taken from the [Ruby on Rails Course](https://gorails.com/start) on Gorails_

There are built-in methods like uncase and downcase. But we can create our own methods too.

```ruby
def say_hello
  puts "Hello, world!"
end
```

To call the function defined above - `say_hello`

```
Hello world!
```

We can add a parameter "username" to our function

```ruby
def say_hello(username)
  puts "Hello, #{username}!"
end
```

Let's call the parametered function with an argument - `say_hello("Thanni")`

```
Hello, Thanni!
```

We can also have a function with multiple parameters.

```ruby
def say_hello(greeting, username)
  puts "#{greeting}, #{username}!"
end
```

Call the function with arguments- `say_hello("Good morning", "Thanni")`

```
Good morning, Thanni!
```

What if you called a function with one argument, instead of two? That's why we can assign default values to our parameters.

```ruby
def say(greeting = "Hello", username)
  put "#{greeting}, #{username}"
end
```

Call the function - `say_hello ("Thanni")`

```
Hello, Thanni
```

The arguments we've used so far are positional, i.e they are matched in order defined by the method. To be able to pass arguments in any order, we use keyword arguments.

```ruby
def example_method(x:, y:)
  puts "x: #{x}, y: #{y}"
end

example_method(y: 2, x: 1) # Keyword arguments
```

Methods return values by default. If the "return" keyword is not explicitly used, the last line in the function block is evaluated.

```ruby
def some_method
  2 + 2
  puts "Hello"
  5 + 5
end

some_method
```

```
10
```
