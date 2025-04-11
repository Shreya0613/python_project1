import random
import string

def generate_password(length=12):
    if length < 2:
        return "Password should be at least 2 characters long."

    # Character sets (no symbols)
    letters = string.ascii_letters  # a-z, A-Z
    digits = string.digits          # 0-9

    # Ensure the password contains at least one letter and one digit
    password = [
        random.choice(letters),
        random.choice(digits)
    ]

    # Fill the rest of the password with letters and digits
    all_chars = letters + digits
    password += random.choices(all_chars, k=length - 2)

    # Shuffle for randomness
    random.shuffle(password)

    return ''.join(password)

# Example usage
length = int(input("Enter the password length: "))
print("Generated Password:", generate_password(length))
