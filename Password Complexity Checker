import re

def check_password_strength(password):
    # Initialize strength metrics
    strength_criteria = {
        'length': len(password) >= 8,
        'uppercase': re.search(r'[A-Z]', password) is not None,
        'lowercase': re.search(r'[a-z]', password) is not None,
        'digit': re.search(r'\d', password) is not None,
        'special_char': re.search(r'[!@#$%^&*(),.?":{}|<>]', password) is not None
    }

    # Determine password strength
    strength_score = sum(strength_criteria.values())
    strength_feedback = []

    if not strength_criteria['length']:
        strength_feedback.append("Password should be at least 8 characters long.")
    if not strength_criteria['uppercase']:
        strength_feedback.append("Password should contain at least one uppercase letter.")
    if not strength_criteria['lowercase']:
        strength_feedback.append("Password should contain at least one lowercase letter.")
    if not strength_criteria['digit']:
        strength_feedback.append("Password should contain at least one digit.")
    if not strength_criteria['special_char']:
        strength_feedback.append("Password should contain at least one special character.")

    # Assess overall strength
    if strength_score == 5:
        overall_strength = "Strong"
    elif strength_score == 4:
        overall_strength = "Good"
    elif strength_score == 3:
        overall_strength = "Fair"
    else:
        overall_strength = "Weak"

    return overall_strength, strength_feedback

def main():
    password = input("Enter a password to assess its strength: ")
    strength, feedback = check_password_strength(password)
    
    print(f"\nPassword Strength: {strength}")
    if feedback:
        print("Feedback:")
        for comment in feedback:
            print(f"- {comment}")

if __name__ == '__main__':
    main()
