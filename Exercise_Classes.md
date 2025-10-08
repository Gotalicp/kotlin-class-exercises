# Kotlin Class & Inheritance Exercises

Welcome! These exercises will help you learn Kotlin classes, inheritance, and debugging skills.  
Click the exercise links to open them in the online Kotlin Playground.

## Exercise 1 – Broken Constructor

[▶ Open in Kotlin Playground](https://pl.kotl.in/cJHxJDeSe)

**Description:**  
Fix the class so that the `introduce()` method works and prints the correct name and age.

<details>
  <summary>🕵️ Hint (click to reveal)</summary>
  The constructor parameters aren't automatically stored as properties.  
  Try using `val` or `var` in the constructor.
</details>

<details>
  <summary>✅ Solution (click to reveal)</summary>

```kotlin
class Person(val name: String, val age: Int) {
    fun introduce() {
        println("Hi, I'm $name and I'm $age years old.")
    }
}

fun main() {
    val p = Person("Alice", 25)
    p.introduce()
}