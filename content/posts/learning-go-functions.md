+++
author = "Thanni"
title = "Learning Go: Functions"
date = "2023-12-29"
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

There are **3** types of functions in Go:

- Normal functions with an identifier
- Anonymous or lambda functions
- Methods

Any of these can have parameters and return values.

**Function call within a function call**

```go
f1(f2(a, b))
```

Functions are first-class values. They can be assigned to a variable, like in:

```go
add := binOp
```

## Parameters and Return Values

A function with no parameters is called a **niladic function**, like `main.main()`

**Call by value or call by reference**

**Call by Value:**

- For basic data types (integers, floats, strings, etc.), the actual value is passed to the function. Any modifications made to the parameter inside the function do not affect the original variable outside the function.

**Call by Value with Pointers:**

- For slices, maps, channels, and structs, the reference (a pointer) to the underlying data structure is passed. Changes to the data through the pointer inside the function will affect the original data outside the function.

Some functions just perform a task and do not return values. They perform what is called a _side-effect_, like printing to the console, sending a mail, logging an error, and so on. However, most functions return values, which can be named or unnamed.

UnNamed Return

```go
func getX2AndX3(input int)(int, int) {
    return 2 * input, 3 * input
}

// return are not named
```

Named Return

```go
func getX2AndX3_2(input int)(x2 int, x3 int) {
    x2 = 2 * input
    x3 = 3 * input
        //return x2, x3
    return
}

// return values are named so the keyword "return" would suffice
```

### Blank Identifier

`_` is used to _discard_ values

```go
func ThreeValues()(int, int, float32) {
    return 5, 6, 7.5
}

i1, _, f1 = ThreeValues()
```

### **Pointing to a Variable**

```go
n := 0
new_n := &n
```

A pointer variable in programming is a variable that stores the memory address of another variable. In other words, it "points" to the memory location of a value.

Here are some key points about pointer variables:

1. **Memory Address:**

   - A pointer variable holds the memory address of another variable rather than the actual value.
   - It allows direct manipulation of memory, which can be useful for tasks like dynamic memory allocation.

2. **Declaration and Initialization:**

   - You declare a pointer variable by adding an asterisk (*) before the variable name. For example: `var ptr *int`.

   - You can initialize a pointer by assigning the memory address of a variable to it.

     ```go
     var x int = 42
     var ptr *int = &x // ptr now holds the memory address of x
     ```

3. **Dereferencing:**

   - To access the value pointed to by a pointer, you use the dereference operator (\*).

   - Example: `value := *ptr` gets the value stored at the memory address pointed to by `ptr`.

     ```go
     fmt.Println(*ptr) // prints the value stored at the memory address pointed to by ptr
     ```

4. **Null Pointers:**

   - In many languages, pointers can have a special value called `null` or `nil`, indicating that they do not point to a valid memory address.

     ```go
     var ptr *int // uninitialized pointer (nil)
     ```

5. **Pointer Arithmetic:**

   - Some languages (like C and C++) allow pointer arithmetic, but Go does not. Go restricts direct manipulation of memory addresses for safety.

   ```go
   // This is invalid in Go
   // ptr = ptr + 1 // pointer arithmetic not allowed
   ```

## Defer and Tracing

Defer is used to postpone function calls until the parent function is done executing.

```go
package main
import "fmt"

func main() {
    Function1()
}

func Function1() {
    fmt.Printf("In Function1 at the top\n")
    defer Function2() // function deferred, will be executed after Function1 is done.
    fmt.Printf("In Function1 at the bottom!\n")
}

func Function2() {
    fmt.Printf("Function2: Deferred until the end of the calling function!")
}
```

This defer function can be used to inverse a sequence of execution like in a stack (LIFO).

```go
package main
import "fmt"

func main() {
    for i := 0; i < 5; i++ {
        defer fmt.Printf("%d ", i)
    }
}
// output 4, 3, 2, 1, 0
```

The last deferred is the first to be executed in the above code.

### Tracing with Defer

When you want to trace the execution flow of a function, you can use `defer` to schedule logging statements at the beginning and end of the function.

```go
func myFunction() {
    // Trace start of function
    defer trace("myFunction - start")()

    // Function logic goes here

    // Trace end of function
    defer trace("myFunction - end")()
}

func trace(msg string) func() {
    fmt.Println("Entering:", msg)
    return func() {
        fmt.Println("Exiting:", msg)
    }
}

```

Using `defer` with tracing in Golang allows you to log information about the entry and exit of functions, aiding in debugging and performance analysis.

## Built-In Functions

Examples include `close, len, cap, new, make, copy, append, panic, recover, print, println, complex, real, imag`

## Higher Order Functions

Functions can also be passed as values

```go
func inc1(x int) int { return x+1 }
f1 := inc1 // f1 := func (x int) int { return x+1 }
```

## Function Literals

Sometimes, we do not want to give a function a name. Instead, we can make an **anonymous function** (also known as a _lambda_ function, a _function literal_, or a _closure_), for example:

```go
func(x, y int) int { return x + y }
```

Such function cannot stand on its own, so it needs to be assigned to a variable or invoked directly.

```go
fplus := func(x, y int) int { return x + y }
fplus(3,4)

// directly

func(x, y int) int { return x + y } (3, 4)
```

## Functions as Return Variables

```go
package main

import "fmt"

type flt func(int) bool

func genInc() flt {
    y := func(x int) bool {
        return x > 2
    }
    return y
}

func main() {
    increment := genInc()
    result := increment(3)
    fmt.Println(result)
}

```

## Debugging using `runtime`

```go
package main

import (
    "fmt"
    "log"
    "runtime"
)

func main() {
    where := func() { // debugging function
        _, file, line, _ := runtime.Caller(1)
        log.Printf("%s:%d", file, line)
    }

    where() // Print file and line information for the first time

    // some code

    a := 2 * 5
    where() // Print file and line information after calculating 'a'

    // some more code

    b := a + 100
    fmt.Println("a: ", a)
    fmt.Println("b: ", b)
    where() // Print file and line information after calculating 'b'
}

```

## Debugging using `log`

```go
package main

import (
	"fmt"
	"log"
	"math"
)

func main() {
	log.Println("Program started")

	result, err := calculateSquareRoot(-4.0)
	if err != nil {
		log.Printf("Error: %v", err)
	} else {
		log.Printf("Result: %f", result)
	}

	log.Println("Program finished")
}

func calculateSquareRoot(x float64) (float64, error) {
	if x < 0 {
		return 0, fmt.Errorf("cannot calculate square root of a negative number")
	}

	return math.Sqrt(x), nil
}

```

## Timing a function

```go
package main
import "fmt"
import "time"

func Calculation(){
    for i := 0; i<10000; i++{
        //do something
    }
}
func main(){
    start := time.Now()
    Calculation()
    end := time.Now()
    delta := end.Sub(start)
    fmt.Printf("Calculation took this amount of time: %s\n", delta)
}
```

## Using Memoization for Performance

Memoization is a technique used in computer programming to optimize the execution of functions by caching or storing the results of expensive function calls and returning the cached result when the same inputs occur again. In simpler terms, it's like keeping a memo (memory) of past calculations to avoid redundant work.

```go
package main

import (
	"fmt"
)

func fib(n int, memo map[int]int) int {
	if result, found := memo[n]; found {
		return result
	}

	if n <= 2 {
		return 1
	}

	result := fib(n-1, memo) + fib(n-2, memo)
	memo[n] = result // Memoize the result for future use
	return result
}

func main() {
	memo := make(map[int]int)
	n := 10
	result := fib(n, memo)
	fmt.Printf("Fibonacci(%d) = %d\n", n, result)
}
```

## Recursion

```go
package main
import "fmt"

func main() {
    printrec(1)
}

func printrec(i int) {
    if i > 10 {
        return
    }
    printrec(i + 1)
    fmt.Printf("%d ", i)
}

// output - 10, 9, 8, 7, 6, 5, 4, 3, 2, 1

// printing each iteration before calling the function again will give the reverse.

package main
import "fmt"

func main() {
    printrec(1)
}

func printrec(i int) {
    if i > 10 {
        return
    }
    fmt.Printf("%d ", i)
  	printrec(i + 1)
}
```

👉🏽 See [all notes](https://notes.thanni.co/learning-go) in this series
