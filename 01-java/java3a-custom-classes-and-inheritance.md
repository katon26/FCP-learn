## Custom Classes & Inheritance
Custom classes and inheritance are fundamental concepts in object-oriented programming like Java. Custom classes allow you to define your own data types, while inheritance enables code reuse across multiple classes. This module covers the basics of creating custom classes, constructors, inheritance, and overriding methods in Java.

- Custom Classes : User-defined data types in Java
- Inheritance : Mechanism for reusing code across multiple classes
- Allows for better organization, modularity, and maintainability


[Creating Custom Classes](#Creating-Custom-Classes)
| [Constructors](#constructors)
| [Inheritance](#inheritance)
| [Overriding Methods](#overriding-methods)

code snippet:
```java
// Custom class
class BankAccount {
    String accountNumber;
    double balance;
    // Other properties and methods...
}

// Inheritance
class SavingsAccount extends BankAccount {
    double interestRate;
    // Other properties and methods...
}
```

### Creating Custom Classes

- Define classes with `class` keyword, class name, and curly braces
- Member variables hold properties; methods define actions
- Contructors initialize member variables when creating objects
- Use access modifiers (`public`, `private`, `protected`) for member visibility
- Encapsulation enforced by getter and setter methods

code snippet:
```java
class BankAccount {
    private String accountNumber; // Member variable
    private double balance; // Member variable

    // Constructor
    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }

    // Getter method
    public String getAccountNumber() {
        return accountNumber;
    }
    
    public double getBalance() {
        return balance;
    }

    // Setter method
    public void deposit(double amount) {
        balance += amount;
    }


    public void withdraw(double amount) {
        balance -= amount;
    }

    // or use this Setter method

    public void setBalance(double balance) {
        this.balance = balance;
    }
}
```

### Constructors
- Special methods called when creating an object of a class
- Constructore ensure that objects are created with the proper state, reducing the risk of errors and improving application stability
- Allows for object initialization and setting default values

code snippet:
```java
class BankAccount {
    private String accountNumber;
    private double balance;

    // Default constructor
    public BankAccount() {
        accountNumber = "000000";
        balance = 0.0;
    }

    // Parameterized constructor
    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }
}
```

### Inheritance
- Inheritance is a fundamental concept in object-oriented programming that allow a new class to inherit properties and methods from an existing class.
- Use the `extends` keyword to inherit from a superclass
- Subclass inherits members and methods of the superclass

code snippet:
```java
class SavingsAccount extends BankAccount {
    private double interestRate;

    // Constructor
    public SavingsAccount(String accountNumber, double initialBalance, double interestRate) {
        super(accountNumber, initialBalance);
        this.interestRate = interestRate;
    }
}
```

### Overriding Methods
- Modify or extend behavior of inherited methods
- Offers flexibility to adapt or enhance inherited functionality
- Method signature must match the superclass method
- Use `@Override` annotation and same method signature to override a method

code snippet:
```java
class SavingsAccount extends BankAccount {
    // Other properties and methods...

    // Override method
    @Override
    public void withdraw(double amount) {
        // Implementation for withdrawal in SavingsAccount
        if (amount > balance) {
            System.out.println("Insufficient funds");
        } else {
            balance -= amount;
        }     
    }
}