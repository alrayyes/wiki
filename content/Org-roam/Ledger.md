---
publish: true
title: Ledger
created: 2020-07-04T15:19:50
---

## Common [Ledger](https://www.ledger-cli.org/) CLI Commands ([Source](https://gist.githubusercontent.com/agarrharr/03450c1be7f6b3d2b883c6b5e317d2aa/raw/4c5bfa57be1cd98a232e3f4bda0fcc2a51ba0862/index.md))

### Income vs expenses this month?

```sh
ledger balance income expenses --period "this month"
```

### What did my budget look like at a certain date?

```sh
ledger balance budget --end 2018-01-02
```

This is how it looked at the end of the day on Jan 1, 2018.

### How much is in the checking account right now?

```sh
ledger balance checking
```

### What is our net worth?

```sh
ledger balance ^assets ^liabilities --real
```

### How much money have we made?

```sh
ledger balance income
```

### How much money have we made from our salaries?

```sh
ledger balance income:salary
```

### How much do we spend each month on x?

```sh
ledger register -M expenses:groceries:food
```

### Group transactions by payee

```sh
ledger register --by-payee
```

### Only show uncleared transactions

```sh
ledger register --uncleared
```

### Do I have enough budgeted to pay off my credit cards?

```sh
ledger balance creditcard
```

It should be $0.00. If it's not $0.00, run this with different dates to find the problem:

```sh
ledger balance creditcard --end 2018-02-01
```

### Import

Change Chase checking from:

```
Details,Posting Date,Description,Amount,Type,Balance,Check or Slip #
```

to:

```
,Date,Payee,Amount,,,Code
```

Change Chase Credit Card from:

```
Type,Trans Date,Post Date,Description,Amount
```

to:

```
,Date,Posted,Payee,Amount
```

```sh
ledger convert ~/Downloads/checking.CSV --input-date-format "%m/%d/%Y" --invert --account Assets:Checking --rich-data -f budget.ledger --auto-match --pager less
```

### Expenses each month (sorted)

```sh
ledger -M --period-sort "(amount)" reg ^expenses
```

This will show all expenses, grouped by month and sorted by the amount.

### How much do we spend on credit cards each month?

```sh
ledger -M -r --display 'account=~/creditcard/' reg ^expenses
```
