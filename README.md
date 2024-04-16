#include <iostream>
#include <vector>
#include <iomanip>

using namespace std
class Employee {
private:
    string name;
    double hourlyRate;
    double hoursWorked;

public:
    Employee(string name, double hourlyRate) : name(name), hourlyRate(hourlyRate), hoursWorked(0) {}
    void recordHours(double hours) {
        hoursWorked += hours;
    }
    double calculatePay() const {
        return hoursWorked * hourlyRate;
    }
    void display() const {
        cout << "Name: " << name << ", Total Hours: " << hoursWorked << ", Total Pay: $" << fixed << setprecision(2) << calculatePay() << endl;
    }
};
int main() {
    vector<Employee> employees;
    employees.push_back(Employee("John", 15.50));
    employees.push_back(Employee("Alice", 18.75));
    employees.push_back(Employee("Bob", 20.00));
    employees[0].recordHours(40);
    employees[1].recordHours(30);
    employees[2].recordHours(45);
    cout << "Employee Details:" << endl;
    for (const auto& emp : employees) {
        emp.display();
    }

    return 0;
}
