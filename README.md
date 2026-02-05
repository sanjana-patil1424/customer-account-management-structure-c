# customer-account-management-structure-c


## Description
This project implements a structure-based program in C language to manage customer account information. The program stores customer details such as name, account number, and balance for three customers and performs balance-related operations using functions and conditional logic.

## Features
- Create structure to store customer details
- Store data for multiple customers
- Display customers having balance less than minimum amount
- Add bonus amount to eligible customers
- Display updated balances

##  Concepts Used
- Structures in C
- Arrays of structures
- Functions
- Conditional Statements
- Loops

## conditions for example

- Store customer details (name, account number, balance)
- Identify customers with low balance (< $500)
- Award bonus to high-balance customers (> $1000)

## Code

```c
#include <stdio.h>

#define MINIMUM_AMOUNT 500
#define BONUS_AMOUNT 100

struct customer
{
    char name[50];
    int accno;
    float balance;
};

int main()
{
    struct customer c[3];
    int i;

    // Input customer details
    for(i = 0; i < 3; i++)
    {
        printf("\nEnter name, account number and balance:\n");
        scanf("%s %d %f", c[i].name, &c[i].accno, &c[i].balance);
    }

    // Customers with low balance
    printf("\nCustomers having balance less than minimum amount:\n");
    for(i = 0; i < 3; i++)
    {
        if(c[i].balance < MINIMUM_AMOUNT)
        {
            printf("%s\n", c[i].name);
        }
    }

    // Add bonus
    printf("\nBalances after adding bonus:\n");
    for(i = 0; i < 3; i++)
    {
        if(c[i].balance > 1000)
        {
            c[i].balance += BONUS_AMOUNT;
        }
        printf("%s - %.2f\n", c[i].name, c[i].balance);
    }

    return 0;
}
```

## How to Compile and Run

### Compile
```bash
gcc customer.c -o customer_prog
```

### Run
```bash
./customer_prog
```

## Sample Input & Output

**Input:**
```
John 1001 600
Alice 1002 1200
Bob 1003 400
```

**Output:**
```
Enter name, account number and balance:

Enter name, account number and balance:

Enter name, account number and balance:

Customers having balance less than minimum amount:
Bob

Balances after adding bonus:
John - 600.00
Alice - 1300.00
Bob - 400.00
```

## Explanation

- **Bob** is listed because his balance ($400) is below the minimum amount ($500)
- **Alice** received a $100 bonus because her balance ($1200) exceeds $1000, bringing it to $1300
- **John**'s balance ($600) doesn't qualify for the bonus, so it remains $600
EOF

## 👩‍💻 Author
Sanjana Patil

