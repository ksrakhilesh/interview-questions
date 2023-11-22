## Expense Sharing System

You are tasked with designing an expense sharing system that allows users to track shared expenses among a group of people. The system should support the following functionalities:

#### (Q1) Add Expense

Implement a function that allows a user to add an expense. The function should take the following parameters:

- Main user (the one who paid)
- Amount of the expense
- List of users included in the payment
- Shares of each user (which can be equal, exact amounts, or percentages)
- Metadata about the expense


#### (Q2) Generate Individual Summary

Implement a function that generates a summary for each individual user. This summary should show all the expenses they are involved in and whether they owe money or are owed money.

Example 1: 
```python
expense_system.add_expense("A", 1000, ["B", "C", "D"], "equal")
```
Expected User A Summary:
```
B owes A 250
C owes A 250
D owes A 250
```

Example 2:
```python
expense_system.add_expense("B", 1000, ["A", "C"], "exact", {"A": 300, "C": 500})
```
Expected User B Summary:

```python
user_a_summary = expense_system.generate_individual_summary("B")
A owes B 50 (300 - 250)
C owes B 500
```

Example 3:
```python
expense_system.add_expense("C", 1000, ["A", "B", "D"], "percentage", {"A": 25, "B": 30, "D": 10})
```
Expected User A Summary:
```python
user_a_summary = expense_system.generate_individual_summary("A")
A owes B 50 (300 - 250)
D owes A 250
```

#### (Q3) List User's Expenses

Create a function that lists all the expenses a given user is involved in. This should include details of the expenses, such as the amount, shares, and the other participants.

Example:
```python
user_a_expenses = expense_system.list_user_expenses("A")
```
Expected User A's Expenses List:
1. A Pays 1000 with B, C, and D (EQUAL)
2. B Pays 1000 with A and C (EXACT => A = 300 C = 500)
3. C Pays 1000 with A, B, and D (PERCENTAGE => A = 25 B = 30 D = 10)


#### (Q4) Settle Funds

Develop a function that calculates and performs fund settlements between two users. Given two users, find the simplest way to settle the debts, if any exist.

Expected User A and B Settle Funds:
```python
user_a_summary = expense_system.settle_funds("A", "B")
>>> A has to Pay B 50
```


### `Note:`
> 1. We are trying to solve the above problem in a DS Algo (runtime) style and not building or solving it as an application
> 2. You can have any amount of space complexity.
> 3. add_expense can have any amount of time and space complexity.
> 4. generate_individual_summary, settle_funds and list_user_expenses should have least time complexity
