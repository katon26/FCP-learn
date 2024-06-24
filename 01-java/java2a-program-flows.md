## Manage Program Flows
Program flow in Java is managed by control structures. Control structures are used to control the flow of execution in a program. They are used to define the order in which the statements are executed in a program. Control structures are used to make decisions, loop over statements, and branch to different parts of the program.
- [Control Structures](#control-structures)
- [Conditional Statements](#conditional-statements)
- [Looping Statements](#loops)
- [Branching Statements](#branching)

### Control Structures
Control structures are used to control the flow of execution in a program. They are used to define the order in which the statements are executed in a program. Control structures are used to make decisions, loop over statements, and branch to different parts of the program.

- If - else : Make decisions based on conditions, executing specific code blocks when conditions are met
- Switch : Selects one of many code blocks to be executed. Handle multiple possible cases for single variable, Improving code readability

code example:
```java
String accountType;

if (balance >= 100000) {
    accountType = "Platinum";
} else if (balance >= 50000) {
    accountType = "Gold";
} else if (balance >= 10000) {
    accountType = "Silver";
} else {
    accountType = "Bronze";
}

switch (accountType) {
    case "Platinum":
        // Perform platinum account operations
        System.out.println("Platinum account");
        break;
    case "Gold":
        // Perform gold account operations
        System.out.println("Gold account");
        break;
    case "Silver":
        // Perform silver account operations
        System.out.println("Silver account");
        break;
    case "Bronze":
        // Perform bronze account operations
        System.out.println("Bronze account");
        break;
    default:
        // Perform default operations
        System.out.println("Invalid account type");
}
```

### Conditional Statements
Conditional statements are used to make decisions based on conditions. They are used to execute specific code blocks when conditions are met.

- Comparison Operators : Compare values to determine the truthfulness of conditions (e.g., ==, !=, >, <, >=, <=)
- Logical Operators : Combine multiple conditions to determine the truthfulness of complex conditions using `AND (&&)`, `OR (||)`, and `NOT (!)` operators

code example:
```java
int creditScore = 750;
double annualIncome = 100000;

if (creditScore >= 700 && annualIncome >= 80000) {
    System.out.println("Loan approved. Eligible");
} else if (creditScore >= 600 || annualIncome >= 110000) {
    System.out.println("Loan approved. Eligible for a smaller loan");
} else {
    System.out.println("Loan denied. Not eligible");
}
```

### Loops
Loops are used to execute a block of code repeatedly. They are used to iterate over a collection of items, perform a specific task a fixed number of times, or execute code as long as a specified condition is true.

- For : iterate a fixed numberof times,. with a known iteration
- While : Execute code repeatedly as long as a specified condition is true, with an unknown iteration count
- Do-While : Execute code repeatedly at least once, then continue to execute code as long as a specified condition is true

code example:
```java
// Using a for loop to process transactions
for (int i = 0; i < transactions.size(); i++) {
    Transaction transaction = transactions.get(i);
    processTransaction(transaction);
}

// Using a while loop to find first account with a negative balance
int i = 0;
while (i < account.size() && account.get(i).getBalance() >= 0) {
    i++;
}

// Using a do-while loop to prompt the user for a valid account number
int accountNumber;
do {
    System.out.println("Enter account number: ");
    accountNumber = scanner.nextInt();
} while (!isValidAccountNumber(accountNumber));

// Using aa for-each loop to calculate interest for multiple accounts
for (Account account : accounts) {
    double interest = calculateInterest(account.getBalance());
    account.addInterest(interest);
}
```

### Branching
Branching statements are used to control the flow of execution in a program by changing the order in which statements are executed.

- Break : Exit a loop prematurely, stopping further iterations
- Continue : Skip the current iteration of a loop, and proceed to the next iteration

code example:
```java
for (Account account : accounts) {
    if (account.isCLosed()) {
        System.out.println("Account is closed. Skipping closed account: " + account.getAccountNumber());
        continue;
    }

    if (!hasSufficientFunds(account, transactionAmount)) {
        System.out.println("Account " + account.getAccountNumber() + " has sufficient funds. Going to next account");
        // perform break operation
        break;
    }

    processTransaction(account, transactionAmount);
}
```