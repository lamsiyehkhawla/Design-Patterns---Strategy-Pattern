# Strategy Pattern - Java Example

## Description

This project demonstrates the **Strategy Design Pattern** in Java.
The Strategy Pattern allows changing the behavior of a program **at runtime** by selecting different strategies.

Instead of using many `if/else` statements, each behavior is implemented in a separate class.

---

## Project Structure

### 1. Strategy (Interface)

Defines the common method that all strategies must implement.

```java
public interface Strategy {
    void operationStrategy();
}
```

---

### 2. Concrete Strategies

These classes implement different behaviors.

* `StrategyImpl1`
* `StrategyImpl2`
* `StrategyImpl3`
* `DefaultStrategyImpl`

Each class implements the method:

```java
operationStrategy()
```

Example:

```java
public class StrategyImpl1 implements Strategy {
    @Override
    public void operationStrategy() {
        System.out.println("++++++++++ Strategy 1 ++++++++++");
    }
}
```

---

### 3. Context

The `Context` class uses a `Strategy` object to execute the selected behavior.

The strategy can be changed dynamically using:

```java
context.setStrategy(strategy);
```

---

### 4. Main Class

The `Main` class asks the user to choose a strategy from the console.

Example input:

```
Quelle stratégie?
1
```

The program dynamically loads the class:

```
StrategyImpl1
```

using Java Reflection.

---

## How It Works

1. The user selects a strategy number.
2. The program checks if the strategy already exists in the `HashMap`.
3. If not, it creates a new strategy object dynamically.
4. The strategy is passed to the `Context`.
5. The context executes the operation.

---

## Example Output

```
Quelle stratégie?
1
++++++++++ Strategy 1 ++++++++++
```

```
Quelle stratégie?
2
............ Strategy 2 ........
```

---

## Key Concepts Demonstrated

* Strategy Design Pattern
* Interfaces
* Polymorphism
* Dynamic object creation with Reflection
* HashMap caching for strategies

---

## Advantages of Strategy Pattern

* Avoids large `if/else` blocks
* Makes code easier to maintain
* Allows adding new strategies without modifying existing code
* Supports runtime behavior changes
