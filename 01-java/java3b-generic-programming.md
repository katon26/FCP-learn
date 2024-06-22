## Generic Programming
- Create flexible, reusable, type-safe code
- Allows for code reusability with different data types
- Java Generics introduced in Java 5

snippet code:
```java
public class Bank<T> {
    private T account;

    public Bank(T account) {
        this.account = account;
    }

    public T getAccount() {
        return account;
    }

    public void setAccount(T account) {
        this.account = account;
    }
}
```

## Using Generic Classes
- Use angle brackets '<>' to specify the generic type
- Specify the data type when creating an object of the class
- Compile-time type checking: Generic classes offer compile-time type checking, which helps catch type-related errors early

snippet code:
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
```