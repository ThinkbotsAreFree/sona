


# sona

a scripting language

![](https://github.com/ThinkbotsAreFree/sona/raw/main/sona.png)

> *from an objective situation, a subjective perception emerges by subtraction. vectors express these contrasts.*



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



## core concepts

vectors are differences between things. vectors may have many dimensions.



### vectors

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

the first vector is from a male to a female of same age, the second vector is from a female to a younger male. these are anonymous vectors.

named vectors are constructed like this:

```
vec(younger)( age(-1) )
```



### semes

a seme is a minimal unit of meaning. a seme is defined only by its relations to other semes.

a relation between two semes is characterized by an N-dimensions vector that describes the relation.

the seme constructor is `seme`.

```
seme(queen king)( gender(-1) )
```

from `queen` to `king` means 1 step left on the `gender` dimension.

this is actually syntactic sugar for:

```
seme(queen king) vec(
    gender(-1)
)
```

the name of existing named vectors can be used.

```
seme(adult child) younger
```

from `adult` to `child` means `younger`.
