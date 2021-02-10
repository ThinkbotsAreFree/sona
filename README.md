


# sona

a scripting language

> *from an objective situation, a subjective perception emerges by subtraction. vectors capture these contrasts and react accordingly.*



## regular syntax

sona has a 100% regular syntax.

```
a(b c d(e f) g)
```

is like s-exp: `(a b c (d e f) g)`

```
a(b)(c d)
```

is like s-exp: `((a b) c d)`



## underlying core concepts

### semes

a seme is a minimal unit of meaning. a seme is defined only by its relations to other semes.

a relation between two semes is characterized by an N-dimensions vector that describes the relation.

```
                 gender   rarity   ...
king-queen       +1       =0
king-man         =0       -1
king-woman       +1       -1
queen-king       -1       =0
queen-man        -1       -1
queen-woman      =0       -1
man-king         =0       +1
man-queen        +1       +1
man-woman        +1       =0
woman-king       -1       +1
woman-queen      =0       +1
woman-man        -1       =0
```

vectors are transitive.



### atoms

semes are like archetypes, classes, or models.

atoms are instances of semes.



### dimensions

the dimension constructor is `dim`.

the vector constructor is `vec`.

```
dim(
    gender(male female)
    age(young adult old)
    species(dog cat cow)
)

vec( gender(1) )

vec(
    gender(-1)
    age(-1)
)
```

the first vector is from a male to a female of same age, the second vector is from a female to a younger male.



### entities

the seme constructor is `seme`.

```
seme(king queen)(
    gender(1)
)
```

the difference between a `king` and a `queen` is `gender`. 

```
seme(older younger)(
    age(-1)
)
```

from `older` to `younger` means 1 step left on the `age` dimension.
