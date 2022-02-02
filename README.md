# Overview

3 languages (Typescript, Solidity, Rust) more or less inspired by Javascript and compared here on most used statements.


# Comparison

## Type declaration

| Javascript  |  Typescript |  Solidity | Rust  |
|---|---|---|---|
|  let a = 2; |  let a:number = 2; |  int256 a = 2; |  let a: i32 = 2; |

Rust is far more complex concerning variables. For example:

- The variable declared here are immutable by default. To be able to modify such a variable we need to do :
```
let mut a: i32 = 2;
```
- Variable  


## Function declaration

Worth noting that all of them are declaring the return type except Javascript.


| Javascript  |  Typescript |  Solidity | Rust  |
|---|---|---|---|
|  function a(x,y){} |  function a(x: number,y: string): void {} |  function a(int256 x, int256 y) return (int256) {} |  pub fn a(x: i32, y: i32) -> i32 {} |


Function key word can also be ommitted and replaced by arrow functions in JS and TS:

```
const a = (x,y) => {
}
```

And similar anomymous function are possible with rust:

```
let a = |x, y| {
}
```

Rust supports implicit return statement : the very last statement not finishing with ; is considered as a return.

## Arrays


| Javascript  |  Typescript |  Solidity | Rust  |
|---|---|---|---|
|  let c = []; |  let c:number[] = []; |  int256[] memory c; |  let c:[i32; 3] = [0; 3]; |

Here with arrays Rust is a bit more complicate. While all data in JS/TS/SOL are stored in a heap (using GC), Rust distinguish between stack and heap. Stack is a fixed sized memory allocation included in the compiled bundle. It is not extensible, contrary to the heap which is a dynamic memory allocation.

Stack based array:

```
let c:[i32; 3] = [0; 3];
```

Heap based array:

```
let c: Vec<i32> = vec![];
```


## For loop

| Javascript  |  Typescript |  Solidity | Rust  |
|---|---|---|---|
|  for(let i = 0; i < a.length; i++) |  for (let i of a) {} |  for(uint i = 0; i < a.length; i++) |  for i in list |


Some cool things in Rust:

```
for i in 1..100 {} // 100 is excluded
```

To loop in a vec:

```
let a = vec![3,4,5];
for x in a.inter() {}
```


## Class

| Javascript  |  Typescript |  Solidity | Rust  |
|---|---|---|---|
|  class MyClass {} |   |  contract MyClass {} |   |