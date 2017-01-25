# The Basics

## Running Scala programs

```
scalac MyModule.scala
scala MyModule
```

or

```
scala MyModule.scala
```

or

```
scala
scala> :load MyModule.scala
scala> MyModule.abs(-42)
```

## Importing

* We can bring an object’s member into scope by importing it, which allows us to call it unqualified from then on:

```
scala> import MyModule.abs
scala> abs(-42)
```

* We can bring all of an object’s (non-private) members into scope by using the underscore syntax:

```
import MyModule._
```

* It’s common in Scala to write functions that are local to the body of another function. In functional programming, we shouldn’t consider this a bigger deal than local integers or strings.

## Defining variables

* val: (value) single assignment, cannot be changed or reassigned

* var: (variable) reassignable

* defaulting: Can use _ to assign default value when initial value not available until later, but types must be explicitly provided:

```
scala> var something:String = _
something: String = null
``` 

* lazy evaluation: the value of the vairable wont be evaluated until first use

```
scala> lazy var something = somethingThatTakesALotOfTime()
```


---
up to page 52. 2.2.3 Defining Functions

