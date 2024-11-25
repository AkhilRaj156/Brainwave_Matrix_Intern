# Brainwave_Matrix_Intern
# Python Program for ATM Functionality
class ATM:
    def __init__(self, balance=0):
        self.balance=balance

    def check_balance(self):
        """Check Account Balance"""
        return f"Your Account Balance is: ${self.balance}"
    
    def deposit(self, amount):
        """Deposit Money into the Account."""
        self.balance+=amount
        return f"${amount} has been Deposited into your Account. Current Balance: ${self.balance}"
    
    def withdraw(self, amount):
        """Withdraw Money from the Account"""
        if amount <=self.balance:
            self.balance -= amount
            return f"${amount} has been Withdraw from your Account. Current Balance: ${self.balance}"
        else:
            return "insufficient Funds"
        
atm= ATM()
menu="""
Welcome to American Bank ATM Machine!
1. Check Balance
2. Deposit
3. Withdraw Cash
4. Exit
"""

while True:
    print(menu)
    choice=input("Enter Your Choice(1/2/3/4):  ")

    if choice=='1':
        print(atm.check_balance())
    elif choice=='2':
        amount=float(input("Enter the Amount to Deposit: $"))
        print(atm.deposit(amount))
    elif choice=='3':
        amount=float(input("Enter the Amount to Withdraw: $"))
        print(atm.withdraw(amount))
    elif choice=='4':
        print("Thank You For Banking with us. Good Bye!")
        break
    else:
        print("Invalid Choice. Please Try Again..")

