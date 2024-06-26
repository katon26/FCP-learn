## Unit Testing in Java
- [Overview](#overview)
- [JUnit Framework](#junit-framework)
- [JUnit Annotations](#junit-annotations)
- [JUnit Assert Methods](#junit-assert-methods)

additional other source outside this repository:
- [JUnit Test Suite](https://www.tutorialspoint.com/junit/junit_test_framework.htm)
- [JUnit Ignore Test](https://www.tutorialspoint.com/junit/junit_ignore_test.htm)
- [JUnit Exception Test](https://www.tutorialspoint.com/junit/junit_exception_test.htm)
- [JUnit Time Test](https://www.tutorialspoint.com/junit/junit_time_test.htm)

### Overview
Unit testing is a software testing method by which individual units of source code, sets of one or more computer program modules together with associated control data, usage procedures, and operating procedures, are tested to determine whether they are fit for use.

- Unit testing : Validate individual components of the software.
- Goal : Ensure code correctness and functionality.

### JUnit Framework
- Popular unit testing framework for Java.
- Provides annotations to identify test methods such as annotations, assertions for testing expected results, test runners for running tests.
- Integrates with build tools like Maven, Gradle, etc and IDEs like Eclipse, IntelliJ IDEA, etc.

snippet code:
```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

class BankAccountTest {
    @Test
    void testDeposit() {
        BankAccount account = new BankAccount();
        account.deposit(100);
        assertEquals(100, account.getBalance());
    }

    @Test
    void testWithdraw() {
        BankAccount account = new BankAccount(500);
        account.withdraw(100);
        assertEquals(100, account.getBalance(), "The balance should be updated after withdrawal");
    }

    @Test
    void withdraw_insufficientBalance() {
        BankAccount account = new BankAccount(100);
        assertThrows(InsufficientBalanceException.class, () -> account.withdraw(200));
    }
}
```

### JUnit Annotations
JUnit provides annotations to identify test methods and lifecycle methods. Some of the commonly used annotations are:

- `@Test` : Identifies a method as a test method.
- `@Before` , `@After` : Identifies a method to run before or after each test.
- `@BeforeClass` , `@AfterClass` : Identifies a method to run before or after all tests.
- `@BeforeAll` : Identifies a method to run before all tests.
- `@BeforeEach` : Identifies a method to run before each test.
- `@AfterEach` : Identifies a method to run after each test.
- `@AfterAll` : Identifies a method to run after all tests.

code snippet:
```java
@Test
public void testDeposit() {
    BankAccount account = new BankAccount();
    account.deposit(100);
    assertEquals(100, account.getBalance());
}

@Test
public void testWithdraw() {
    BankAccount account = new BankAccount(500);
    account.withdraw(100);
    assertEquals(400, account.getBalance());
}
```

```java
@Before
public void setUp() {
    account = new BankAccount(1000);
}
```

```java
@BeforeClass
public static void setUpClass() {
    System.out.println("Before all tests. Setting up the test environment.");
}
```

### JUnit Assert Methods
JUnit provides a set of assert methods to test expected results. Some of the commonly used assert methods are:

- `AssertTrue(boolean condition)` , `AssertFalse(boolean condition)` : Tests if a condition is true or false.
- `AssertEquals(expected, actual)` , `AssertNotEquals(expected, actual)` : Tests if two values are equal or not equal.
- `AssertNull(object)` , `AssertNotNull(object)` : Tests if an object is null or not null.
- `AssertArrayEquals(expectedArray, actualArray)` : Tests if two arrays are equal.

code snippet:
```java
@Test
public void testTransfer() {
    BankAccount fromAccount = new BankAccount(1000);
    BankAccount toAccount = new BankAccount(500);
    fromAccount.transfer(toAccount, 500);
    assertEquals(500, fromAccount.getBalance());
    assertEquals(1000, toAccount.getBalance());
}

@Test
public void testAccountStatus() {
    BankAccount account = new BankAccount(0);

    assertFalse(account.isActive());
    account.deposit(100);
    assertTrue(account.isActive());
}
```
___

## Recap Module 2
- Manage Program Flows: Control structures, conditional statements, loops, branching, etc.
- Error / Exception Handling: Types of exceptions, try-catch-finally, throw, throws, etc.
- Unit Test in Java: JUnit framework, annotations, assert methods, etc.