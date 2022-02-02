# Overview

Typescript, Solidity and Rust are more (TS and solidity) or less (Rust) inspired by Javascript and compared here on most used statements.

Using all these languages might appear a bit strange. But we love using **javascript** for its simplicity being a complete language syntax with a script approach, while being browser compatible. Then if we need to add some safety we move to **typescript**. We could need to run CPU intensive code, then **Rust** is our lifesaver. And finally to be able to run our code in the blockchain and not on a specific server, **Solidity** is a good candidate.


# Comparison

## Type declaration

| Javascript  |  Typescript |  Solidity | Rust  |
|---|---|---|---|
|  let a = 2; |  let a:number = 2; |  int256 a = 2; |  let a: i32 = 2; |

- While Rust is using static typing, the compiler will infer automatically the type from the context when possible.

- The variable declared here are immutable by default. To be able to modify such a variable we need to do :
```
let mut a: i32 = 2;
```

- Note also that variables in Rust are handled by a mecanism of borrowing to allow the freeing of the memory. See [this](https://doc.rust-lang.org/rust-by-example/scope/move.html).

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

I group in this section JS classes, with Solidity Contracts and Rust structs are all the structures are used with the same objective : having in the same place related properties and behaviour.

| Javascript  |  Typescript |  Solidity | Rust  |
|---|---|---|---|
|  class Point {} |   |  contract Point {} |   |