# -Mini-ATM-by-Python.
<br>
# Modify your ATM from Day 4:
<br>
# Ask the user for a PIN (e.g., 1234)
<br>
# Allow 3 tries only
<br>
# If correct, allow withdrawal like before
<br>
# Else, block access

class ATM:
    def __init__(self,balance,pin):
        self.balance = balance
        self.pin = pin 
        self.amount = 0

    def verify_pin(self):
        tries = 3
        while tries > 0:
            user_pin = int(input("Enter the 4 digit pin :"))
            if user_pin == self.pin :
                print("pin access")
                return True
            else:
                tries -= 1
                print(f"tries left {tries}")
        print(f"access blocked . The pin is incorrect {user_pin}")
        return False

    def withdrawal(self , amount):
        if self.balance >= amount :
           self.balance -= amount
           self.amount = amount
           print(f"withdrawal {self.amount} successful ")
        else:
            print("Insufficient balance ")
            
    def show(self):
        print(f"The Total balance is {self.balance}")
        print(f"The withdrawal amount is {self.amount} ")


atm = ATM(balance=5000,pin=2525)                

if atm.verify_pin ():
<br>
    amount = int(input("Enter the amount :"))
<br>   
    atm.withdrawal(amount)    
<br>   
    atm.show()

