## Scala : FP + OOP on JVM

### Introduction to Scala
Scala is a language combining obeject-oriented and functional programming languages. The Scala tutorial is very similar to Learn You A Haskell For a Great Good. Some of its basic grammar is so close to haskell so it is easy for people with some haskell experience to learn basic scala. Scala runs on JVM, so it competes with Java nowdays. The main benefit of Java is that it modulize programmer's work so it is popular in big companies. However Java tries to make every programmer the same with little variety. On the contrary Scala allows smart programmers write better code and thus outcome others. The most famous application written by Scala is Spark, an open-source distributed general-purpose cluster-computing framework for manipulating big-data. It is well-known for its efficiency and good community environment. 

#### What kind of people might want to learn Scala? 
People using JAVA but found it awkward or just don't like JAVA but have to design programs running on JVM might give a try to Scala.

#### How similiar is Haskell and Scala?
The father of scala had a joke that "Scala is a gateway drug to Haskell". Beginners might found it is very similar to haskell but when you look into them you'll find they are different in a lot of ways.

#### How is Scala in finding a job?

### Scala's FP paradigm

#### An Overview Fomr a Example : insertionSort
``` scala
  def insertionSort(xs: List[Int]) : List[Int] = xs match{
    case List() => List()
    case y :: ys = insert(y, insertionSort(ys))
  }
  
  val cond: (Int, Int) => Boolean = (x: Int, y :Int )=> if (x <= y) true else false
  
  def insert(x: Int, xs : List[Int]) : List[Int] =
    xs match {
      case List() => x :: List()
      case y :: ys  =>
        if(cond(x, y)) x :: y :: ys
        else y :: insert(x, ys)
    }
```
Looks familiar? From keyworkd "case" "=>", type declaration, List types, if else condition, we can easily figure out what is was doing, and I will go over the possible confusing statements one by one
- **lexical scope**
In scala, a {} block can be treated like an expression, with value as its last expression. For example :
``` scala
var x = {
    val y = 3
    y * y
}
```
The final result of x is 9 in this case. This can help you understand a lot of scala code for the first time.

- **pattern match**
a match sentence is an "expression" just as "1 + 1" and has its value.

- **val function**
Usually, val is used to define a variable like **val x = 10**, however in scala we can also treat functions as variables, only that "val" cannot change the function it points to. Here we use val to define a function cond, and it has type declaration. But what is the difference between "val", "def" ? This is one of the frequently asked questions from Scala beginners. The major difference is that "def function" are created when called each time (the Function1 instance), however val evaluates when defined. In most cases, the difference between them is not important as a beginner. To see more of this, try Scala's Function Objects.

- **type declaration**
In scala, we use : to add type declarations to a function, a parameter, or a return value. It is not compulsory to give type declaration for a function because the scala have implicit type inference.

#### Higher Order Functions & lambda
higher order function (or first-class function) are important in functional programming. In scala, we can use a function like this:
``` scala
  def sum(f: Int => Int, a: Int, b: Int) : Int =
    if (a > b) 0
    else f(a) + sum(f,a+1,b)
    
  def sumSquare(a: Int, b: Int) : Int = sum((x:Int) => x * x, a, b)
```
lambda expression(anonymous function) are written like "(x: Int) => x * x". Very familiar isn't it? Just like what we did in haskell.

#### Lazy Evaluation in Scala
Like haskell, scala has lazy evaluation too. In haskell a very useful calss is "Stream" (like generator in python), when defining an infinite stream, we will not evaluate it unless we really needed some of it os value.

``` scala
class Stream[+T]{
    def filter(p: T => Boolean): Stream[T] = 
        if(isEmpty) this
        else if (p(head)) cons(head, tail.filter(p))
        else tail.filter(p)
}
```

#### List Comprehension
``` scala
    val list_a = List(1,10,100)
    val something = for(a <- list_a if a > 10)
    
    // something = List(100)
```

#### Scala's OOP and imperative programming
Just like most OOP languages such as C++, Java, Python, scala use classes to offer data package and user interface. A general class is defined and created using operator "new"
``` scala
class Person(name_value: String, age_value: Int){
    def name = name
    def age = age_value
}
// Person is a constructor for this class

var affe = new Person("affe", 18)
```
also we can add member functions just like we do in C++. We can also add "private", "public" keyword in front of each attribute, this is useful in derived classes. You can do operator override in a certain class. Here I want to introduce abstract class(remember pure virtual function in C++ ?). An abstract class is defined using "abstract" keyword like this.
``` scala
abstract class Shape{
    def area() : Int
}
```
And the derived class are declared using "extends" just like in Java. In scala, any user-defined class extends to another class. Scala has dynamic binding too (like in almost every OOP language)to offer support to polumorphism, which we will talk about later. To support multi-inheritance, scala use "traits", a class can inherit from atmost one class but arbitary traits.

#### polymorphic types & type bounds
scala's polymorphism is based on type inference. But there is something interesting called type bound to a type variable. A type bound defines the possible type it can be inferred as. For example.
``` scala
def selection[A <: Animal](a1: A,a2: A):A = 
    if(a1.fitness > a2.fitness) a1 else a2
```
in this case, A <: type_b means A is a sub-type of type_B, or on the otherhand, A is a supertype of type_b if A >: type_b. Also we can contrain type to a certain type classes just like in Haskell using operator [].

### Scala's Type system

#### static typing
Scala is a strongly statically typed language. 

#### scala's type classes 
Just like haskell, scala has type class as well. And it is defined using type variable.

``` scala
  def insertionSort[T](xs: List[T])(implicit ord: Ordering[T]): List[T] = {
  def insert(y: T, ys: List[T]): List[T] =
    … if (ord.lt(y, z)) …

  … insert(y, insertionSort(ys)) …
}
```
#### Scala function types

#### scala's wrapper?(Maybe in haskell)

#### Scala's Memory Management
scala using GC to manage memory. 

### Other Interesting Features

#### Sparks

### Conclusion

#### What's good in scala
Scala is not treating programmer as machines.It serves the smart people, and programmers can choose among a whole bunch of tools to decide what they really want to do. They can use mutable or immutable data structures as they want and then optimizing them in terms of algorithms. Also, compared with Java, scala tries to trust how their programmer can optimize their program in scala. Scala can be very efficient if you take time to reform your code. However most Java won't let you do so because the modulization.

#### What's bad in scala
Scala is not widely used, partly because ... it is too difficult( close to C++). Programmers will take efforts to undertand Scala and use it in an efficient way compared with Java. On the other hand, Java offer great libraries, and in some big companies their fundamental codes were built in Java and reform them is really difficult. Since Java is still the most used language in the world, everyday new tools come out in forms of Java and Scala is not as good as Java definitely.

#### Why not using C++ if you want efficiency?
Because there are already a lot of good tools and programs running on JVM. Nobody wants to start from the very beginning.

#### How is scala developing
All functional programming are generally easy to code in concurrent context, and so is Scala. Technically, Scala has already shown its power in data science and cloud computing. We can see that in Java 8 and later version it included more FP features. On the other hand, Scala can be extended infinitely in theories and is used in famous universities. The only disadvantage is project management in large scale programming. However more and more scala users are contributing to the community with CI , automated-test and a whole bunch of tools.In the near future, scala will take important role on JVM.
