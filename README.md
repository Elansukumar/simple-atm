# simple-atm
import time
print("Welcome to ATM How can I help you")
acc_bal = 10000
my_pin = 2598
transaction_history = {"TXN001": {"date": "2023-07-01", "type": "debit", "amount": 150.0, "description": "Grocery shopping"},
             "TXN002": {"date": "2023-07-02", "type": "credit", "amount": 2000.0, "description": "Salary"},
             "TXN003": {"date": "2023-07-03", "type": "debit", "amount": 100.0, "description": "Electricity bill"},
             "TXN004": {"date": "2023-07-04", "type": "debit", "amount": 50.0, "description": "Internet bill"},
             "TXN005": {"date": "2023-07-05", "type": "credit", "amount": 500.0, "description": "Freelance work"}
            }
while True:
    print("Please Insert your Card")
    time.sleep(5)
    pin = int(input("Enter your pin:"))
    if pin == my_pin:
        print("1.Account balance Inquiry")
        print("2.Cash withdrawal")
        print("3.cash deposit")
        print("4.PIN Change")
        print("5.Transaction History")
        choice = int(input("Enter your choice from 1 to 5:"))
        if choice == 1:
            print("Your Account Balance is ",acc_bal)
        elif choice == 2:
            cash_wid = int(input("Enter your amount to withdraw"))
            curr_acc_bal = acc_bal - cash_wid
            print("the currenr account balance is: ",curr_acc_bal)
        elif choice == 3:
            cash_dep = int(input("Enter your amount to Deposit"))
            up_bal = cash_dep + acc_bal
            print("The Updated balance is ",up_bal)
        elif choice == 4:
            c_pin = int(input("Enter Your New PIN"))
            s_pin = int(input("Enter your confirmed PIN"))
            if c_pin == s_pin:
                print("Your PIN Has been changed")
                print(c_pin)
        elif choice == 5:
            def get_transaction_history_string(history):
                output = ""
                for txn_id, details in history.items():
                    output += f"Transaction ID: {txn_id}\n"
                    output += f"  Date: {details['date']}\n"
                    output += f"  Type: {details['type']}\n"
                    output += f"  Amount: {details['amount']}\n"
                    output += f"  Description: {details['description']}\n\n"
                return output
            transaction_history_string = get_transaction_history_string(transaction_history)
            print(transaction_history_string)
    elif pin != my_pin:
        print("you have Entered Incorrect PIN")
        break
