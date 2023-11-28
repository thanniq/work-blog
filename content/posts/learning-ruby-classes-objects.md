+++
author = "Thanni"
title = "Learning Ruby: Classes & Objects"
date = "2023-11-26"
description = "Learning Ruby"
tags = [
    "ruby-notes",
]
categories = [
    "Tutorial",
]
series = ["BackEnd Development"]
+++

Methods are a way to encapsulate and provide names for ruby expressions. It helps avoid code duplication, so we can keep calling the same methods when we need them.

<!--more-->

## Classes

Classes in ruby are first-class objects. Each is an instance of class `Class`

A class can be defined simply as:

```ruby
class House
end
```

To make an instance of `House`

```ruby
house_1 = House.new
```

We can set values to the `House` class, which will be inherited by every instance.

```ruby
class House
  def initialize(color)
    @color = color
  end
end

house = House.new('blue')
```

We can access the instance values by creating _getter methods_ in the class.

```ruby
class House
  def initialize(color)
    @color = color
  end

  def color
    @color
  end

end

house = House.new('blue')
puts house.color
```

We can also set new values to instances by creating _setter methods_ in the class.

```ruby
class House
  def initialize(color)
    @color = color
  end

  def color
    @color
  end

  def color=(new_color)
    @color = new_color
  end

end

house = House.new('blue')
puts house.color

house.color = "red"
puts house.color
```

A better way to create the getter and setter without having to create new methods is to use `attr_reader` and `attr_writer`

```ruby
class House
  attr_reader :color
  attr_writer :color

  def initialize(color)
    @color = color
  end

end

house = House.new('blue')
puts house.color

house.color = "red"
puts house.color
```

An even better way is to use `attr_accessor` to read and write

```ruby
class House
  attr_accessor :color

  def initialize(color)
    @color = color
  end

end

house = House.new('blue')
puts house.color

house.color = "red"
puts house.color
```

A parent class can have its own variable, and they are denoted with two `@@`

```ruby
class House
	@@count = 0
  def initialize(color)
    @color = color
  end

end

house = House.new('blue')
```

We can create a getter method for a parent class by using the `self.[method name]`

```ruby
class House
	@@count = 0
	def self.count
		@@count
	end
  def initialize(color)
    @color = color
    @@count += 1
  end

end

house = House.new('blue')
puts house.count
```

👉🏽 See [all notes](https://notes.thanni.co/learning-ruby) in this series
