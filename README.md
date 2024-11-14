import random
import string

def generate_password(length=12):
    # Define the characters to choose from (letters, digits, and punctuation)
    characters = string.ascii_letters + string.digits + string.punctuation
    
    # Randomly select characters and join them to form a password
    password = ''.join(random.choice(characters) for i in range(length))
    
    return password

# Ask the user for the password length
length = int(input("Enter the password length: "))

# Generate and print the password
password = generate_password(length)
print(f"Generated password: {password}")
