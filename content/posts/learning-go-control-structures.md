+++
author = "Thanni"
title = "Learning Go: Control Structures"
date = "2023-12-19"
description = "Learning Go"
tags = [
    "go-notes",
]
categories = [
    "Tutorial",
]
series = ["BackEnd Development"]
+++

Go Control Structures empower precise flow: loops for iteration, conditionals for decisions. Simplifying logic with elegance and efficiency

<!--more-->

Go provides the following conditional or branching structures:

- The `if-else` construct
- The `switch-case` construct
- The `for` construct

## The `if-else` Construct

```go
if condition {
    // do something
}
.......
if condition {
// do something
} else {
// do something else
}
.......
if condition1 {
    // do something
} else if condition2 {
    // do something else
} else {
    // catch-all or default
}
.......
if true {
    fmt.Printf("I'm always executing this branch");
}
.......
if false {
    fmt.Printf("I will never execute this code!")
}
```

### **Testing for Errors on Functions**

An error message is nil if there's no error. So...

```go
if err != nil {
	// print the error message
	return
}
```

In a situation where we're converting a string to an integer

```go
package main
import (
"fmt"
"strconv"
)

func main() {
    var orig string = "ABC"
    var an int
    var err error
    // storing integer and error information
    an, err = strconv.Atoi(orig)

    if err != nil { // if it was an error, discontinue
        fmt.Printf("orig %s is not an integer - exiting with error\n", orig)
        return
    }
    fmt.Printf("The integer is %d\n", an)
    // rest of the code
}
```

## The `switch-case` construct

We use the switch case if we're looking to compare a variable to different values. And each value should give a unique result.

```go
switch var1 {
case val1:
...
case val2:
...
default:
...
}

// if there's only one value, it can be written as

case val1, val2, val3:

// for cases where there's no return, you can use the fallthrough

switch i {
case 0: fallthrough
case 1:
    f() // f is now also called when i==0!
}
```

## The `for` construct

**Types of for loops**

There are _two_ methods to control iteration:

- _Counter-controlled_ iteration
- _Condition-controlled_ iteration

The simplest form is the counter-controlled iteration. The general format is:

```go
for initialization; condition; modification { }
```

For example:

```go
for i := 0; i < 10; i++ {}
```

For condition controlled

```go
for condition { }
```

```go
package main
import "fmt"

func main() {
    var i int = 0
    // condition controlled for loop with 5 iterations
    for i < 5 {
        fmt.Printf("This is the %d iteration\n", i)
        i = i + 1
    }
}
```

Infinite loop is written as `for { }`

### Use of for range of `for range`

```go
for pos, char := range str {
        fmt.Printf("Character on position %d is: %c \n", pos, char)
    }
```

In the above code, pos is the index, char is the value.

### Labels

Labels are identifiers associated with a statement in your code. You can use labels with control flow statements like `break` and `continue` to specify which loop or switch statement you want to break out of or continue.

```go
package main

import "fmt"

func main() {
    // Define a label called "outer"
outer:
    for i := 0; i < 3; i++ {
        for j := 0; j < 3; j++ {
            if i == 1 && j == 1 {
                // Use the "outer" label to break out of the outer loop
                break outer
            }
            fmt.Printf("%d %d\n", i, j)
        }
    }
}

```

In this example, the `outer` label is associated with the outer `for` loop. When the condition `i == 1 && j == 1` is met, the `break outer` statement is executed, causing the program to exit the outer loop immediately.

👉🏽 See [all notes](https://notes.thanni.co/learning-go) in this series
