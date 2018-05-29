# 運算子的多載
```


```
## 14.1 運算子與operator[]

比較下列兩個程式範例:
```
string s1("Washington");
string s2("California");
cout << "The first character in s1 is " << s1[0] << endl;
cout << "s1 + s2 is " << (s1 + s2) << endl;
cout << "s1 < s2? " << (s1 < s2) << endl;
```

```
string s1("Washington");
string s2("California");
cout << "The first character in s1 is " << s1.operator[](0) << endl;
cout << "s1 + s2 is " << operator+(s1, s2) << endl;
cout << "s1 < s2? " << operator<(s1, s2) << endl;

```
比較下列兩個程式範例:
```
vector<int> v;
v.push_back(3);
v.push_back(5);
cout << "The first element in v is " << v[0] << endl;
```

```


vector<int> v;
v.push_back(3);
v.push_back(5);
cout << "The first element in v is " << v.operator[](0) << endl;


```
## 14.2 建立有理數的 Rational 類別(參考課本)

Rational.h
```
#ifndef RATIONAL_H
#define RATIONAL_H
#include <string>
using namespace std;

class Rational
{
public:
  Rational();
  Rational(int numerator, int denominator);
  int getNumerator() const;
  int getDenominator() const;
  Rational add(const Rational& secondRational) const;
  Rational subtract(const Rational& secondRational) const;
  Rational multiply(const Rational& secondRational) const;
  Rational divide(const Rational& secondRational) const;
  int compareTo(const Rational& secondRational) const;
  bool equals(const Rational& secondRational) const;
  int intValue() const;
  double doubleValue() const;
  string toString() const;

private:
  int numerator;
  int denominator;
  static int gcd(int n, int d);
};

#endif
```

Rational.cpp
```
#include "Rational.h"
#include <sstream> // Used in toString to convert numbers to strings
#include <cstdlib> // For the abs function
Rational::Rational()
{
  numerator = 0;
  denominator = 1;
}

Rational::Rational(int numerator, int denominator)
{
  int factor = gcd(numerator, denominator);
  this->numerator = ((denominator > 0) ? 1 : -1) * numerator / factor;
  this->denominator = abs(denominator) / factor;
}

int Rational::getNumerator() const
{
  return numerator;
}

int Rational::getDenominator() const
{
  return denominator;
}

// Find GCD of two numbers 
int Rational::gcd(int n, int d) 
{
  int n1 = abs(n);
  int n2 = abs(d);
  int gcd = 1;

  for (int k = 1; k <= n1 && k <= n2; k++)
  {
    if (n1 % k == 0 && n2 % k == 0)
      gcd = k;
  }

  return gcd;
}

Rational Rational::add(const Rational& secondRational) const
{
  int n = numerator * secondRational.getDenominator() +
    denominator * secondRational.getNumerator();
  int d = denominator * secondRational.getDenominator();
  return Rational(n, d);
}

Rational Rational::subtract(const Rational& secondRational) const
{
  int n = numerator * secondRational.getDenominator()
    - denominator * secondRational.getNumerator();
  int d = denominator * secondRational.getDenominator();
  return Rational(n, d);
}

Rational Rational::multiply(const Rational& secondRational) const
{
  int n = numerator * secondRational.getNumerator();
  int d = denominator * secondRational.getDenominator();
  return Rational(n, d);
}

Rational Rational::divide(const Rational& secondRational) const
{
  int n = numerator * secondRational.getDenominator();
  int d = denominator * secondRational.numerator;
  return Rational(n, d);
}

int Rational::compareTo(const Rational& secondRational) const
{
  Rational temp = subtract(secondRational);
  if (temp.getNumerator() < 0)
    return -1;
  else if (temp.getNumerator() == 0)
    return 0;
  else
    return 1;
}

bool Rational::equals(const Rational& secondRational) const
{
  if (compareTo(secondRational) == 0)
    return true;
  else
    return false;
}

int Rational::intValue() const
{
  return getNumerator() / getDenominator();
}

double Rational::doubleValue() const
{
  return 1.0 * getNumerator() / getDenominator();
}

string Rational::toString() const
{
  stringstream ss;
  ss << numerator;

  if (denominator > 1)
    ss << "/" << denominator;

  return ss.str();
}
```

TestRationalClass.cpp
```
#include <iostream>
#include "Rational.h"
using namespace std;

int main()
{
  // Create and initialize two rational numbers r1 and r2.
  Rational r1(4, 2);
  Rational r2(2, 3);

  // Test toString, add, subtract, multiply, and divide
  cout << r1.toString() << " + " << r2.toString() << " = "
    << r1.add(r2).toString() << endl;
  cout << r1.toString() << " - " << r2.toString() << " = "
    << r1.subtract(r2).toString() << endl;
  cout << r1.toString() << " * " << r2.toString() << " = "
    << r1.multiply(r2).toString() << endl;
  cout << r1.toString() << " / " << r2.toString() << " = "
    << r1.divide(r2).toString() << endl;

  // Test intValue and double
  cout << "r2.intValue()" << " is " << r2.intValue() << endl;
  cout << "r2.doubleValue()" << " is " << r2.doubleValue() << endl;

  // Test compareTo and equal
  cout << "r1.compareTo(r2) is " << r1.compareTo(r2) << endl;
  cout << "r2.compareTo(r1) is " << r2.compareTo(r1) << endl;
  cout << "r1.compareTo(r1) is " << r1.compareTo(r1) << endl;
  cout << "r1.equals(r1) is " 
       << (r1.equals(r1) ? "true" : "false") << endl;
  cout << "r1.equals(r2) is " 
       << (r1.equals(r2) ? "true" : "false") << endl;

  return 0;
}
```
## 14.3 運算子函式(operator function)

###### 可被overloading的運算子
```
+      -      *      /     %     ^     &      |      ~      !     =     
<      >     +=     -=    *=    /=    %=     ^=     &=     |=     <<    
>>    >>=    <<=    ==    !=    <=    >=     &&     ||     ++     --
->*    ,      ->    []     ()   new  delete

```
###### 不可被overloading的運算子
```
?:    .     .*      ::
```


## 14.8.friend 函式(friend function)與 friend 類別(friend class)
>* 私有的類別成員是無法從類別外部存取的。
>* 有時候它允許一些信任的函式或類別可存取類別的私有的成員。
>* C++ 允許您使用 friend 關鍵字定義 friend 函式和friend 類別，讓這些信任的函式和類別可以存取另一類別的私有成員。

Date.h
```
#ifndef DATE_H
#define DATE_H
class Date
{
public:
  Date(int year, int month, int day)
  {
    this->year = year;
    this->month = month;
    this->day = day;
  }

  friend class AccessDate;//宣告AccessDate為friend class

private:
  int year;
  int month;
  int day;
};

#endif
```
Date.cpp
```
#include "Date.h"

Date::Date(int newYear, int newMonth, int newDay)
{
  year = newYear;
  month = newMonth;
  day = newDay;
}

int Date::getYear()
{
  return year;
}

void Date::setYear(int newYear)
{
  year = newYear;
}
```

TestFriendClass.cpp
```
#include <iostream>
#include "Date.h"
using namespace std;

class AccessDate
{
public:
  static void p()
  {
    Date birthDate(2010, 3, 4);//使用Date類別建立birthDate物件
    birthDate.year = 2000;
    cout << birthDate.year << endl;
  }
};

int main()
{
  AccessDate::p();

  return 0;
}
```
TestFriendFunction.cpp
```
#include <iostream>
using namespace std;

class Date
{
public:
  Date(int year, int month, int day)
  {
    this->year = year;
    this->month = month;
    this->day = day;
  }
  friend void p();

private:
  int year;
  int month;
  int day;
};

void p()
{
  Date date(2010, 5, 9);
  date.year = 2000;
  cout << date.year << endl;
}

int main()
{
  p();

  return 0;
}
```
## 14.12

RationalWithOperators.h
```
#ifndef RATIONALWITHOPERATORS_H
#define RATIONALWITHOPERATORS_H
#include <string>
#include <iostream>
using namespace std;

class Rational
{
public:
  Rational();
  Rational(int numerator, int denominator);
  int getNumerator() const;
  int getDenominator() const;
  Rational add(const Rational& secondRational) const;
  Rational subtract(const Rational& secondRational) const;
  Rational multiply(const Rational& secondRational) const;
  Rational divide(const Rational& secondRational) const;
  int compareTo(const Rational& secondRational) const;
  bool equals(const Rational& secondRational) const;
  int intValue() const;
  double doubleValue() const;
  string toString() const;

  Rational(int numerator); // Suitable for type conversion 

  // Define function operators for augmented operators
  Rational& operator+=(const Rational& secondRational);
  Rational& operator-=(const Rational& secondRational);
  Rational& operator*=(const Rational& secondRational);
  Rational& operator/=(const Rational& secondRational);

  // Define function operator []
  int& operator[](int index);

  // Define function operators for prefix ++ and --
  Rational& operator++();
  Rational& operator--();

  // Define function operators for postfix ++ and --
  Rational operator++(int dummy);
  Rational operator--(int dummy);

  // Define function operators for unary + and -
  Rational operator+();
  Rational operator-();

  // Define the << and >> operators
  friend ostream& operator<<(ostream&, const Rational&);
  friend istream& operator>>(istream&, Rational&);

private:
  int numerator;
  int denominator;
  static int gcd(int n, int d);
};

// Define nonmember function operators for relational operators
bool operator<(const Rational& r1, const Rational& r2);
bool operator<=(const Rational& r1, const Rational& r2);
bool operator>(const Rational& r1, const Rational& r2);
bool operator>=(const Rational& r1, const Rational& r2);
bool operator==(const Rational& r1, const Rational& r2);
bool operator!=(const Rational& r1, const Rational& r2);

// Define nonmember function operators for arithmetic operators
Rational operator+(const Rational& r1, const Rational& r2);
Rational operator-(const Rational& r1, const Rational& r2);
Rational operator*(const Rational& r1, const Rational& r2);
Rational operator/(const Rational& r1, const Rational& r2);

#endif


```


RationalWithOperators.cpp
```
#include "RationalWithOperators.h"
#include <sstream> // Used in toString to convert numbers to strings
#include <cstdlib> // For the abs function
Rational::Rational()
{
  numerator = 0;
  denominator = 1;
}

Rational::Rational(int numerator, int denominator)
{
  int factor = gcd(numerator, denominator);
  this->numerator = (denominator > 0 ? 1 : -1) * numerator / factor;
  this->denominator = abs(denominator) / factor;
}

int Rational::getNumerator() const
{
  return numerator;
}

int Rational::getDenominator() const
{
  return denominator;
}

// Find GCD of two numbers 
int Rational::gcd(int n, int d) 
{
  int n1 = abs(n);
  int n2 = abs(d);
  int gcd = 1;

  for (int k = 1; k <= n1 && k <= n2; k++)
  {
    if (n1 % k == 0 && n2 % k == 0)
      gcd = k;
  }

  return gcd;
}

Rational Rational::add(const Rational& secondRational) const
{
  int n = numerator * secondRational.getDenominator() +
    denominator * secondRational.getNumerator();
  int d = denominator * secondRational.getDenominator();
  return Rational(n, d);
}

Rational Rational::subtract(const Rational& secondRational) const
{
  int n = numerator * secondRational.getDenominator()
    - denominator * secondRational.getNumerator();
  int d = denominator * secondRational.getDenominator();
  return Rational(n, d);
}

Rational Rational::multiply(const Rational& secondRational) const
{
  int n = numerator * secondRational.getNumerator();
  int d = denominator * secondRational.getDenominator();
  return Rational(n, d);
}

Rational Rational::divide(const Rational& secondRational) const
{
  int n = numerator * secondRational.getDenominator();
  int d = denominator * secondRational.numerator;
  return Rational(n, d);
}

int Rational::compareTo(const Rational& secondRational) const
{
  Rational temp = subtract(secondRational);
  if (temp.getNumerator() < 0)
    return -1;
  else if (temp.getNumerator() == 0)
    return 0;
  else
    return 1;
}

bool Rational::equals(const Rational& secondRational) const
{
  if (compareTo(secondRational) == 0)
    return true;
  else
    return false;
}

int Rational::intValue() const
{
  return getNumerator() / getDenominator();
}

double Rational::doubleValue() const
{
  return 1.0 * getNumerator() / getDenominator();
}

string Rational::toString() const
{
  stringstream ss;
  ss << numerator;

  if (denominator > 1)
    ss << "/" << denominator;

  return ss.str();
}

Rational::Rational(int numerator) // Suitable for type conversion
{
  this->numerator = numerator;
  this->denominator = 1;
}

// Define function operators for augmented operators
Rational& Rational::operator+=(const Rational& secondRational)
{
  *this = add(secondRational);
  return *this;
}

Rational& Rational::operator-=(const Rational& secondRational)
{
  *this = subtract(secondRational);
  return *this;
}

Rational& Rational::operator*=(const Rational& secondRational)
{
  *this = multiply(secondRational);
  return *this;
}

Rational& Rational::operator/=(const Rational& secondRational)
{
  *this = divide(secondRational);
  return *this;
}

// Define function operator []
int& Rational::operator[](int index)
{
  if (index == 0)
    return numerator;
  else 
    return denominator;
}

// Define function operators for prefix ++ and --
Rational& Rational::operator++()
{
  numerator += denominator;
  return *this;
}

Rational& Rational::operator--()
{
  numerator -= denominator;
  return *this;
}

// Define function operators for postfix ++ and --
Rational Rational::operator++(int dummy)
{
  Rational temp(numerator, denominator);
  numerator += denominator;
  return temp;
}

Rational Rational::operator--(int dummy)
{
  Rational temp(numerator, denominator);
  numerator -= denominator;
  return temp;
}

// Define function operators for unary + and -
Rational Rational::operator+()
{
  return *this;
}

Rational Rational::operator-()
{
  return Rational(-numerator, denominator);
}

// Define the output and input operator
ostream& operator<<(ostream& out, const Rational& rational)
{
  if (rational.denominator == 1)
    out << rational.numerator;
  else
    out << rational.numerator << "/" << rational.denominator;
  return out;
}

istream& operator>>(istream& in, Rational& rational)
{
  cout << "Enter numerator: ";
  in >> rational.numerator;

  cout << "Enter denominator: ";
  in >> rational.denominator;
  return in;
}

// Define function operators for relational operators
bool operator<(const Rational& r1, const Rational& r2)
{
  return (r1.compareTo(r2) < 0);
}

bool operator<=(const Rational& r1, const Rational& r2)
{
  return (r1.compareTo(r2) <= 0);
}

bool operator>(const Rational& r1, const Rational& r2)
{
  return (r1.compareTo(r2) > 0);
}

bool operator>=(const Rational& r1, const Rational& r2)
{
  return (r1.compareTo(r2) >= 0);
}

bool operator==(const Rational& r1, const Rational& r2)
{
  return (r1.compareTo(r2) == 0);
}

bool operator!=(const Rational& r1, const Rational& r2)
{
  return (r1.compareTo(r2) != 0);
}

// Define non-member function operators for arithmetic operators
Rational operator+(const Rational& r1, const Rational& r2)
{
  return r1.add(r2);
}

Rational operator-(const Rational& r1, const Rational& r2)
{
  return r1.subtract(r2);
}

Rational operator*(const Rational& r1, const Rational& r2)
{
  return r1.multiply(r2);
}

Rational operator/(const Rational& r1, const Rational& r2)
{
  return r1.divide(r2);
}


```

TestRationalWithOperators.cpp
```
#include <iostream>
#include <string>
#include "RationalWithOperators.h"
using namespace std;

int main()
{
  // Create and initialize two rational numbers r1 and r2.
  Rational r1(4, 2);
  Rational r2(2, 3);

  // Test relational operators
  cout << r1 << " > " << r2 << " is " << 
    ((r1 > r2) ? "true" : "false") << endl;
  cout << r1 << " < " << r2 << " is " << 
    ((r1 < r2) ? "true" : "false") << endl;
  cout << r1 << " == " << r2 << " is " << 
    ((r1 == r2) ? "true" : "false") << endl;
  cout << r1 << " != " << r2 << " is " << 
    ((r1 != r2) ? "true" : "false") << endl;

  // Test toString, add, subtract, multiply, and divide operators
  cout << r1 << " + " << r2 << " = " << r1 + r2 << endl;
  cout << r1 << " - " << r2 << " = " << r1 - r2 << endl;
  cout << r1 << " * " << r2 << " = " << r1 * r2 << endl;
  cout << r1 << " / " << r2 << " = " << r1 / r2 << endl;

  // Test augmented operators
  Rational r3(1, 2);
  r3 += r1;
  cout << "r3 is " << r3 << endl;

  // Test function operator []
  Rational r4(1, 2);
  r4[0] = 3; r4[1] = 4;
  cout << "r4 is " << r4 << endl;

  // Test function operators for prefix ++ and --
  r3 = r4++;
  cout << "r3 is " << r3 << endl;
  cout << "r4 is " << r4 << endl;

  // Test function operator for conversion
  cout << "1 + " << r4 << " is " << (1 + r4) << endl;

  return 0;
}


```


```


```
