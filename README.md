# FitTrack_BMI_Health_Tracker
"""
FitTrack – Smart BMI & Health Tracker
Run: python 02_FitTrack_BMI_Health_Tracker.py
"""


def calculate_bmi(weight_kg, height_m):
    if weight_kg <= 0 or height_m <= 0:
        raise ValueError("Weight and height must be greater than zero.")
    return weight_kg / (height_m ** 2)


def bmi_category(bmi):
    if bmi < 18.5:
        return "Underweight"
    if bmi < 25:
        return "Normal weight"
    if bmi < 30:
        return "Overweight"
    return "Obesity"


def main():
    print("=" * 48)
    print("       FitTrack – Smart BMI & Health Tracker")
    print("=" * 48)

    name = input("Enter your name: ").strip() or "User"
    try:
        weight = float(input("Enter your weight in kilograms (kg): "))
        height_cm = float(input("Enter your height in centimeters (cm): "))
        height_m = height_cm / 100
        bmi = calculate_bmi(weight, height_m)
    except ValueError as error:
        print("Invalid input:", error)
        return

    print("\n----- Your BMI Report -----")
    print("Name:", name)
    print(f"Weight: {weight:.1f} kg")
    print(f"Height: {height_cm:.1f} cm")
    print(f"BMI: {bmi:.2f}")
    print("Category:", bmi_category(bmi))
    print("\nBMI is a general screening measure, not a medical diagnosis.")
    print("For personal health advice, consult a qualified healthcare professional.")


if __name__ == "__main__":
    main()
