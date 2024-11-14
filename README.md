# Password-Generate-

import random
import string

def generate_password(length=12, use_special_chars=True, use_digits=True, use_uppercase=True, use_lowercase=True):
    # Create the pool of characters to choose from
    characters = ''
    
    if use_lowercase:
        characters += string.ascii_lowercase
    if use_uppercase:
        characters += string.ascii_uppercase
    if use_digits:
        characters += string.digits
    if use_special_chars:
        characters += string.punctuation
    
    # Ensure the pool is not empty
    if not characters:
        raise ValueError("No character types selected. At least one type must be enabled.")
    
    # Randomly select characters to create the password
    password = ''.join(random.choice(characters) for _ in range(length))
    
    return password

# Example usage
password = generate_password(length=16)
print("Generated password:", password)
