#include <iostream>
using namespace std;

int main() {
    // Step 1: Declare variables
    double celsius, fahrenheit;

    // Step 2: Ask user for input
    cout << "Enter temperature in Celsius: ";
    cin >> celsius;

    // Step 3: Convert Celsius to Fahrenheit
    fahrenheit = (celsius * 1.8) + 32;

    // Step 4: Output the result
    cout << "Temperature in Fahrenheit: " << fahrenheit << endl;

    // Step 5: Bonus condition
    if (celsius < 0) {
        cout << "Freezing!" << endl;
    }
    else if (celsius > 30) {
        cout << "Hot!" << endl;
    }

    return 0;
}
