+++
author = "Thanni"
title = "Typescript Crash Course"
date = "2023-12-01"
description = "Typescript"
tags = [
    "typescript",
]
categories = [
    "Tutorial",
]
series = ["BackEnd Development"]
+++

TypeScript, a superset of JavaScript, enhances code quality with static typing. It brings robustness to web development, empowering developers with modern features.

<!--more-->

## Starting a typescript project with the CLI

`npm init -y` to create the package.json file.

Install the typescript compiler - `npm i --save-dev typescript` as a dev dependency

`npx tsc --init` to run the typescript compiler and create a config file

## Starting a typescript project with a bundle - VITE

`npm create vite@latest .`

## Assignment Types

```typescript
let a: number = 5;
let b: string = "asdf";
let a: number[] = []; // array type
let a; // any type
```

## Objects

```typescript
const user: { name: string; age: number; isProgrammer: boolean } = {
  name: "John",
  age: 32,
  isProgrammer: true,
};
```

We could also make one of the types optional using `?` after the variable identifier

```typescript
const user: { name: string; age: number; isProgrammer?: boolean } = {
  name: "John",
  age: 32,
};
```

### Type

A type is declared with capital case - `PersonName`

```typescript
type Person = { name: string; age: number; isProgrammer?: boolean };

const user: Person = {
  name: "John",
  age: 32,
};
```

### Interface

An interface is more or less like type, but it has a few differences

- It has no equal sign - `interface Person {....}`
- It has to be an object
- It's not flexible like type where it can be assigned to other types e.g `type Person = number`

```typescript
interface Person {
  name: string;
  age: number;
  isProgrammer?: boolean;
}
```

## Functions

A function takes parameters with types and returns a type (implicitly) too.

```typescript
function printPerson (name: string, age: number) {
  return ()
} //This code returns any type, but the arguments when calling the funciton msut be a string and a number.

function printPerson (person: {name: string}) {
  return (person.name)
}
```

### Void Type

Unless explicitly stated that a function returns undefined, a function that doesn't return anything returns void by defauly.

```typescript
function printPerson(name: string, age: number) {
  console.log(age);
  return;
}
```

### Optional Parameters

Uses the `?` to denote parameters that are optional when passing arguments.

```typescript
function printPerson(name: string, age?: number) {
  console.log(age);
  return;
}
```

### Destructured Parameters

```typescript
type options = { debugMode: boolean };

function test(age: number, { debugMode = false }: options) {
  console.log(age, debugMode);
}
test(18, { debugMode: true });
```

### Rest Parameters

It's always important to use an array type when passing a rest parameter

```typescript
function test(...nums: number[]) {
  console.log(nums);
}
test(1, 3, 4, 5, 6, 7, 8, 9, 0);
```

### Functions as Variables

```typescript
function test(a: number, b: number, cb: (x: number, y: number) => void) {
  cb(a, b);
}

test(3, 8, (x, y) => {
  console.log(x * y);
});
```

## More Types

### Union Type

We can have a union of types

```typescript
type name = string | number;

function sayHello(name: name) {
  console.log(`Hello ${name}`);
}

sayHello("Thanni");
```

We can also have a union of defined values

```typescript
type name = "user" | "username";

function sayHello(name: name) {
  console.log(`Hello ${name}`);
}

sayHello("user");
```

We can also have a union of unions

### Intersection Type

An intersection is the opposite of union, using the `&` sign

```typescript
type Person = {
  user: string;
  age: number;
};

type PersonWithID = Person & { id: number };

const person: PersonWithID = { user: "John", age: 30, id: 1 };

console.log(person);
```

### Read Only

```typescript
type NumberArray = readonly number[];

const newNum: NumberArray = [1, 2, 3, 4, 5];
```

### KeyOf

```typescript
type Person = {
  user: string;
  age: number;
};

const person = setPerson("user", { user: "Thanni", age: 25 });

function setPerson(key: keyof Person, Person: Person) {
  console.log(Person[key]);
}
```

### TypeOf

```typescript
const user = {
  user: "Thanni",
  age: 25,
};

const newUser: typeof user[] = [];

newUser.push(user);
newUser.push({ user: "John", age: 30 });

console.log(newUser);
```
