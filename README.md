# Java Bank Account
Course: Problem Solving and Programming I
Assignment: Final Project
Language: Java
Author: Red Team
Date: December 17, 2025

# Project Overview

This project implements a console-based banking system using object-oriented programming principles in Java. The system allows users to create customers, open multiple types of bank accounts, perform deposits and withdrawals, apply end-of-month updates, and generate bank-wide statistics.

The application demonstrates core OOP concepts including inheritance, encapsulation, polymorphism, and method overriding, all accessed through a menu-driven interface.

# UML Diagram

<img width="916" height="654" alt="image" src="https://github.com/user-attachments/assets/f286f244-e5b0-495a-9f04-ea76913124be" />

# Design and Implementation Assumptions

Account balances and interest rates are stored as double.

Account IDs are assigned based on the size of the account list.

Data is stored in memory only (no database or file storage).

End-of-month processing is manually triggered by the user.

Customers may have multiple accounts.

Gold accounts do not charge maintenance or transaction fees.

# Objects in the System and Their Responsibilities

## Bank

Manages all accounts in the system.

Opens checking, regular, and gold accounts.

Applies monthly updates:

CheckingAccount: transaction fees

RegularAccount: maintenance fee and interest

GoldAccount: interest only

Displays bank-wide statistics.

## Account (Superclass)

Stores ID, balance, interest rate, and associated customer.

Provides deposit and withdrawal functionality.

Acts as the base class for all account types.

## CheckingAccount

Tracks monthly transaction count.

Allows two free transactions per month.

Charges $3 per transaction after the second.

Prevents withdrawals that would cause transaction fees to exceed the balance.

Resets transaction count during monthly processing.

## RegularAccount

Charges a fixed $10 monthly maintenance fee.

Does not allow overdrafts.

Displays an error message when insufficient funds exist.

Interest is applied during monthly processing.

## GoldAccount

Stores an interest rate.

Applies monthly interest.

Does not charge maintenance or transaction fees.

## Customer

Stores customer name, address, and phone number.

Acts as a data holder for account ownership.

## BankDemo

Provides a menu-driven console interface.

Handles user input and validation.

Connects user actions to bank operations.

# Design Patterns Used

Inheritance: Account subclasses extend Account.

Method Overriding: CheckingAccount and RegularAccount override withdrawal behavior.

Polymorphism: Bank processes accounts dynamically by type.

Encapsulation: Private fields accessed through public getters.

Association: Accounts maintain references to Customer objects.

# Challenges Faced During Design

Interpreting whether interest should be added or deducted from Checking and Gold accounts based on the phrasing of the requirements

Deciding how to implement the end of month function, whether it'd be best to do it in the account or bank class. 

# Known Bugs

When depositing, the banking system incorrectly adds the amount and increases the deposited amount by 10, you can reproduce this by making an account, selecting deposit, entering the id, and then an amount, then afterwards check the balance.

Random line text printed

Invalid Results
