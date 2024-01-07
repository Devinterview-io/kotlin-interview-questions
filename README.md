# 100 Important Kotlin Interview Questions

<div>
<p align="center">
<a href="https://devinterview.io/questions/web-and-mobile-development/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fweb-and-mobile-development-github-img.jpg?alt=media&token=1b5eeecc-c9fb-49f5-9e03-50cf2e309555" alt="web-and-mobile-development" width="100%">
</a>
</p>

#### You can also find all 100 answers here 👉 [Devinterview.io - Kotlin](https://devinterview.io/questions/web-and-mobile-development/kotlin-interview-questions)

<br>

## 1. What is _Kotlin_ and how does it interoperate with _Java_?

**Kotlin** is a modern, statically typed language. Having been developed by JetBrains, it targets the JVM, among other platforms.

### Key Strengths of Kotlin on JVM

- **Concise Syntax**: Kotlin's compact code minimizes boilerplate.
- **Null Safety**: With its nullable types, Kotlin helps reduce null-pointer exceptions.
- **Extension Functions**: These functions simplify class extension.
- **Coroutines**: Kotlin's lightweight threads make asynchronous operations more manageable.
- **Immutability**: Kotlin has built-in support for immutable structures through 'val'.

### Core Java-Kotlin Interoperability Mechanisms

**Kotlin** can use Java Frameworks and libraries. Plus, it offers mechanisms for both Java-to-Kotlin and Kotlin-to-Java interoperability.

These mechanisms include:

1. **Kotlin Libraries and Frameworks**: They are tested to work with Java.
2. **nullability Roadmap and @Nullable/@NotNull Annotations**: One can take advantage of both Kotlin's null-safe types and Java's nullability guidelines.
3. **Supportive Native Tools**: Kotlin paves the way for Android development with libraries compatible with Java.
4. **Instrumented and Standard Libraries**: Both libraries have Kotlin origin.  It offers the convenience of unifying coding styles and tools.  The 'kotlin.jvm' package is tailored for standard Java operations.

### Common Scenarios for Java-Kotlin Interoperability

- **Migrating Codebases**: Gradual transitions are possible. Both languages can interoperate within a single project.
  
- **Collaborative Development**: Team members who prefer different languages can still contribute to the common codebase.

- **Libraries and Frameworks**: Leveraging Java libraries in a Kotlin-based system is seamless.

- **Android Development**: Kotlin has been officially backed by Google as a primary language for Android app development.

- **VM and Platform Independence**: Kotlin's multi-platform capabilities allow functionality sharing across different platforms.

### Java-Kotlin Code Example: Interoperability

Here is the Java class:

```java
public class Fruit {
    private String name;
    private int quantity;

    public Fruit(String name, int quantity) {
        this.name = name;
        this.quantity = quantity;
    }

    public String getName() {
        return name;
    }

    public int getQuantity() {
        return quantity;
    }

    public void setName(String name) {
        this.name = name;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }
}
```

And here is the Kotlin class that uses the `Fruit` Java class:

```kotlin
fun main() {
    val apple = Fruit("Apple", 10)  // Use of Java class
    println("Name: ${apple.name}, Quantity: ${apple.quantity}")

    apple.name = "Green Apple"      // Kotlin syntax for modifying Java object
    apple.quantity += 5

    println("Updated Apple: Name - ${apple.name}, Quantity - ${apple.quantity}")
}
```
<br>

## 2. How does _Kotlin_ improve upon _Java_ for _Android development_?

**Kotlin**, a statically-typed language, provides several benefits over Java in the context of Android development.

### Improved Developer Experience

- **Intuitive Syntax**: Kotlin reduces boilerplate code, leading to more elegant, succinct, and readable codebases.
- **Extension Functions**: This language feature allows developers to extend specific types with new functionalities.

### Enhanced Productivity

- **Null Safety**: The type system in Kotlin differentiates between nullable and non-nullable references, effectively reducing `NullPointerException` occurrences.
- **Smart Casting**: The language's type inference allows automatic casting of types wherever possible, thereby eliminating the need for explicit casting.
- **Coroutines**: Kotlin's built-in support for coroutines makes asynchronous programming simpler and less error-prone.

### Modern Language Features

- **Lambdas**: Kotlin's support for concise yet powerful lambda expressions outstrips that of Java.
- **Data Classes**: These classes, which Kotlin can generate getters, setters, `equals()`, and other basic methods automatically make working with models more streamlined.
- **Type Inference**: The language can often discern the type of a variable from its value, thus alleviating the need for explicit type declarations.

### Compatibility with Java

- **Interoperability with Java**: Kotlin integrates seamlessly with existing Java code, allowing for easy migration and coexistence.
- **Full Java SDK Support**: Kotlin is fully compatible with the Java SDK, enabling access to the plethora of Java libraries from Kotlin projects.

### Enhanced Safety and Accuracy

- **Immutability by Default**: In Kotlin, variables are, by default, immutable (read-only). This approach is conducive to preventing bugs and improving code safety.
- **Parameterized Contracts**: The `where` clause in Kotlin ensures more robust compile-time checks for generic types.
- **Range and Step Constructs**: These features enhance data accuracy and prevent out-of-bounds access.
<br>

## 3. What are the basic types in _Kotlin_?

**Kotlin** has a rich set of built-in data types tailored for various uses. They are mostly categorized into **Primitive** and **Object** data types.

### Basic Types Categories

#### **Primitive Types**

**Kotlin** introduces the following **Primitive** types:
- `Double`: Double precision 64-bit floating point number.
- `Float`: Single precision 32-bit floating point number.
- `Long`: 64-bit integer.
- `Int`: 32-bit integer.
- `Short`: 16-bit integer.
- `Byte`: 8-bit integer.
- `Char`: A single 16-bit Unicode character.
- `Boolean`: Represents truth values: true or false.

#### **Object Types**

These are **Object** types:

- `String`: A sequence of characters.
- `Any`: The root of the Kotlin class hierarchy. This is the equivalent of `Object` in Java.

#### Other Types

- `Array`: A class for array types.
- `Function`: A function type, which is determined by its parameter types and return type.

You can have a look at the Kotlin code.

Here is the Kotlin code:

### Code Example: Kotlin Types

```kotlin
fun main() {
    val doubleNum: Double = 100.0
    val floatNum: Float = 100.0f
    val longNum: Long = 100
    val intNum: Int = 100
    val shortNum: Short = 100
    val byteNum: Byte = 100
    val charLetter: Char = 'A'
    val isRainingToday: Boolean = true
    val text: String = "Hello, Kotlin!"

    val anyValue: Any = "This is an example of Any type in Kotlin"

    val intArray: Array<Int> = arrayOf(1, 2, 3, 4, 5)
    val strArray: Array<String> = Array(5) { "Item #$it" }

    fun myFunction(num: Int): Boolean {
        return num % 2 == 0
    }

    val myFunctionType: (Int) -> Boolean = ::myFunction
}
```
<br>

## 4. Explain the difference between `val` and `var` in _Kotlin_.

In Kotlin, the keywords `val` and `var` are used for **variable declaration**, each with distinct mutability characteristics.

### Immutable with `val`

`val`, akin to `final` in Java, denotes an **immutable reference**. This means after its initial assignment, the reference doesn't change. However, the state of the object or type it points to can still be altered.

### Mutable with `var`

`var` designates a **mutable reference**. This type of variable allows both reassignment and potential state changes during its lifecycle.

### Tips for Usage

- **Prefer `val`**: Use it unless there's a compelling reason for mutability. This practice aligns with Kotlin's design for immutability.
  
- **Mutable Limited**: In production code, restrict mutability with `var` to situations where its necessity is clear and justified.

### Code Example: `val` and `var`

Here is the Kotlin code:

```kotlin
fun main() {
    val PI = 3.14159  // Immutable PI, defined with val
    var count = 0     // Mutable count, defined with var
  
    // Following lines lead to compiler errors
    PI = 3.14       // Cannot reassign PI as it's declared with val, not var
    count = 1       // OK! Reassignment of a variable defined with var is allowed
}
```
<br>

## 5. How do you create a _singleton_ in _Kotlin_?

In Kotlin, defining a **singleton** is straightfoward; the language provides a dedicated `object` keyword.

When you declare a companion object in a class, it becomes a singleton accessible through the class name. This is useful for creating global handles.

### Singleton Using `object` Keyword

- **Kotlin Code**:  

```kotlin
object MySingleton {
    fun someFunction() {
        // Logic here
    }
}
```

- **Access**:

  ```kotlin
  MySingleton.someFunction()
  ```

### Singleton through `Companion Object`

- **Kotlin Code:**  

  ```kotlin
  class MySingletonClass {
      companion object {
          fun someFunction() {
              // Logic here
          }
      }
  }
  ```

- **Access**:

  ```kotlin
  MySingletonClass.someFunction()
  ```

### Why Use `object` over `companion object`?

If a class doesn't require an instance or has a single instance throughout the application, `object` is the most succinct and expressive solution.

In contrast, `companion object` is suitable when non-static methods or properties need to interact with the singleton. It's pertinent to classes you instatiate but have a single instance for per application.

### `object` Versus Traditional Singletons

Kotlin's `object` offers several advantages over **traditional singletons**, including automatic management of thread safety, lazy initialization, and streamlined syntax. It's a recommended approach for modern Kotlin development.

Traditional Java singletons also had complications with lazy initialization and thread safety, which are non-issues with Kotlin's `object`.

From a design standpoint, the single-responsibility principle should guide the decision to use singletons. Cohesiveness allows for consistency and predictability across the app.

### Key Takeaways:

- Kotlin's `object` keyword is the most straightforward way to create singletons.
- `companion object` is appropriate for singletons tied to the containing class where both need to be instantiated.
- Kotlin's `object` is a modern, expressive alternative to the verbosity and potential issues of traditional Java singletons.
- Threading and resource management are handled seamlessly, simplifying code.
<br>

## 6. What are the _Kotlin type inference_ rules?

Kotlin **type inference** represents a powerful feature that automatically determines variable types. Nonetheless, it does so within the constraints of **Kotlin's Type Hierarchy**.

- Kotlin types are static, meaning they're determined at compile time.
- The Kotlin compiler analyses assignments and method calls to infer types.
- When there are multiple possible types, the compiler selects the most specific one. In case of ambiguity, the code will not compile, and a **type annotation** is needed to provide clarity.

Kotlin also supports **type inference** with:

- **Lambda expressions**
- **Generics**

The Kotlin compiler uses both the **expected type** and the **inferred type of the arguments** to infer the type of both return value and the arguments of the `run` and 'let' extension function.

### Type Inference With Lambdas

In Kotlin, you can use `it` as shorthand for a single lambda parameter. Type inference deduces the type based on the context in which the lambda is used.

The `list` argument is expected to be a list of strings, allowing `it` to be inferred as a `String`. Consequently, the type of `length` is inferred as `Int`.

#### Code Example: Type Inference With Lambdas

Here is the Kotlin code:

```kotlin
fun main() {
    val names = listOf("Alice", "Bob")

    // Infers `it` as String
    val lengths: List<Int> = names.map { it.length }

    println(lengths)  // Output: [5, 3]
}
```
<br>

## 7. Can _Kotlin code_ be executed without a `main` function?

While it is essential to have a `main` function to initiate an application in most programming languages, **Kotlin** offers the flexibility to apply direct execution to standalone code.

### Direct Execution in Kotlin

The directive to execute code without a `main` function is termed **script mode** and is enabled using the following steps:

1. Define a build and execution environment through the Kotlin compiler or the IntelliJ IDEA.
2. Ensure that the script file has **.kts** or **kotlin-script** extension to indicate it's a Kotlin script.

This adaptation simplifies rapid prototyping and facilitates learning and testing in sandbox environments. Nonetheless, it's important to note that traditional Java applications, as well as Android applications, still necessitate a `main` function.
<br>

## 8. What is the purpose of the `Unit` type in _Kotlin_?

While some languages use "void" to indicate functions or expressions with no useful return value, **Kotlin** leverages the Unit type.

### Why Kotlin Introduced 'Unit'

The driving principle behind introducing the `Unit` type was to provide a unified approach to functions across the **object-oriented** and **functional** programming paradigms.

### Key Characteristics of `Unit`

- **Singleton Element**: `Unit` is a singleton, meaning there's only one instance of it. This allows functions with **no explicit return** to be understood as returning a single, distinct value.
- **Immutable State**: As a singleton, `Unit` is inherently immutable, ensuring that every function call returning `Unit` produces the same fixed value.

### Use Cases

1. **Functionality Communication**: `Unit` serves as a clear signal that a function is invoked strictly for its side effects.
2. **Interface Alignment**: Codebases aiming for consistency can utilize `Unit` to harmonize function return types.

### Code Example: Unit in Functions

Here is the Kotlin code:

```kotlin
// Function with explicit Unit return type
fun greet(name: String): Unit {
    println("Hello, $name!")
}

// Function without explicit return type defaults to Unit
fun performTask(): Unit {
    // Task logic goes here
}

// Function with no explicit return type
fun noReturn(): Nothing? {
    // Code that will never execute
    throw NotImplementedError()
}

fun main() {
    // All three function calls here can be understood as returning Unit
    greet("Alice")
    performTask()
    println(noReturn()) // Will not print anything
}
```

In this code, `greet("Alice")`, `performTask()`, and `println(noReturn())` are all implicitly equated to `Unit` return types. The "MessageBox" would close after 12 seconds without the output.
<br>

## 9. How do you perform _string interpolation_ in _Kotlin_?

In Kotlin, you can **interpolate** strings using the `$` symbol. This mechanism allows for the direct embedding of variables, expressions, and Math operations within a string.

Alternatively, you can leverage **raw strings** with the `trimMargin` method for multi-line text.

### Code Example: String Interpolation

Here is the Kotlin code:

```kotlin
fun main() {
    val name = "Alice"
    val age = 25

    println("Name: $name, Age: $age")
    
    // Dollar sign within a string
    println("$$100: A Hundred Dollars")
    
    // Interpolated expression
    val tripleAge = age * 3
    println("In 3 years, $name will be ${age + 3} years old, and 3 times $age is $tripleAge")

    // Raw string with trimMargin
    val poem = """
        |Two roads diverged in a yellow wood,
        |And sorry I could not travel both
        |And be one traveler
        """.trimMargin()
    println(poem)
}
```

### Output

```
Name: Alice, Age: 25
$100: A Hundred Dollars
In 3 years, Alice will be 28 years old, and 3 times 25 is 75
Two roads diverged in a yellow wood,
And sorry I could not travel both
And be one traveler
```
<br>

## 10. What are _extension functions_ in _Kotlin_?

**Kotlin's extension functions** provide a convenient mechanism for adding methods to existing classes without altering their source code. This is especially useful for extending classes that are otherwise fixed or derive from external libraries, such as built-in types from Java.

### Benefits of Extension Functions

- **Improved Readability**: Extension functions enable adding context-specific methods to types.
  
- **Consistent Naming**: These functions ensure a standard naming convention for classes.

- **No Inheritance Issues**: Overriding is not a concern, making extension functions ideal for providing custom behavior to existing classes.
  
- **Modular Code**: Associates utility methods directly with the classes they operate on, streamlining code organization.

### Function vs. Method

In Kotlin, the term **"function"** typically refers to a top-level function, whereas the term **"method"** is used within the context of a class.

### Usage

1. **Importing Extension Functions**: Kotlin's standard library provides numerous extension functions. Additional extensions can be imported using the `import` directive.

2. **Working with Nullable Types**: Extension functions can be applied to nullable types to avoid invoking methods on `null`. By checking for `null` within the function, it ensures safe execution.

3. **Scoping**: Although extension functions resemble regular methods, their scoping is limited to the file where they are defined unless they are imported or are part of the same package.

4. **Inheritance**: When a class and its parent provide methods of the same name and signature, the class's own methods always take precedence.

   However, even when an extension function exists, classes and their derived types (e.g., subclasses) can override the functionality by defining methods with the same signature.

### Code: Extension Function on Nullable Type

Here is the Kotlin code:

```kotlin
fun String?.isNullEmptyOrBlank(): Boolean {
    return this == null || this.isEmpty() || this.isBlank()
}

fun main() {
    val text: String? = "Hello"
    val emptyText: String? = ""
    val blankText: String? = "   "

    println(text.isNullEmptyOrBlank())  // false
    println(emptyText.isNullEmptyOrBlank())  // true
    println(blankText.isNullEmptyOrBlank())  // true
}
```
In this example, `String?` is a nullable type, and the extension function **`isNullEmptyOrBlank`** checks for `null`, an empty string, or a string consisting entirely of whitespace.
<br>

## 11. How are `if` expressions used in _Kotlin_ as compared to _Java_?

While both Kotlin and Java use `if` **expressions** to conditionally execute code, Kotlin offers more power and flexibility with its `if` expression.

### Key Differences

- **Return Type**: In Java, you can only use `if` to conditionally execute statements. In contrast, Kotlin's `if` can also return a value, similar to the Ternary Operator in Java.
  
- **Immutability**: Kotlin's `if` is an expression that produces a value, and that value is immutable once assigned. However, in Java, variables assigned within each `if` block can have different values outside the block.

- **When to Use**: In Kotlin, the standard recommendation is to use `if` for simple or limited cases and use `when` for more complex and multifaceted scenarios.

#### Example: If-Else Expression

Here is the Kotlin code:

```kotlin
val result = if (condition) "Value1" else "Value2"
```

And here is the equivalent Java code:

```java
String result;
if (condition) {
    result = "Value1";
} else {
    result = "Value2";
}
```

### Best Practices

- **Kotlin Compactness**: Utilize Kotlin's concise syntax for improved readability and maintainability.
  
- **Type Inference**: In Kotlin, you may let the compiler infer the result type rather than explicitly defining it.
<br>

## 12. Explain `when` expressions in _Kotlin_.

In **Kotlin**, the `when` expression is a powerful control-flow construct that simplifies and enhances many operations.

It combines the best aspects of **conditional execution** and **pattern matching** from other languages like Java, C++, and Scala. This dynamic construct allows for complex evaluations in a concise, easy-to-read structure.

### Key Features

- **Branching**: Similar to `switch` statements, `when` evaluates different conditions and triggers corresponding code blocks.
- **Expression-based**: It works well in both code blocks and as standalone expressions.
- **Versatile Syntax**: It supports a broad range of matching techniques, such as value matching, range checks, and null safety operators.
- **Extensive Filtering**: Can evaluate conditions like type checks, boolean expressions, and custom checks.
- **Sealed Classes Support**: Seamlessly integrates with sealed classes, enforcing a comprehensive check of all possible subtypes.

### Code Example: Basic when-expression

Here is the Kotlin code:

```kotlin
fun describe(object: Any): String {
    return when (object) {
        1 -> "One"
        2 -> "Two"
        3, 4 -> "Three or Four"
        is String -> "That's a string"
        is Number -> "That's a number"
        else -> "Something else"
    }
}

fun main() {
    println(describe(1))
    println(describe(3))
    println(describe(5))
    println(describe("hello"))
}
```

When you run the above code, you will get the following output:

```plaintext
One
Three or Four
Something else
That's a string
```

### Code Example: Returning Booleans

Here is the Kotlin code:

```kotlin
fun isStringOrEmpty(input: Any?): Boolean {
    return when (input) {
        null -> true
        is String -> input.isEmpty()
        else -> false
    }
}

fun main() {
    println(isStringOrEmpty(null))
    println(isStringOrEmpty(""))
    println(isStringOrEmpty(123))
}
```

When you run the above code, you will get the following output:

```plaintext
true
true
false
```

### Advanced Example: Data Classes and Smart Casting

Here is the Kotlin code:

```kotlin
data class Person(val name: String, val age: Int, val email: String = "")

fun processPerson(person: Person) {
    when {
        person.age < 0 -> println("Invalid age!")
        person.name.isBlank() -> println("No name provided")
        person.email.isBlank() -> println("No email provided")
        else -> {
            println("All details provided:")
            println("Name: ${person.name}")
            println("Age: ${person.age}")
            println("Email: ${person.email}")
        }
    }
}

fun main() {
    val person1 = Person("Alice", 25, "alice@example.com")

    val person2 = Person("Bob", 30)
  
    val person3 = Person("", -10, "invalidemail")

    processPerson(person1) // Should print all details
    processPerson(person2) // Should print "No email provided"
    processPerson(person3) // Should print "Invalid age!"
}
```

- We define a data class, `Person`.
- The `when` block operates without an explicitly defined expression (commonly referred to as a "subject"). This feature allows for more intricate conditions and is known as a "subject-less `when`."
<br>

## 13. How does _Kotlin_ handle _null safety_ and what is the _Elvis operator_?

In Kotlin, **null safety** is a core feature designed to address the issues around null references. It aims to reduce `NullPointerException` errors that are commonly encountered in other languages, particularly Java.

The **Elvis Operator** provides a concise means for handling `null` values within expressions.

### Null Safety

Kotlin employs a set of rules to manage nullability in objects:

#### Nullable Types

- A type is marked as **nullable** if it can accept `null` values. This is indicated by appending `?` to the type name.

  ```kotlin
  val name: String? = null  // Nullable String
  ```

- If the `name` variable was not marked as nullable (e.g., `val name: String = null`), and you attempted to assign `null`, the Kotlin compiler wouldn't allow it.

#### Safe Calls

- To invoke a method or access a property on a nullable object, use the **safe call** operator `?.`. The method is called only if the object isn't `null`:

  ```kotlin
  val length: Int? = name?.length  // null if name is null
  ```

#### The Not-Null Assertion Operator

- When you're certain an object isn't `null`, you can use the **not-null assertion operator** `!!`.

  Be cautious with this operator. If the object turns out to be `null`, it will result in a `NullPointerException`.

  ```kotlin
  val l: Int = name!!.length  // Throws NPE if name is null
  ```

#### Safe Casts (as & as?)

- For type checks, Kotlin offers both the straightforward `is` operator and the **safe cast** `as?`. This safely casts an object to a type, returning `null` if the cast fails.

  ```kotlin
  val cat: Cat? = animal as? Cat  // null if animal isn't Cat
  ```

### The Elvis Operator: ?: 

The Elvis operator prompts Kotlin to return a non-null value or a **default** or **alternative** value if the operating object is null.

- It's presented as a double dot `?:`.
- The value on the left of the `?:` will be returned if it's not `null`. Otherwise, the value on the right will be the result:

  ```kotlin
  val length: Int = name?.length ?: -1  // If name is null, length is -1
  ```

Replace **null** values with appropriate defaults, simplifying code and handling absence scenarios.
<br>

## 14. What is a “smart cast” in _Kotlin_?

In Kotlin, a **smart cast** refers to the compiler's ability to automatically cast a variable under certain conditions. This feature significantly reduces code verbosity and casting overhead, ensuring code safety.

### How It Works

The smart cast is automatically applied after the compiler identifies a segment of code where a certain type check has been completed.

For example, consider the following code snippet:

```kotlin
fun processStringOrInt(obj: Any) {
    if (obj is String) {
        // here, `obj` is smart-cast to a `String`
        println(obj.length)
    } else if (obj is Int) {
        // here, `obj` is smart-cast to an `Int`
        println(obj - 1)
    }
}
```

### Code Analysis

- Within the `if` and `else if` blocks, **smart casts** are triggered. After these checks, the compiler automatically adjusts the type of `obj` for that code block.
- This mechanism eliminates the need for developers to manually cast `obj` within each conditional branch.

### Considerations & Limitations

- **Complexity**: While simple checks like type and `null` are direct matches, more complex contexts, such as generics, may not trigger smart casts in Kotlin.
- **Return Type Ambiguity**: In functions using smart casts, the return type can become ambiguous. If one branch of the condition returns a particular type, the compiler may not know for certain that the other branch never returns that type. This ambiguity can lead to compile-time errors.
- **Capture Scope**: Avoid modifying variables within the smart-cast-conditional blocks. Such modifications can disrupt the typing and lead to unexpected behaviors.

### Key Advantages

- **Code Conciseness**: Smart casts reduce the need for explicit type checks and casts, leading to cleaner and more readable code.
- **Error Prevention**: Smart casts help in avoiding potential errors related to type mismatches and nullability. Once a type is checked, the variable is guaranteed to be of that type within the corresponding code block.
<br>

## 15. How do you implement a custom _getter_ and _setter_ in _Kotlin_?

In Kotlin, you can **customize** property behaviors, including defining your own **custom getters** and **setters**.

### Syntax

Here is the syntax:

```kotlin
var <propertyName>[: <PropertyType>] [= <property_initializer>]
    get() = <custom_getter>
    set(value) { <custom_setter> }
```

### Example: Custom Getters/Setters for a `Temperature` Class

Let's take a look at the code:

#### Data Model - Temperature.kt

Here is the Kotlin code:

```kotlin
class Temperature {
    var celsius: Float = 0f
        get() {
            return (field * 9 / 5) + 32
        }
        set(value) {
            field = (value - 32) * 5 / 9
        }
    val fahrenheit: Float
        get() = celsius
}
```

#### Activity

Here is Java code:

```java
public class Main {
    public static void main(String[] args) {
        Temperature weather = new Temperature();
        weather.setCelsius(20);
        System.out.println("Temperature in Fahrenheit: " + weather.getFahrenheit());
    }
}
```
<br>



#### Explore all 100 answers here 👉 [Devinterview.io - Kotlin](https://devinterview.io/questions/web-and-mobile-development/kotlin-interview-questions)

<br>

<a href="https://devinterview.io/questions/web-and-mobile-development/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fweb-and-mobile-development-github-img.jpg?alt=media&token=1b5eeecc-c9fb-49f5-9e03-50cf2e309555" alt="web-and-mobile-development" width="100%">
</a>
</p>

