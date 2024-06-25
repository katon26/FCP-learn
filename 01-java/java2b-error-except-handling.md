## Error / Exception Handling
Error handling is a mechanism to handle runtime errors so that normal flow of the application can be maintained. In Java, an exception is an event that disrupts the normal flow of the program. It is an object that wraps an error event that occurred within a method and contains information about the error, including its type and the state of the program when the error occurred. When an error occurs within a method, the method creates an object and hands it off to the runtime system. The object, called an exception object, contains information about the error, including its type and the state of the program when the error occurred. Creating an exception object and handing it to the runtime system is called throwing an exception.

- [Overview](#overview)
- [Types of Exceptions](#types-of-exceptions)
- [Try-Catch-Finally](#try-catch-finally)
- [Throwing Exceptions (throw, throws)](#throwing-exceptions)

### Overview
- Error handling is a mechanism to handle runtime errors so that normal flow of the application can be maintained.
- Error handling : anticipate and address issues during runtime.
- Exception is an event or unusual conditions that disrupts the normal flow of the program.
- Exception handling is a mechanism to handle runtime errors so that normal flow of the application can be maintained.
- In Java, an exception is an object that wraps an error event that occurred within a method and contains information about the error, including its type and the state of the program when the error occurred.

### Types of Exceptions
- Checked Exception
  - Checked exceptions are checked at compile-time.
  - If some code within a method throws a checked exception, then the method must either handle the exception or it must specify the exception using throws keyword.
  - Example: IOException, SQLException, etc.
- Unchecked Exception
    - Unchecked exceptions are not checked at compile-time.
    - It is up to the programmer to write the code to handle such exceptions.
    - Example: ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException, etc.
- Error
    - Error is irrecoverable.
    - Example: OutOfMemoryError, VirtualMachineError, AssertionError etc.

example code checked exception:
FileNotFoundException
```java
try {
    // code that may throw exception
    FileReader file = new FileReader("C:\\test\\a.txt");
} catch (FileNotFoundException e) {
    // code to handle exception
    System.out.println("File not found");
}
```

```java
try {
    FileInputStream file = new FileInputStream("accounts.txt");
} catch (FileNotFoundException e) {
    System.out.println("File not found " + e.getMessage());
}
```

another example code checked exception:
IOException
```java
try {
    // code that may throw exception
    FileReader file = new FileReader("C:\\test\\a.txt");
    BufferedReader fileInput = new BufferedReader(file);
    
    // Print first 3 lines of file "C:\test\a.txt"
    for (int counter = 0; counter < 3; counter++) 
        System.out.println(fileInput.readLine());
    
    fileInput.close();
} catch (IOException e) {
    // code to handle exception
    System.out.println("IOException occurred");
}
```

example code unchecked exception:
NullPointerException
```java
Account account = null;

try {
    account.deposit(500);
} catch (NullPointerException e) {
    System.out.println("Account object is null: " + e.getMessage());
}

// getMessages() is a method of the Throwable class that returns the error message.
```

example code error:
```java
try {
    ArrayList<Account> accounts = loadAllAccounts();
} catch (OutOfMemoryError e) {
    System.out.println("Out of memory error occurred to load all accounts: " + e.getMessage());
}
```

### Try-Catch-Finally
Try-Catch-Finally block is used to handle exceptions in Java. It is used to maintain the normal flow of the program even if an exception occurs. It must be followed by either catch or finally or both.

- Try : Enclose code that might throw an exception. It must be followed by either catch or finally or both.
- Catch : Code to handle the specific exception. It must be preceded by try block.
- Finally : Execute code regardless of exception occurence. It must be preceded by try block.

```java
try {
    account.withdraw(amount);
} catch (InsufficientBalanceException e) {
    System.out.println("Insufficient balance. Please try again with a lesser amount.");
} finally {
    System.out.println("Transaction completed. Thank you for banking with us.");
}
```

### Throwing Exceptions
Throwing exceptions is a way to create and throw custom exceptions. It is used to throw an exception explicitly. The throw keyword is used to throw an exception. The throws keyword is used to declare exceptions. It specifies the exceptions that a method can throw.

- Throw: Create and throw custom exceptions. It is used to throw an exception explicitly.
- Throws: Declare exceptions. It specifies the exceptions that a method can throw.

```java
class BankAccount {
    // ...

    public void withdraw(double amount) throws InsufficientBalanceException {
        if (balance < amount) {
            throw new InsufficientBalanceException("Insufficient balance");
        }
        balance -= amount;
    }
}

// -= is a shorthand operator that subtracts the right operand from the left operand and assigns the result to the left operand.
```