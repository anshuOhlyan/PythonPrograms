# PythonPrograms
This repository contains python assignments given in a college/university.

1. Write a program that will calculate the cost of purchasing a meal.  This program will include decisions and loops.(YUM YUM BURGER JOINT)
    
def getBurger():
    burgerCount = int(input("Enter the number of burgers you want "))
    totalBurger = burgerCount * 0.99
    return totalBurger

def getFries():
    fryCount = int(input("Enter the number of fries you want "))
    totalFry = fryCount * 0.79
    return totalFry

def getSoda():
    sodaCount = int(input("Enter the number of burgers you want "))
    totalSoda =  sodaCount * 1.09
    return totalSoda

def calc(totalBurger, totalFry, totalSoda, total):
    subtotal = totalBurger + totalFry + totalSoda
    tax = subtotal * 0.06
    total = subtotal + tax

    return total

def printReceipt(total):
     print("The total price is $",total)
     return total

def menu():
    totalBurger = 0
    totalFry = 0
    totalSoda = 0
    total = 0

    print("Enter 1 for Yum Yum Burger")
    print("Enter 2 for Grease Yum Fries")
    print("Enter 3 for Soda Yum")

    user = int(input("Enter now ->"))

    if user == 1:
         totalBurger = getBurger()
    elif user == 2:
         totalFry = getFries()
    elif user == 3:
         totalSoda = getSoda()
    else:
        print("Please enter the valid number")
        exit()

    final_amount = calc(totalBurger, totalFry, totalSoda, total)

    return final_amount


def order():
    amount = menu()
    endOrder = input("Do you want to end your order? (Please enter yes or no): ")

    while(endOrder == "no"):
        amount = amount + menu()
        endOrder = input("Do you want to end your order? (Please enter yes or no): ")

    printReceipt(amount)


def main():
    order()

    endProgram = input("Do you want to end program? (Enter no to process a new order) : ")

    while(endProgram == "no"):
        order()
        endProgram = input("Do you want to end program? (Enter no to process a new order) : ")

    exit()


main()
