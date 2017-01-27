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

## Defining methods

```
def helloWorld():String = { "hello world" }
```

* The return type is optional (can be inferred).

* The return keyword is also optional.

* Methods can accept and return parameterised types:

```
scala> def toList[A](value:A) = List(value)toList: [A](value: A)List[A]
scala> toList(1)res16: List[Int] = List(1)
```

* Function literals (single-line functions) can be provided as parameters:

```
scala> val evenNumbers = List(2, 4, 6, 8, 10)
evenNumbers: List[Int] = List(2, 4, 6, 8, 10)

scala>  evenNumbers.foldLeft(0) { (a: Int, b:Int) => a + b }
res0: Int = 30

```
with type inference:

```
scala> evenNumbers.foldLeft(0) { (a, b) => a + b }
res0: Int = 30
```
with placeholders:

```
scala> evenNumbers.foldLeft(0) { _ + _ }
res0: Int = 30
```

---
up to page 59. 2.3 Working with Array and List

