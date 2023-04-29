# Category: The Essence of Composition

## Arrows
- Arrows also called morphisms

So,
A -> B is `f(A) = B`; where A and B are objects but also types

B -> C would be `g(B) = A`

There must also be an arrow that goes from A -> C => function composition

Input: A  
Output: C

```
h(A) = C
h = g(f(A)) ; g ∘ f (in maths)
```

## Properties of Composition
- Associativity  
`h ∘ (g ∘ f ) = (h ∘ g) ∘ f = h ∘ g ∘ f`

- Identity function  
`id :: a -> a`

## Composition
- Decompose problems, solve them and compose them back again
- Right chunks for composition of programs?
    - surface area has to increase slower than their volume
    - a < a^2 < a ^3
- Surface Area: Information to compose chunks: objects or abstact interface in OOP and functions in FP
- Volume: Information to implement chunks