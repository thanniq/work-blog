+++
author = "Thanni"
title = "Learning Ruby: Loops & Blocks"
date = "2023-11-25"
description = "Learning Ruby"
tags = [
    "ruby-notes",
]
categories = [
    "Tutorial",
]
series = ["BackEnd Development"]
+++

A loop is a control structure that allows you to repeatedly execute a block of code.

```ruby
loop do
	puts "I'm looping..."
end
```

<!--more-->

## Loops

The above code is called an infinite loop because it won't stop executing unless we add a clause.

```ruby
20.times do
  puts "I'm looping..."
end
```

```
I'm looping...
I'm looping...
I'm looping...
.......
.......
I'm looping... (20th)
```

We could also do

```ruby
1.upto(20) do
  puts "I'm looping..."
end
```

Also

```ruby
1.upto(10) { |n| puts n }
```

## While Loop

```ruby
while <= 50
  puts "Not greater than or equals to 50, yet..."
  num += 1
end
```

## Until Keyword

```ruby
until num > 50
	puts "Not there yet..."
  num += 1
end
```

## .each

```ruby
nums = [1, 2, 3, 4, 5]
nums.each { |num| puts num}

output:
1
2
3
4
5
```

## Code Blocks

They are nameless methods. They can be passed into other methods or stored for later use.

```ruby
negative_nums = [-1, -2, -3, -4, -5]
positive_nums = negative_nums { |num| mum.abs}

output:
[1, 2, 3, 4, 5]
```

Code blocks can also be passed into methods for reusability. Each method call below will produce a different result.

```ruby
def play_with_each_toy(toy_box, &instructions)
  toy_box.each do |toy|
    instructions.call(toy)
  end
end

toys = [1, 2, 3, 4, 5]

play_with_each_toy(toys) do |toy|
  puts toy * 2
end

play_with_each_toy(toys) do |toy|
  puts toy * 4
end
```

We could also use the `yield` keyword to achieve the same result

```ruby
def play_with_each_toy(toy_box)
  toy_box.each do |toy|
    yield(toy * 2)
  end
end

toys = [1, 2, 3, 4, 5]

play_with_each_toy(toys) do |result|
  puts result
end
```

Also, we could save a block for later use

```ruby
saved_block = Proc.new { |x| x * 3 }

result = saved_block.call(5)
puts "Result from saved block: #{result}"
```

### if block_given?

Calling a blocked method without a block will return an error. Even with using the yield keyword. We solve this using a conditional

```ruby
def play_with_each_toy(toy_box, &instructions)
  toy_box.each do |toy|
    instructions.call(toy) if block_given?
  end
end

toys = [1, 2, 3, 4, 5]

# Using the block
play_with_each_toy(toys) do |toy|
  puts toy * 3
end

# Without providing a block
play_with_each_toy(toys)

```

We can also create a code block with `lambda` and `stubby_lambda`

```ruby
# Using lambda keyword
my_lambda = lambda { |x| puts x * 2 }
my_lambda.call(5)  # Output: 10
```

```ruby
# Using stabby lambda syntax
my_stabby_lambda = ->(x) { puts x * 2 }
my_stabby_lambda.call(5)  # Output: 10
```

👉🏽 See [all notes](https://notes.thanni.co/learning-ruby) in this series
