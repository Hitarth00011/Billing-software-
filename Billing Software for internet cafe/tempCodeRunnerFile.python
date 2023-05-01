import datetime

# define hourly rate per PC
hourly_rate = 5

# define a dictionary to hold customer information
customers = {}

# define a dictionary to hold PC status
pc_status = {f'PC{pc_num}': 'available' for pc_num in range(1, 31)}

# function to add a new customer
def add_customer(name, pc_num, login_time):
    customers[name] = {
        'pc_num': pc_num,
        'login_time': login_time,
        'total_time': datetime.timedelta(0),
        'total_bill': 0
    }
    pc_status[f'PC{pc_num}'] = 'occupied'

# function to update customer details when they log out
def update_customer(name, logout_time):
    pc_num = customers[name]['pc_num']
    login_time = customers[name]['login_time']
    total_time = logout_time - login_time
    total_bill = hourly_rate * total_time.seconds / 3600
    customers[name]['total_time'] = total_time
    customers[name]['total_bill'] = total_bill
    pc_status[f'PC{pc_num}'] = 'available'

# function to display the customer details
def display_customer_details():
    for name, details in customers.items():
        print(f"Name: {name}")
        print(f"PC Number: {details['pc_num']}")
        print(f"Login Time: {details['login_time']}")
        print(f"Total Time: {details['total_time']}")
        print(f"Total Bill: {details['total_bill']}")
        print()

# function to display PC status
def display_pc_status():
    for pc, status in pc_status.items():
        print(f"{pc}: {status}")

# main program
if __name__ == '__main__':
    while True:
        # display menu
        print("Menu:")
        print("1. Add customer")
        print("2. Update customer details")
        print("3. Display customer details")
        print("4. Display PC status")
        print("5. Exit")

        # get user choice
        choice = input("Enter choice (1-5): ")

        if choice == '1':
            # add a new customer
            name = input("Enter customer name: ")
            pc_num = int(input("Enter PC number: "))
            login_time = datetime.datetime.now()
            add_customer(name, pc_num, login_time)
            print(f"{name} has logged in to PC{pc_num} at {login_time}")

        elif choice == '2':
            # update customer details
            name = input("Enter customer name: ")
            logout_time = datetime.datetime.now()
            update_customer(name, logout_time)
            print(f"{name} has logged out at {logout_time}")

        elif choice == '3':
            # display customer details
            display_customer_details()

        elif choice == '4':
            # display PC status
            display_pc_status()

        elif choice == '5':
            # exit the program
            print("Exiting program...")
            break

        else:
            print("Invalid choice. Please try again.")
