def check_password(password):
    # Define the criteria for a strong password
    criteria = {
        'length': 8,
        'uppercase': False,
        'lowercase': False,
        'digits': False,
        'special_chars': False
    }

    # Check the length
    if len(password) < criteria['length']:
        return False

    # Check for uppercase letters
    if not any(char.isupper() for char in password) and criteria['uppercase']:
        return False

    # Check for lowercase letters
    if not any(char.islower() for char in password) and criteria['lowercase']:
        return False

    # Check for digits
    if not any(char.isdigit() for char in password) and criteria['digits']:
        return False

    # Check for special characters
    special_chars = "!@#$%^&*()_+=-{}[]|\:;<>?,./"
    if not any(char in special_chars for char in password) and criteria['special_chars']:
        return False

    # If all criteria are met, the password is valid
    return True

# Prompt the user to enter a password
password = input("Enter a password: ")

# Check the password
if check_password(password):
    print("Valid password!")
else:
    print("Invalid password!")
