#include <iostream>
#include <vector>
#include <string>

using namespace std;

// ================= STUDENT CLASS =================
class Student {
public:
    string indexNumber;
    string name;
    string programme;

    Student(string idx, string n, string prog) {
        indexNumber = idx;
        name = n;
        programme = prog;
    }
};

// ================= GLOBAL STORAGE =================
vector<Student> students;

// ================= FUNCTION PROTOTYPES =================
void registerStudent();
void viewStudents();
void searchStudent();
void menu();

// ================= MAIN FUNCTION =================
int main() {
    menu();
    return 0;
}

// ================= MENU =================
void menu() {
    int choice;
    do {
        cout << "\n--- DIGITAL ATTENDANCE SYSTEM ---\n";
        cout << "1. Register Student\n";
        cout << "2. View All Students\n";
        cout << "3. Search Student by Index Number\n";
        cout << "0. Exit\n";
        cout << "Enter choice: ";
        cin >> choice;

        switch (choice) {
        case 1:
            registerStudent();
            break;
        case 2:
            viewStudents();
            break;
        case 3:
            searchStudent();
            break;
        case 0:
            cout << "Exiting program...\n";
            break;
        default:
            cout << "Invalid choice!\n";
        }
    } while (choice != 0);
}

// ================= REGISTER STUDENT =================
void registerStudent() {
    string idx, name, prog;

    cout << "Enter Index Number: ";
    cin >> idx;
    cin.ignore();
    cout << "Enter Full Name: ";
    getline(cin, name);
    cout << "Enter Programme: ";
    getline(cin, prog);

    students.push_back(Student(idx, name, prog));
    cout << "Student registered successfully!\n";
}

// ================= VIEW STUDENTS =================
void viewStudents() {
    if (students.empty()) {
        cout << "No students registered yet.\n";
        return;
    }

    cout << "\nINDEX\tNAME\t\tPROGRAMME\n";
    for (const auto& s : students) {
        cout << s.indexNumber << "\t" << s.name << "\t" << s.programme << endl;
    }
}

// ================= SEARCH STUDENT =================
void searchStudent() {
    string searchIndex;
    cout << "Enter Index Number to search: ";
    cin >> searchIndex;

    for (const auto& s : students) {
        if (s.indexNumber == searchIndex) {
            cout << "Student Found:\n";
            cout << "Name: " << s.name << endl;
            cout << "Programme: " << s.programme << endl;
            return;
        }
    }
    cout << "Student not found.\n";
}
