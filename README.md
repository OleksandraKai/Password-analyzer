def password_strength(password):
    strength = {"length": False, "uppercase": False, "lowercase": False, "numbers": False, "special": False}
    special = '!@#$%^&*()-_=+[]{}|;:,.<>?/~`'

    if len(password) >= 8:
        strength["length"] = True
    for char in password:
        if char.isupper():
            strength["uppercase"] = True
        elif char.islower():
            strength["lowercase"] = True
        elif char.isdigit():
            strength["numbers"] = True
        elif char in special:
            strength["special"] = True

    return strength

password = input("Enter a password to test: ")
print(password_strength(password))
