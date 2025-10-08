# Kotlin Class & Inheritance Exercises

Welcome! These exercises will help you learn Kotlin classes, inheritance, and debugging skills.  
Click the exercise links to open them in the online Kotlin Playground.

## Part 1 – Debugging Exercises
### Exercise 1 – Broken Constructor

[▶ Open in Kotlin Playground](https://pl.kotl.in/cJHxJDeSe)

**Description:**  
Fix the class so that the `introduce()` method works and prints the correct name and age.

<details>
  <summary>Hint (click to reveal)</summary>
  The constructor parameters aren't automatically stored as properties.  
  Try using `val` or `var` in the constructor.
</details>

<details><summary>✅ Solution (click to reveal)</summary>

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
```
</details>


### Exercise 2 – Wrong Inheritance

[▶ Open in Kotlin Playground](https://pl.kotl.in/jsFqx4un5)

**Description:**
Fix the Dog class so it correctly overrides `makeSound()`.

<details> <summary>Hint (click to reveal)</summary> The parent class must be `open` and the child class must use `override`. </details> <details> <summary>✅ Solution (click to reveal)</summary>

```kotlin
open class Animal {
    open fun makeSound() {
        println("Some sound")
    }
}

class Dog : Animal() {
    override fun makeSound() {
        println("Woof!")
    }
}
```
</details>

### Exercise 3 – Property Not Initialized

[▶ Open in Kotlin Playground](https://pl.kotl.in/NUzP5my7Q)

**Description:**  
Fix the Car class so printInfo() prints the correct brand.

<details> <summary>Hint (click to reveal)</summary>
  The `brand` property must be initialized in the constructor. 
</details> 
<details> <summary>✅ Solution (click to reveal)</summary>

```kotlin
class Car(val brand: String) {
    fun printInfo() {
        println("This is a $brand")
    }
}

fun main() {
    val c = Car("BMW")
    c.printInfo()
}
```
</details>

### Exercise 4 – Missing super() Call

[▶ Open in Kotlin Playground](https://pl.kotl.in/L8MQT_Z7a)

**Description:**  
The Mage class should inherit from Character correctly.

<details> <summary>Hint (click to reveal)</summary> 
  Child classes must call the parent constructor: `class Mage(name: String, ...) : Character(name)`. 
</details> 
<details> <summary>✅ Solution (click to reveal)</summary>

```kotlin
open class Character(val name: String) {
    fun status() {
        println("$name is ready!")
    }
}

class Mage(name: String, val mana: Int) : Character(name) {
    fun castSpell() {
        println("$name casts a spell using $mana mana!")
    }
}

fun main() {
    val m = Mage("Gandalf", 100)
    m.status()
    m.castSpell()
}
```
</details>

### Exercise 5 – Logic Bug in BankAccount

[▶ Open in Kotlin Playground](https://pl.kotl.in/FR_3A-NbQ)

**Description:**  
Add deposit() and fix withdraw() methods so balance updates correctly.

<details> <summary>Hint (click to reveal)</summary> 
  Deposit should add money, withdraw should subtract money if there’s enough balance.
</details> 
<details> <summary>✅ Solution (click to reveal)</summary>

```kotlin
class BankAccount(val owner: String, var balance: Double) {
    fun deposit(amount: Double) {
        balance += amount
    }

    fun withdraw(amount: Double) {
        if (amount > balance) {
            println("Not enough money")
        } else {
            balance -= amount
        }
    }
}

fun main() {
    val account = BankAccount("John", 100.0)
    account.deposit(50.0)
    account.withdraw(30.0)
    println(account.balance) // 120.0
}
```
</details>

## Part 2 – Creation Exercises

For the next tasks use a clean playground

### Exercise 6 – Player Class

[▶ Open in Kotlin Playground](https://play.kotlinlang.org)

Task:

Create a class Player with name (String) and level (Int)

Function levelUp() increases level by 1

Function printInfo() prints the player’s stats

<details> <summary>Hint (click to reveal)</summary> Use `var level` to allow updates. </details>

### Exercise 7 – Game Characters with Inheritance

[▶ Open in Kotlin Playground](https://play.kotlinlang.org)

Task:

Base class Character: name, health, status()

Subclasses:

Knight with strength and attack()

Wizard with mana and castSpell()

Override status() to print stats

<details> <summary>Hint (click to reveal)</summary> Remember to mark the base class and methods `open` for inheritance and `override` in children. </details>

### Exercise 8 – Car & FuelStation Interaction

[▶ Open in Kotlin Playground](https://play.kotlinlang.org)

Task:

Car class: brand (String), fuel (Double), drive(distance) subtracts fuel

FuelStation class: refuel(car, amount) adds fuel

Test driving and refueling in main()

<details> <summary>Hint (click to reveal)</summary> 
  Use `distance * 0.1` to reduce fuel. The `refuel()` method should modify the `car.fuel`.
</details>

### Exercise 9 – Abstract Shape

[▶ Open in Kotlin Playground](https://play.kotlinlang.org)

Task:

abstract class Shape with abstract fun area(): Double

Subclasses: Rectangle(width,height), Circle(radius) implementing area()

Create a list of Shape and print areas in main()

<details> <summary>Hint (click to reveal)</summary>
  Use `override fun area()` in each subclass. Use `Math.PI * radius * radius` for Circle.
</details>

### Exercise 10 – Mini RPG Combat (Challenge)

[▶ Open in Kotlin Playground](https://play.kotlinlang.org)

Task:

Base class Character with name, health, takeDamage(amount)

Subclasses:

Warrior with strength and attack(target)

Mage with mana and castSpell(target)

In main(), simulate a few turns of combat and print status

<details> <summary>Hint (click to reveal)</summary> 
  Make `takeDamage()` reduce `health`. `attack()` and `castSpell()` should call `takeDamage()` on the target. 
</details>