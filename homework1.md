#Homework 1

## Problem 1

####(a) 

`(r ^ ~s) -> p` is equivalent to 

“If the Moon is out and it is **not** snowing, then Phyllis goes out for a walk.”

####(b)

`r -> (~s -> p)` is equivalent to

"If the Moon is out, then it is the case that if it is **not** snowing, then Phyllis goes out for a walk."

####(c)


`~(p <-> (s v r))` is equivalent to

"It is **not** the case that Phyllis goes out for a walk **if and only if** it is snowing or the Moon is out."

## Problem 2

####(a)

`p ^ ~(p -> q)`

| p | q | p->q | ~(p->q) | p^~(p->q)
--- | --- | --- | --- | --- |
| 0 | 0 | 1 | 0 | 0
| 0 | 1 | 1 | 0 | 0 
| 1 | 0 | 0 | 1 | 1
| 1 | 1 | 1 | 0 | 0

####(b)

`(p <-> ~(q v r)) ^ (r -> q)`

| p | q | r |qvr | ~(qvr) | p<->~(qvr) | r->q | (p<->~(qvr))^(r-> q)
--- | --- | --- | --- | --- | --- | --- | --- 
| 0 | 0 | 0 | 0 | 1 | 0 | 1 | 0
| 0 | 0 | 1 | 1 | 0 | 1 | 0 | 0
| 0 | 1 | 0 | 1 | 0 | 1 | 1 | 1
| 0 | 1 | 1 | 1 | 0 | 1 | 1 | 1
| 1 | 0 | 0 | 0 | 1 | 1 | 1 | 1
| 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0
| 1 | 1 | 0 | 1 | 0 | 0 | 1 | 0
| 1 | 1 | 1 | 1 | 0 | 0 | 1 | 0

## Problem 3

#### (a)
`~(p <-> s)`

| p | s | p<->s | ~(p<->s) 
--- | --- | --- | --- 
| 0 | 0 | 1 | 0
| 0 | 1 | 0 | 1 
| 1 | 0 | 0 | 1
| 1 | 1 | 1 | 0

#### (b)

`(~p) <-> (~s)`

| p | s | ~p | ~s | (~p) <-> (~s) |
--- | --- | --- | --- | --- 
| 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 1 | 0 | 0| 
| 1 | 0 | 0 | 1 | 0
| 1 | 1 | 0 | 0 | 1

#### (c)
`p <-> s`

| p | s | p<->s 
--- | --- | --- 
| 0 | 0 | 1 
| 0 | 1 | 0 
| 1 | 0 | 0 
| 1 | 1 | 1 

#### (d)

`(~p) <-> s`

| p | s | ~p | (~p)<->s 
--- | --- | --- | ---
| 0 | 0 | 1 | 0
| 0 | 1 | 1 | 1 
| 1 | 0 | 0 | 1
| 1 | 1 | 0 | 0

#### (e)

`p <-> (~s)`

| p | s | ~s | p<->(~s)
--- | --- | --- | ---
| 0 | 0 | 1 | 0
| 0 | 1 | 0 | 1 
| 1 | 0 | 1 | 1
| 1 | 1 | 0 | 0

#### conclusion

One way to negate a biconditional is to negate one of the conditions.

## Problem 4

Prove `~((a ^ b) ^ c) === ~a v (~b v ~c)`

```
~((a ^ b) ^ c)      # given
=== ~(a ^ b) v ~c   # demorgan's
=== (~a v ~b) v ~c  # demorgan's
=== ~a v (~b v ~c)  # associative law
```

## Problem 5

#### (a)

Prove `p -> (r -> p) === True`

```
p -> (r -> p)     # given
~p v (r -> p)     # eliminate implication
~p v (~r v p)     # eliminate implication
(~p v p) v ~r     # associative law
True v ~r         # negation law
True              # domination law
```

#### (b)

Prove `(p -> r) v (r -> p) === True`

```
(p -> r) v (r -> p) # given
(~p v r) v (r -> p) # eliminate implication
(~p v r) v (~r v p) # eliminate implication
(r v ~r) v (p v ~p) # associative law
True v True         # negation law
True
```

#### (c)

Prove `r -> (p -> (r -> p)) === True`

```
r -> (p -> (r -> p))  # given
~r v (p -> (r -> p))  # eliminate implication
~r v (~p v (r -> p))  # eliminate implication
~r v (~p v (~r v p))  # eliminate implication
(~p v p) v (~r v ~r)  # associative law
True v False          # negation law
True
```

## Problem 6

Prove that `p ^ (p v t) === p`

```
p ^ (p v t)            # given
(p v False) ^ (p v t)  # p === p v False
p v (t ^ False)        # reverse distributive laws
p v False              # domination law
p                      # domination law
```

## Problem 7 

Prove that `p <-> q === (~p ^ ~q) v (p ^ q)`

```
p <-> q                                       # given 
(p -> q) ^ (q -> p)                           # eliminate biconditional
(~p v q) ^ (~q v p)                           # eliminate implication
((~p v q) ^ ~q) v ((~p v q) ^ p)              # distributive law
((~p ^ ~q) v (q ^ ~q)) v ((p ^ ~p) v (q ^ p)) # distributive law
((~p ^ ~q) v False) v ((q ^ p) v False)       # negation law
(~p ^ ~q) v (p ^ q)                           # domination law
```

## Problem 8

#### (a)

Prove:

```
p ^ q
q -> (r ^ s)
-----------
r
```

Solution:

```
1. p ^ q        # Given
2. q -> (r ^ s) # Given
3. q            # Simplification, 1
4. r ^ s        # Modus Ponens, 2, 3
5. r            # Simplification, 4
```

#### (b)

Prove:

```
p -> (~s ^ r)
s v t
p
------
t
```

Solution:

```
1. p -> (~s ^ r)  # Given
2. s v t          # Given
3. p              # Given
4. ~s ^ r         # Modus ponens, 1, 4
5. ~s             # Simplification, 4
6. t              # Disjunctive syllogism, 2, 5
```

#### (c)

Prove:

```
(~p v s) <-> q
~q
------
p
```

Solution:

```
1. (~p v s) <-> q                     # Given
2. ~q                                 # Given
3. ((~p v s) -> q) ^ (q -> (~p v s))  # Equivalent to 1
4. (~p v s) -> q                      # Simplification, 3
5. ~(~p v s)                          # Modus tollens, 2, 4
6. ~(~p) ^ ~s                         # Equivalent to 5
7. ~(~p)                              # Simplification, 6
8. p                                  # Equivalent to 7
```