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
def say(greeting, username)
  puts "#{greeting}, #{username}!"
end
```

Let's call the function with arguments- `say_hello("Good morning", "Thanni")`

```
Good morning, Thanni!
```

<mark>Learning in progress</mark>
