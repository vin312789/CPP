# 指標與動態記憶體管理

lab1:寫入資料於檔案

TestPointer.cpp
```
#include <iostream>
using namespace std;

int main()
{
  int count = 5;
  int* pCount = &count;

  cout << "The value of count is " << count << endl;
  cout << "The address of count is " << &count << endl;
  cout << "The address of count is " << pCount << endl;
  cout << "The value of count is " << *pCount << endl;

  return 0;
}
```
lab2:ArrayPointer.cpp
```
#include <iostream>
using namespace std;

int main()
{
  int list[6] = {11, 12, 13, 14, 15, 16};

  for (int i = 0; i < 6; i++)
    cout << "address: " << (list + i) << 
      " value: " << *(list + i) << " " <<
      " value: " << list[i] << endl;  

  return 0;
}
```

lab3:PointerWithIndex.cpp
```
#include <iostream>
using namespace std;

int main()
{
  int list[6] = {11, 12, 13, 14, 15, 16};
  int* p = list;

  for (int i = 0; i < 6; i++)
    cout << "address: " << (list + i) <<
      " value: " << *(list + i) << " " <<
      " value: " << list[i] << " " <<
      " value: " << *(p + i) << " " <<
      " value: " << p[i] << endl;

  return 0;
}
```

lab4: call by reference

TestPointerArgument.cpp

```
#include <iostream>
using namespace std;

// Swap two variables using pass-by-value
void swap1(int n1, int n2)
{
  int temp = n1;
  n1 = n2;
  n2 = temp;
}

// Swap two variables using pass-by-reference
void swap2(int& n1, int& n2)
{
  int temp = n1;
  n1 = n2;
  n2 = temp;
}

// Pass two pointers by value
void swap3(int* p1, int* p2)
{
  int temp = *p1;
  *p1 = *p2;
  *p2 = temp;
}

// Pass two pointers by reference
void swap4(int* &p1, int* &p2)
{
  int* temp = p1;
  p1 = p2;
  p2 = temp;
}

int main()
{
  // Declare and initialize variables
  int num1 = 1;
  int num2 = 2;

  cout << "Before invoking the swap function, num1 is "
    << num1 << " and num2 is " << num2 << endl;

  // Invoke the swap function to attempt to swap two variables
  swap1(num1, num2);

  cout << "After invoking the swap function, num1 is " << num1 <<
    " and num2 is " << num2 << endl;

  cout << "Before invoking the swap function, num1 is "
    << num1 << " and num2 is " << num2 << endl;

  // Invoke the swap function to attempt to swap two variables
  swap2(num1, num2);

  cout << "After invoking the swap function, num1 is " << num1 <<
    " and num2 is " << num2 << endl;

  cout << "Before invoking the swap function, num1 is "
    << num1 << " and num2 is " << num2 << endl;

  // Invoke the swap function to attempt to swap two variables
  swap3(&num1, &num2);

  cout << "After invoking the swap function, num1 is " << num1 <<
    " and num2 is " << num2 << endl;

  int* p1 = &num1;
  int* p2 = &num2;
  cout << "Before invoking the swap function, p1 is "
    << p1 << " and p2 is " << p2 << endl;

  // Invoke the swap function to attempt to swap two variables
  swap4(p1, p2);

  cout << "After invoking the swap function, p1 is " << p1 <<
    " and p2 is " << p2 << endl;

  return 0;
}

```

lab:
```

```

lab:
```

```
