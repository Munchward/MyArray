#include <iostream>
using namespace std;
 
void swapPlace(string myArray[], int a, int b)
{
        string temp = myArray[a];
        myArray[a] = myArray[b];
        myArray[b] = temp;
}
 
string* sortByCharacterLength(string countries[])
{
 
        string countryByCharacterLength[12];
        for (int i = 0; i < 12; i++)
        {
                countryByCharacterLength[i] = countries[i];
                cout << countryByCharacterLength[i] << endl << endl;
        }
        bool needsSorting = false;
        do {
                needsSorting = false;
 
                for (int i = 0; i < 11; i++)
                {
                        if (countryByCharacterLength[i].length()
                                        > countryByCharacterLength[i + 1].length())
                        {
                                swapPlace(countryByCharacterLength, i, i + 1);
                                needsSorting = true;
                        }
                }
 
        } while (needsSorting);
        cout << endl;
        for (int i = 0; i < 12; i++)
        {
                cout << countryByCharacterLength[i] << endl;
        }
        return countryByCharacterLength;
}
 
int main() {
        string countries[12];
        countries[0] = "January";
        countries[1] = "February";
        countries[2] = "March";
        countries[3] = "April";
        countries[4] = "May";
        countries[5] = "June";
        countries[6] = "July";
        countries[7] = "August";
        countries[8] = "September";
        countries[9] = "October";
        countries[10] = "November";
        countries[11] = "December";
 
        sortByCharacterLength(countries);
 
        return 0;
}
