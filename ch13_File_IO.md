# 檔案的輸入與輸出

lab1:寫入資料於檔案
TextFileOutput.cpp
```
建立一 ofstream 的物件，並且寫入二行資料於 scores.txt 檔案。每一行資料包含名(字串)、中間名(字元)、姓(字串)以及分數(整數)。
```
```
#include <iostream>
#include <fstream>
using namespace std;

int main()
{
  ofstream output;

  // Create a file
  output.open("scores.txt");

  // Write two lines
  output << "John" << " " << "T" << " " << "Smith" 
    << " " << 90 << endl;
  output << "Eric" << " " << "K" << " " << "Jones" 
    << " " << 85 << endl;

  output.close();

  cout << "Done" << endl;

  return 0;
}
```
lab2:從檔案讀出資料

檔案===>scores2.txt
```
John T Smith 70
Eric K Jones 95
```
程式===>TextFileIput.cpp
```
#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main()
{
  ifstream input("scores2.txt");

  // Read data
  string firstName;
  char mi;
  string lastName;
  int score;
  input >> firstName >> mi >> lastName >> score;
  cout << firstName << " " << mi << " " << lastName << " "
    << score << endl;

  input >> firstName >> mi >> lastName >> score;
  cout << firstName << " " << mi << " " << lastName << " "
    << score << endl;

  input.close();

  cout << "Done" << endl;

  return 0;
}

```
