---
title: Rust
parent:
  - "[[Cheat Sheet]]"
aliases: 
tags:
  - dense-note
  - incomplete
---
## Syntax
### Keywords
**as** - Used for casting between types.
- `let x = 10 as f64; // Casts integer to floating point`
**async** - Marks a function or block as asynchronus, meaining it returns a `Future` and can be awaited.
- `async fn my_async_function() { }`
**await** - Used to wait for the completion of an asynchronus operation.
- `let result = my_async_function().await;`
**break** - Exit a loop early.
**const** - Defines a constant given a fixed value at comile-time.
- `const MAX_SIZE: u32 = 100;`
**continue** - Skips the rest of the current loop iteration and proceeds to the next iteration.
**crate** - Refers to the current crate or package.
 - `use crate::my_module::public_function;`
**dyn** - Used to denote dynamic dispatch for trait objects.
- `let obj: &dyn MyTrait = &MyStruct;`
**else** - Used in conditional branches.
**enum** - Defines an enumerated type.
**extern** - Links external code or marks functions as available outside the current module.
**false** - A boolean literal representing false.
**fn** - Declares a function.
- `fn my_function() { }`
**for** - Defines a loop over an iterator.
- `for i in 0..5 { } `
**if** - Used in conditional branches.
**impl** - Defines an implementation block for methods or traits.
**in** - Used in for loops to specify the ranger or iterator to loop over.
- `for i in 0..5 { } `
**let** - Declares a variable.
**loop** - Creates an infinite loop.
- `loop { } `
**match** - Pattern matching for multiple conditions.
```
match x {
	1 => println!("One),
	2 => println!("Two"),
	_ => println!("Other"),
}
```
**mod** - Declares a module.
- `mod my_module { } `
**move** - Captures variables by value in closures, moving them into the closure.
- `let x = 10;`
- `let closure = move || println!("{}", x);`
**mut** - Marks a variable as mutable.
- `let mut x = 5;`
**pub** - Marks an item as public.
- `pub fn my_public_function() { } `
**ref** - Creates a reference to a pattern inside a match.
```
match some_option {
    Some(ref value) => println!("{}", value),
    None => println!("None"),
}
```
**return** - Exits a function and returns a value.
**Self** - Refers to the type implementing that current trait or method.
```
impl MyStruct {
    fn new() -> Self {
        MyStruct {}
    }
}
```
**self** - Refers to the current instance of a struct or enum inside an impl block.
**static** - Defines a global variable with a static lifetime.
- `static MAX_POINTS: u32 = 1000;`
**struct** - Declares a structure, which is a custom data type with named fields.
```
struct Point {
	x: i32,
	y: i32,
}
```
**trait** - Declares a trait, which is a collection of methods than types can implement.
```
trait Printable {
    fn print(&self);
}
```
**true** - A boolean literal representing true.
**type** - Defines a type alias.
- `type Kilometers = i32;`
**unsafe** - Allows code that bypasses Rust's safety gurantees.
```
unsafe {
    let raw_pointer = &10 as *const i32;
}
```
**use** - Imports items from a module.
- `use std::io;`
**where** - Adds constraints to generic types.
```
fn my_function<T>(t: T)
where T: Display {
    println!("{}", t);
}
```
**while** - Executes a block of code while a condition is true.
- `while x < 5 { } `
**yield** - Pauses a generator and returns a value, used in asynchronus contexts (unstable feature).
- `yield value;`
**super** - Refers to the parent module in the module heirarchy.
- `use super::parent_module_function;`
## Rust Mechanics
### Implementations (impl)
### Trait Objects
**What is a Trait** - A trait is a way to define shared behaviors, similar to an interface in other languages.
