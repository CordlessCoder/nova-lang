# nova-lang

![Screenshot](nova-logo.png)

Programming lang WIP

Enjoy this demo!

```swift
// Type declaration
struct Person {
    name: String,
    age: Int,
}

// Hello world
println("hello world!")

// Creating instance of type
let person : Person = Person {name = "bob", age = 42}
let person2 : Person = Person("joe", 50)

// Function for type
fn display(self: Person) {
    println(self.name)
    println(self.age)
}

// Using function
person.display()
display(person2)

// For loop
let i = 0
for i = 0; i < 10; i += 1 {
    println(i)
}

using "../std/list.nv"

// Array
let arr = [1,2,3]
println(arr)

let arr2 = []: Int.list::fill(10,5)
arr2.println()

let arr3 = list::initList(10,5)
arr3.println()
 
arr[1] = 4
println(arr)

// Changing struct value
person.name = "bingo"
person.display()


struct Zed {
    test: ()
}

// Creating an instance from a type
let zed = Zed {
    test = fn() {
        print("wow\n")
    }
}

// Now we can access its namespace and call functions directly
zed::test()

// Using iterators
using "../std/iter.nv"

let myIter = [1,2,3,4,5]
    .iter::create()
    .iter::map(fn(x:Int)->Int{return x * x})

myIter
    .iter::printIter()

// Function pointers
struct SomeFunction {
    function: (Int,Int) -> Int
}

let myMul = SomeFunction(fn(x:Int,y:Int)->Int {
    return x * y
})

let myOtherFunc = myMul.function
let simpleSquare = fn(x: Int) -> Int {return x * x}

// Calling function pointer from a struct
(myMul.function)(4,99).println()
myMul::function(4,99).println()

// Support for most escape chars
print("hello again!\n")

myOtherFunc(4,7).println()

let myIterTwo = [1,2,3,4,5]
    .iter::create()
    .iter::map(simpleSquare)
    .iter::map(simpleSquare)
    .iter::collect()

println(myIterTwo)
```