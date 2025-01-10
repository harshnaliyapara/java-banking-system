# java-banking-system
Project Description:
This Java-based banking application is a simple yet functional simulation of a basic banking system. It allows users to perform essential banking operations like checking their account balance, depositing funds, withdrawing money, and exiting the program. Built using core Java concepts, this project is ideal for beginners to learn user input handling, conditional logic, methods, and control flow.

Key Features:
Menu-Driven Interface: Users can choose from four options:
1. Check Balance: Displays the current balance.
2. Deposit: Adds funds to the account.
3. Withdraw: Deducts funds if sufficient balance is available.
4. Exit: Closes the application with a farewell message.
Static Balance Management: The balance is stored in a static variable (balance), ensuring it persists throughout the program.
User Input Handling: Uses the Scanner class to accept user input for menu options, deposit amounts, and withdrawal amounts.
Error Handling: Prevents withdrawals exceeding the available balance with an "Insufficient funds" message.
Currency Representation: Transactions are displayed in Indian Rupees (₹).

Project Code: 
import java.util.Scanner;

public class Project {
  static double balance = 0;

  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    int option = 0;
    while (option != 4) {
      System.out.println("Welcome to the Bank of Java");
      System.out.println("1. Check Balance");
      System.out.println("2. Deposit");
      System.out.println("3. Withdraw");
      System.out.println("4. Exit");
      System.out.print("Enter an option: ");
      option = scanner.nextInt();

      switch (option) {
        case 1:
          checkBalance();
          break;
        case 2:
          deposit();
          break;
        case 3:
          withdraw();
          break;
        case 4:
          exit();
          break;
        default:
          System.out.println("Invalid option. Try again.");
          break;
      }
    }
  }

  public static void checkBalance() {
    System.out.println("Your current balance is ₹" + balance);
  }

  public static void deposit() {
    Scanner scanner = new Scanner(System.in);
    System.out.print("Enter the amount to deposit: ₹");
    double amount = scanner.nextDouble();
    balance = balance + amount;
    System.out.println("₹" + amount + " has been deposited to your account.");
    checkBalance();
  }

  public static void withdraw() {
    Scanner scanner = new Scanner(System.in);
    System.out.print("Enter the amount to withdraw: ₹");
    double amount = scanner.nextDouble();
    if (amount > balance) {
      System.out.println("Insufficient funds.");
    } else {
      balance -= amount;
      System.out.println("₹" + amount + " has been withdrawn from your account.");
    }
    checkBalance();
  }

  public static void exit() {
    System.out.println("Thank you for banking with us. Have a great day!");
  }
}
