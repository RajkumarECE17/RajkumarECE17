class Student:
    def __init__(self, name):
        self.name = name
        self.grades = {}

    def add_grade(self, subject, grade):
        if subject in self.grades:
            self.grades[subject].append(grade)
        else:
            self.grades[subject] = [grade]

    def get_average_grade(self):
        total_grades = sum([sum(grades) for grades in self.grades.values()])
        total_count = sum([len(grades) for grades in self.grades.values()])
        if total_count == 0:
            return 0
        return total_grades / total_count

    def get_grades(self):
        return self.grades


class GradeTracker:
    def __init__(self):
        self.students = {}

    def add_student(self, name):
        if name not in self.students:
            self.students[name] = Student(name)

    def add_grade(self, name, subject, grade):
        if name in self.students:
            self.students[name].add_grade(subject, grade)
        else:
            print(f"Student {name} not found. Please add the student first.")

    def get_student_average(self, name):
        if name in self.students:
            return self.students[name].get_average_grade()
        else:
            print(f"Student {name} not found.")
            return None

    def get_all_students(self):
        return self.students.keys()

    def get_student_grades(self, name):
        if name in self.students:
            return self.students[name].get_grades()
        else:
            print(f"Student {name} not found.")
            return None

    def get_overall_average(self):
        total_grades = 0
        total_count = 0

        for student in self.students.values():
            for grades in student.get_grades().values():
                total_grades += sum(grades)
                total_count += len(grades)

        if total_count == 0:
            return 0
        return total_grades / total_count


# Example usage
tracker = GradeTracker()

# Adding students
tracker.add_student("Alice")
tracker.add_student("Bob")

# Adding grades
tracker.add_grade("Alice", "Math", 85)
tracker.add_grade("Alice", "English", 90)
tracker.add_grade("Bob", "Math", 78)
tracker.add_grade("Bob", "Science", 88)

# Getting student average
print(f"Alice's average grade: {tracker.get_student_average('Alice')}")
print(f"Bob's average grade: {tracker.get_student_average('Bob')}")

# Getting overall average across all students and subjects
print(f"Overall average grade: {tracker.get_overall_average()}")

# Getting student grades
print(f"Alice's grades: {tracker.get_student_grades('Alice')}")
print(f"Bob's grades: {tracker.get_student_grades('Bob')}")

# List all students
print(f"All students: {list(tracker.get_all_students())}")class Student:
    def __init__(self, name):
        self.name = name
        self.grades = {}

    def add_grade(self, subject, grade):
        if subject in self.grades:
            self.grades[subject].append(grade)
        else:
            self.grades[subject] = [grade]

    def get_average_grade(self):
        total_grades = sum([sum(grades) for grades in self.grades.values()])
        total_count = sum([len(grades) for grades in self.grades.values()])
        if total_count == 0:
            return 0
        return total_grades / total_count

    def get_grades(self):
        return self.grades


class GradeTracker:
    def __init__(self):
        self.students = {}

    def add_student(self, name):
        if name not in self.students:
            self.students[name] = Student(name)

    def add_grade(self, name, subject, grade):
        if name in self.students:
            self.students[name].add_grade(subject, grade)
        else:
            print(f"Student {name} not found. Please add the student first.")

    def get_student_average(self, name):
        if name in self.students:
            return self.students[name].get_average_grade()
        else:
            print(f"Student {name} not found.")
            return None

    def get_all_students(self):
        return self.students.keys()

    def get_student_grades(self, name):
        if name in self.students:
            return self.students[name].get_grades()
        else:
            print(f"Student {name} not found.")
            return None

    def get_overall_average(self):
        total_grades = 0
        total_count = 0

        for student in self.students.values():
            for grades in student.get_grades().values():
                total_grades += sum(grades)
                total_count += len(grades)

        if total_count == 0:
            return 0
        return total_grades / total_count


# Example usage
tracker = GradeTracker()

# Adding students
tracker.add_student("Alice")
tracker.add_student("Bob")

# Adding grades
tracker.add_grade("Alice", "Math", 85)
tracker.add_grade("Alice", "English", 90)
tracker.add_grade("Bob", "Math", 78)
tracker.add_grade("Bob", "Science", 88)

# Getting student average
print(f"Alice's average grade: {tracker.get_student_average('Alice')}")
print(f"Bob's average grade: {tracker.get_student_average('Bob')}")

# Getting overall average across all students and subjects
print(f"Overall average grade: {tracker.get_overall_average()}")

# Getting student grades
print(f"Alice's grades: {tracker.get_student_grades('Alice')}")
print(f"Bob's grades: {tracker.get_student_grades('Bob')}")

# List all students
print(f"All students: {list(tracker.get_all_students())}")
