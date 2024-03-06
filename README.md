def inputNumber(prompt):
    while True:
        try:
            magicNumber = float(input(prompt))
            return magicNumber
        except ValueError:
            print("Error! Please enter again...")

def calculate_gpa():
    product = 0
    for i in range(0,len(subjects)):
        product += grades[i]*credits[i]
    return product / (sum(credits))


subjects = ["C#", "Python"]
credits = []
grades = []

student_name = input("Enter your name: ")

for subject in subjects:
    grade = inputNumber(f"Enter your grade for {subject}: ")
    grades.append(grade)

    credit = inputNumber(f"Enter the credit hours for {subject}: ")
    credits.append(credit)

total_credits = sum(credits)
total_grades = sum(grades)

print(f"Total credits for {student_name}: {total_credits}")
print(f"Total grades for {student_name}: {total_grades}")

# Calculate GPA
gpa = calculate_gpa()
print(f"{student_name}'s GPA is: {gpa}")

# Write to file
with open('hieu.nmh', 'w') as file:
    file.write(f'{student_name}, {credits}, {grades}, {gpa}')
