# ☕ Coffee Machine Simulator

A Python program that simulates a coffee machine using Object-Oriented Programming (OOP) principles. The program consists of different classes for modeling the coffee maker, menu items, and money handling.

## 🚀 Features

1. **CoffeeMaker Class**: Models the coffee machine that makes the coffee. Handles resources, reports, and coffee-making functionality.

2. **Menu Class**: Models the menu with different drink options. Includes a class for each menu item with specific ingredients and costs.

3. **MoneyMachine Class**: Models the money-handling functionality. Processes coins, makes payments, and keeps track of profits.

4. **Main Program (main.py)**: Integrates the classes to create an interactive coffee machine experience. Allows users to order coffee, turn off the machine, and generate reports.

## 📂 Project Structure

- **coffee_maker.py**: Models the CoffeeMaker class.
- **menu.py**: Models the Menu and MenuItem classes.
- **money_machine.py**: Models the MoneyMachine class.
- **main.py**: Main program that utilizes the classes for a complete coffee machine simulation.

## ⚙️ Usage

1. Run the `main.py` file in a console or terminal.
2. Follow the prompts to order coffee, turn off the machine, generate reports, and more.
3. Experience a virtual coffee-making adventure!

## 🌐 Example

```python
#
from menu import Menu, MenuItem
from coffee_maker import CoffeeMaker
from money_machine import MoneyMachine

money_machine = MoneyMachine()
coffee_maker = CoffeeMaker()
coffee_maker.report()
money_machine.report()
menu = Menu()
is_on = True

while is_on:
    options = menu.get_items()
    choice = input(f"What would you like? ({options}): ")
    if choice == 'off':
        is_on = False
    elif choice == 'report':
        coffee_maker.report()
        money_machine.report()
    else:
        drink = menu.find_drink(choice)
        if coffee_maker.is_resource_sufficient(drink) and money_machine.make_payment(drink.cost):
            coffee_maker.make_coffee(drink)


