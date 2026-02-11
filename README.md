cin >> celsius;
#include <iostream>
using namespace std;

int main() 
{
    double celsius, fahrenheit;

    // 1. Ask user to input temperature in Celsius
    cout << "Enter temperature in Celsius: ";
    cin >> celsius;

    // 2. Convert to Fahrenheit
    fahrenheit = (celsius * 1.8) + 32;

    // 3. Output the result
    cout << "Temperature in Fahrenheit: " << fahrenheit << "°F" << endl;

    // 4. Bonus condition
    if (celsius < 0) 
    {
        cout << "Freezing!" << endl;
    }
    else if (celsius > 30) 
    {
        cout << "Hot!" << endl;
    }

    return 0;
}
