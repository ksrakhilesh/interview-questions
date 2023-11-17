**Optimal Bill Distribution**

You are given a list of bills paid by a group of friends. Each bill indicates the payer, the total amount, and the friends involved. 
- Design a function to verify whether the transactions effectively settle the debts and distribute expenses fairly among friends.
- Design an algorithm to fairly distribute the expenses among the friends, minimizing the total amount exchanged.

**Input:**
- A list of bills, each containing information about the payer, total amount, and friends involved.

**Output:**
- Design a function to verify whether the bills effectively settle the debts and distribute expenses fairly among friends.
- Design an algorithm to fairly distribute the expenses among the friends, minimizing the total amount exchanged.

**Example:**
```javascript
bills = [
    { payer: "A", amount: 100, friends: ["B", "C", "D"] },
    { payer: "B", amount: 50, friends: ["A", "C"] },
    { payer: "C", amount: 30, friends: ["A", "B", "D"] },
    { payer: "D", amount: 20, friends: ["A", "C"] }
]

isDebtSettled(bills)
// Output =  False

optimalDistribution(bills)
// Output = 
[
    {
        "debtor": "A",
        "creditor": "C",
        "amount": 38.333333333333336
    },
    {
        "debtor": "A",
        "creditor": "D",
        "amount": 16.666666666666664
    },
    {
        "debtor": "B",
        "creditor": "D",
        "amount": 6.666666666666664
    }
]


bills = [
    { payer: "A", amount: 100, friends: ["B", "C"] },
    { payer: "B", amount: 100, friends: ["A", "C"] },
    { payer: "C", amount: 100, friends: ["A", "B"] },
]


isDebtSettled(bills)
// Output =  True

optimalDistribution(bills)
// Output = []
```

**Constraints:**
- The number of friends in each bill is variable.
- The total amount is a positive integer.


