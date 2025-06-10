# password-generator-project
# Password Generator

## Overview
This project is a simple Password Generator tool written in Python. It generates strong, random passwords based on user-selected criteria, including length, uppercase letters, lowercase letters, numbers, and special characters.

## Features
- User inputs desired password length.
- Option to include/exclude uppercase letters, lowercase letters, numbers, and special characters.
- Generates a random, secure password based on selected options.

## Technologies Used
- Python 3.x
- Standard Python libraries (`random`, `string`)

## How to Use
1. Run the script.
2. Enter the desired password length.
3. Choose which character types to include.
4. Receive a randomly generated secure password.

## Sample Code Snippet
```python
import random
import string

def generate_password(length, use_upper, use_lower, use_numbers, use_special):
    characters = ''
    if use_upper:
        characters += string.ascii_uppercase
    if use_lower:
        characters += string.ascii_lowercase
    if use_numbers:
        characters += string.digits
    if use_special:
        characters += string.punctuation

    if not characters:
        raise ValueError("At least one character type must be selected")

    return ''.join(random.choice(characters) for _ in range(length))

# Example usage
print(generate_password(12, True, True, True, True))
