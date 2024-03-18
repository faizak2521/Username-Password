```

# Username-Password
Safe Password and Username Creator 
# Project: Username and Password Generator and Validator
# Author: Faiza Khan

# Importing necessary modules
import re

# Displaying Welcome Message and Instructions
print("\033[4mHello and Welcome!\033[0m")
print("Use this app to set up strong combinations of usernames/passwords.")
print("\nRules For Your User/Passwords:")
print("\tMust be a minimum of 5 and maximum of 10 characters.")
print("\tCannot start your username with a number or blank space.")
print("\tPassword must be different from the username (cannot match).")
print("\nNow You May Create:")

# Function to validate username and password inputs
def validate_input(user_data):
    """Validates user input against defined rules."""
    if len(user_data) < 5 or len(user_data) > 10:
        return False
    if user_data[0].isdigit() or ' ' in user_data:
        return False
    return True

# Function to check if username and password are unique
def compare_inputs(my_username, my_password):
    """Checks if username and password are unique."""
    if my_username == my_password:
        return False
    return True

# Prompting for Username and Validating
username = input("\tEnter a Valid Username: ")
while not validate_input(username):
    print("\n\033[31mInvalid Username. Please follow the rules.\033[0m")
    username = input("\n\tPlease Enter a Valid Username: ")

# Prompting for Password and Validating
password = input("\tEnter a Valid Password: ")
while not validate_input(password) or not compare_inputs(username, password):
    if not validate_input(password):
        print("\n\033[31mInvalid Password. Please follow the rules.\033[0m")
    else:
        print("\n\033[31mInvalid Password.\033[0m")
        print("\033[31mPassword must be different from the username.\033[0m")
    password = input("\n\tEnter a Valid Password: ")

# Displaying Final Entries
print("\nFinal Entries:")
print(f"\tUsername: {username} "
      f"\n\tPassword: {password} "
      f"\n\033[32mValidated\033[0m")
print("\nThank you for using this app!")

```
