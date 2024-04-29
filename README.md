# Personal Finance Tracker

A Python program for tracking personal finance transactions. It allows users to add, view, update, delete transactions, add transactions in bulk from a CSV file and display a summary of all transactions. This version includes a GUI feature of my application.


## Features

- Add a new transaction
- View transactions (with a search and sort feature using a GUI)
- Add transactions in bulk from a CSV file
- Update existing transactions
- Delete a specific transaction
- Display a summary of transactions made

## Demo

https://github.com/SSSAccount/finance-tracker-gui/assets/115540526/fc744798-91bd-4d9f-aa00-3171b80253cd

## Requirements
- Python >= 3.12.1
- pip >= 24.0

## Installation

Download requirements.txt and ensure you are in the same directory as the requirements.txt file. Execute the following in the terminal.

```bash
pip install -r requirements.txt
```

Ensure you have also downloaded "gui.py", "finance_tracker.py", "helper.py", "financials.json" and create a new file called
"bulk.csv" in the same directory

## Usage/Examples

Ensure "gui.py", "finance_tracker.py", "helper.py", "financials.json" and "bulk.csv" are in the same directory and then run 
```bash
python gui.py
```

or if you want to access the GUI while using the CLI version of the application then run the following and enter option 7
```bash
python finance_tracker.py
```

in the terminal before using the following features:

1. **Adding Transactions**:
   - GUI:
      - Select the add tab from the gui application.
      - Enter the following data and select the following options presented in the tab.
      - Press the "Add Transaction" Button after entering all the necessary data.
   - CLI:
      - Choose option 1 from the main menu.
      - Follow the prompts to enter the transaction details such as category, amount, date and choice
      - Confirm the transaction to add it to the records.

2. **Viewing Transactions**:
   - GUI:
      - Select the view tab from the gui application.
      - To search type your search query inside of the search box.
      - To sort click on a column header to sort the data.
   - CLI:
      - Select option 2 from the main menu.
      - Choose a category to view transactions for that specific category.
      - To view all transactions, choose the "All" option.
      - Follow on-screen instructions to navigate through transactions.
     
4. **Adding Bulk Transactions**:
   - Make a copy of the bulk.csv to avoid any data loss as the program empties the file after adding the transactions (Optional)
   - The bulk.csv file should look something like this:
      
      (Category),(Amoount),(Date),(Choice if Category is "Other")

      Examples:
        Salary,500,2024-02-29\
        Other, 300, 2024-02-29, Income 

   - GUI:
      - Select the add tab from the gui application.
      - Press the "Add Bulk" button.
   - CLI:
      - Choose option 3 from the main menu.
      - Transactions will be added automatically from the file.

5. **Updating Transactions**:
   - GUI:
      - Select the update tab from the gui application
      - Enter the necessary data presented on the tab
      - Click on the "Update Transaction" Button
   - CLI:
      - Select option 4 from the main menu.
      - Follow the prompts to select the transaction to update which asks you for the ID of the transaction and the category of the transaction
      - Choose the aspect of the transaction to update (category, amount, date, choice).
      - Confirm the changes to update the transaction.

7. **Deleting Transactions**:
   - GUI:
      - Select the delete tab from the gui application
      - Enter the necessary data presented on the tab
      - Click on the "Delete Transaction" Button
   - CLI:
      - Choose option 5 from the main menu.
      - Follow the prompts to select the transaction to delete.
      - Confirm deletion to remove the transaction.

9. **Displaying Summary**:
   - GUI:
      - Select the summary tab from the gui application
      - A summary of all transactions will be displayed, including net profit/loss, overall financial status, and the category with the most income and expense contributions.
   - CLI:
      - Select option 6 from the main menu.
      - A summary of all transactions will be displayed, including net profit/loss, overall financial status, and the category with the most income and expense contributions.   


11. **Gui Mode** (Only available in CLI):
   - Select option 7 from the menu
   - To exit click on the "X" button in the top right corner to return to the main menu in the CLI

11. **Exit**:
   - If you are using the CLI version of the app, then enter 8 in the main menu
   - If you are using the GUI, then click on the "X" button in the top right corner 

## FAQ

#### 1. What are the supported categories?

The supported categories are:
Groceries, Salary, Utilities, Healthcare, Education and Other

The 'Other' category needs identification of whether it as an income or an expense. Any unsupported categories will be converted to the 'Other' category

#### 2. What should the schema of the bulk.csv file be?

For categories that are not "Other", each row should be:

(Category),(Amount),(Date)

Else if the category is "Other" then the row should be:

(Category),(Amount),(Date),(Choice)

#### 3. What is Choice for the "Other" category?

Choice is the type of transaction thats has been done. It can be "Income" or "Expense". Since the actual type of transaction done is unknown,
when the "Other" category is chosen, the application asks for the user to enter "Income" or "Expense" 

#### 4. Entering the category in the update tab did not make the ID menu appear

If the ID menu did not appear after selecting the category in the update tab this means that the category had no transaction made.

#### 5. There are multiple of the same ID

The ID is not unique for each category but it is unique for each transaction in each category. Therefore an ID of 1 in "Salary" is not the same
as an ID of 1 in "Groceries" but there can only be one instance of an ID of 1 in each category

## Credits

[prettytable](https://github.com/jazzband/prettytable) - For creating summary tables and viewing transactions

[PyInputPlus](https://github.com/asweigart/pyinputplus) - For creating options and getting user input easier

[questionary](https://github.com/tmbo/questionary) - For 'Press any key to continue....'

[schema](https://github.com/keleshev/schema) - For checking the schema of bulk.csv

[ttkbootstrap](https://github.com/israel-dryer/ttkbootstrap) - For creating the table of the gui and for the 'superhero theme'
