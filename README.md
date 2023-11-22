## Expense Sharing System

You are tasked with designing an expense sharing system that allows users to track shared expenses among a group of people. The system should support the following functionalities:

#### Add Expense

Implement a function that allows a user to add an expense. The function should take the following parameters:

- Main user (the one who paid)
- Amount of the expense
- List of users included in the payment
- Shares of each user (which can be equal, exact amounts, or percentages)
- Metadata about the expense

Example 1: 
```python
expense_system.add_expense("A", 1000, ["B", "C", "D"], "equal")
```
Expected Summary:
```
B owes A 250
C owes A 250
D owes A 250
```

Example 2:
```python
expense_system.add_expense("B", 1000, ["A", "C"], "exact", {"A": 300, "C": 500})
```
Expected Summary:
```
A owes B 50 (300 - 250)
C owes A 250
C owes B 500
D owes A 250
```

Example 3:
```python
expense_system.add_expense("C", 1000, ["A", "B", "D"], "percentage", {"A": 25, "B": 30, "D": 10})
```
Expected Summary:
```
A owes B 50 (300 - 250)
C owes B 200
D owes A 250
D owes C 100
```

#### List User's Expenses

Create a function that lists all the expenses a given user is involved in. This should include details of the expenses, such as the amount, shares, and the other participants.

Example:
```python
user_a_expenses = expense_system.list_user_expenses("A")
```
Expected User A's Expenses:
1. A Pays 1000 with B, C, and D (EQUAL)
2. B Pays 1000 with A and C (EXACT => A = 300 C = 500)
3. C Pays 1000 with A, B, and D (PERCENTAGE => A = 25 B = 30 D = 10)

#### Generate Individual Summary

Implement a function that generates a summary for each individual user. This summary should show all the expenses they are involved in and whether they owe money or are owed money.

Example:
```python
user_a_summary = expense_system.generate_individual_summary("A")
```
Expected User A's Summary:
```
A owes B 50
C owes A 250
D owes A 250
```

#### Settle Funds

Develop a function that calculates and performs fund settlements between two users. Given two users, find the simplest way to settle the debts, if any exist.

#### Generate Overall Summary

Create a function that generates an overall summary of the expenses. The summary should include details of who owes whom and how much.
