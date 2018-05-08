
```
#include <iostream>
using namespace std;

int main()
{
  string s1("Welcome");
  s1.append(" to CPP"); 
  cout << s1 << endl; 
  
  string s2("Welcome");
  s2.append(" to C and C++", 0, 5); // appends " to C" to s2
  cout << s2 << endl; // s2 now becomes Welcome to C

  string s3("Welcome");
  s3.append(" to C and C++", 5); // appends " to C" to s3
  cout << s3 << endl; // s3 now becomes Welcome to C

  string s4("Welcome"); 
  s4.append(4, 'G'); // appends "GGGG" to s4
  cout << s4 << endl; // s4 now becomes WelcomeGGGG

  return 0;
}
```
