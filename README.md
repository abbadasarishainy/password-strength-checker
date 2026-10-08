# password-strength-checker
password strength checker 
def check_password(password):
    has_digit = False
    has_upper = False
    has_lower = False
    has_special = False

    for ch in password:
        if ch.isdigit():
            has_digit = True
        elif ch.isupper():
            has_upper = True
        elif ch.islower():
            has_lower = True
        else:
            has_special = True

    score = sum([has_digit, has_upper, has_lower, has_special])

    if len(password) < 6:
        return "Weak Password"
    elif score >= 3 and len(password) >= 8:
        return "Strong Password"
    else:
        return "Medium Password"


password = input("Enter your password: ")

result = check_password(password)

print("Password Strength:", result)