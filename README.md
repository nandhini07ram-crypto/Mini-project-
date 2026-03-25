students = {}
n = int(input("Enter number of students: "))
for i in range(n):
    name = input(f"Enter name of student {i+1}: ")
    students[name] = []
days = int(input("Enter number of days: "))
for day in range(1, days + 1):
    print(f"\nDay {day} Attendance:")
    for name in students:
        status = input(f"Is {name} present? (P/A): ").upper()
        students[name].append(status)
print("\nAttendance Report:")
for name, records in students.items():
    present_days = records.count('P')
    percentage = (present_days / days) * 100
    print(f"{name}: {percentage:.2f}%")
print("\nStudents with attendance below 75%:")
for name, records in students.items():
    present_days = records.count('P')
    percentage = (present_days / days) * 100
    if percentage < 75:
        print(name)
