## Functional & Modular Programming
- Programming paradigm treating computation as evaluation of mathematical functions
- Encourages immutability and statelessness
- Java 8 introduced functional programming features, e.g., lambda expressions, functional interfaces, and the Stream API
- Modular programming divides a program into separate modules, each with its own functionality
- Promotes code reusability, maintainability, and scalability
- Java 9 introduced the module system to improve code organization and security

code snippet:
```java
public class Transaction<T> {
    private T transactionDetail;

    public T getTransactionDetail() {
        return transactionDetail;
    }

    public void setTransactionDetail(T transactionDetail) {
        this.transactionDetail = transactionDetail;
    }
}

// Use Transaction class with String
Transaction<String> transaction = new Transaction<>();
stringTransaction.setTransactionDetail("Deposit $1000");
String detail = stringTransaction.getTransactionDetail();

// Use Transaction class with Integer
Transaction<Integer> intTransaction = new Transaction<>();
intTransaction.setTransactionDetail(1000);
Integer amount = intTransaction.getTransactionDetail();
```

### Lambda Expressions
- Represent instances of functional interfaces
- Provide a concise way to write anonymous functions
- Promote functional programming principles in Java
- Syntax: `(parameters) -> expression/body`
- Simplify code and improve readability
- Useful in banking for filtering, mapping, sorting, calculating, and processing data.

### Stream API
- Perform functional-style operations on collections
- Supports common operations like:  `filter()`, `map()`, `reduce()`, `collect()`, `forEach()`, etc.
- Enables parallel processing of data
- Improves code readability and maintainability
- Useful in banking or financial data for processing large datasets efficiently.

### Modular Programming
- Divide a software or program into smaller, reusable, and manageable components (modules)
- Each module has its own functionality and can be developed, tested, and maintained independently
- Promotes code maintainability, security, and performance
- Java 9 introduced the module system to improve code organization and security
- Define modules using `module-info.java` file and `module` keyword and directives like `requires`, `exports`, `opens`, etc.
- Promotes code organization, reusability, and scalability in large projects.
- JPMS (Java Platform Module System) helps in creating modular applications in Java.

### Creating a Java Module
- Declare a module with the `module` keyword
- Define module dependencies using the `requires` directive
- Define the module name and export packages using the `exports` directive
- Use `requires` to specify dependencies on other modules
- Use `exports` to make packages accessible to other modules
- Use `opens` to allow reflection on packages
- Compile modules using the `javac` command with the `--module-source-path` option
- Run modules using the `java` command with the `--module-path` option

code snippet:
```java
module com.example.banking {
    requires java.base;
    exports com.example.banking.transactions;
}
```

### Best Practices
- Use lambda expressions for simple, one-off operations
- Avoid using lambda expressions for complex logic
- Use method references for readability
- Use the Stream API for processing collections
- Organize modules based on functionality or domain
- Define clear boundaries between modules
- Limit module dependencies to reduce coupling
- Use the `exports` directive judiciously
- Follow naming conventions for modules, packages, and classes
- Write unit tests for modules to ensure correctness
- Use tools like Jigsaw to manage modules effectively
- Keep modules small, focused, and cohesive

### Example: Banking Application
- Use custom classes for modeling transactions, accounts, customers, etc.
- Use inheritance to model relationships between classes, e.g., `SavingsAccount` extends `Account`
- Use generic classes for handling different types of transactions, e.g., `Transaction<T>`
- Use lambda expressions for processing transactions, e.g., filtering transactions by amount
- Use the Stream API for processing large datasets, e.g., calculating total deposits
- Use modular programming to organize code into separate modules, e.g., `com.example.banking.transactions`

---
### Key Takeaways
- Custom Classes and Inheritance: improve code organization and reusability
- Generic Programming: handle different types of data in a type-safe manner
- Functional Programming: use lambda expressions and the Stream API for processing data, encourages immutability and statelessness, functional-style operations on collections
Modular Programming: enhance code maintainability, security, and performance, divide a program into separate modules, each with its own functionality