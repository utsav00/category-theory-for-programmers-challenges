# Types and Functions

## What
- Simplest intuition for types: set of values  
Bool : {True, False}  
Char: {All Unicode Chars}
- Finite and Infintie sets

- A set of all sets? X
- There is a category of sets which is called **Set**
- In Set, objects are sets and morphisms (arrows) are functions

- Halting problem:
    - Extends all type by a special value called _bottom_ (\_|\_, or ⊥)
    - non terminating computation

`f :: Bool -> Bool` may return true or false or bottom

- Explicitly return bottom  
`f x = undefined` == ` f = undefined` because bottom is also a part of `Bool`

- Functions that may return bottom are called partial functions

## Mathematical Model

Describing Semantics of language:
- Operational Semantics - formalized idealized interpreter
    - informal operational reasoning - abstract machine
    - "run it" thrgouh the idealized interpreter
- Denotational Semantics - prove program by a mathematical theorem
    - `fact n = product [1..n]`
    - Couldn't use with real life problems - reading from a file, sending data across network
    - Enter "monads"; props to Eugenio Moggi
    - Formal proofs or correctness can be seemed important in mission critical softwares

## Pure and Dirty Functions
- A function that always return the same output for the same inputs is a pure function
- Monads help model different effects using only pure functions

## Types Examples
- Types are Set of things
1. Empty Set = `Void` in Haskell (not `void` in cpp)
- A type that's not inhabited by any values

`absurd :: Void -> a`
- polymorphic return type
- Can never call such a function because to call it you require a type that has a `Void` value but there aren't any
- The type `Void` represents falsity, and the type of the function absurd corresponds to the statement that from falsity follows anything, as in the Latin adage “ex falso sequitur quodlibet” translating to "from falsehood, anything". (verbatim)

2. Singleton Set
- Example - cpp `void`

```C++
int f44 {return 44;}
```
- It doesn't take "nothing" because that will be absurd (yes, reference to above)
- It takes a dummy value that only ever has one instance, so there's no need to mention it explicitly
- It's `()` (pronounced unit) in Haskell

```Haskell
f44 :: () -> Integer
f44 () = 44
```

- Many to one mapping when a function returns unit value

```Haskell
fInt :: Integer -> ()
fInt x = ()
# or
fInt _ = ()
```
- parametrically polymorphic

3. Two Element Set
- Boolean - True or False
- Functions to `Bool` are called predicates - `isAlpha` or `isDigit`