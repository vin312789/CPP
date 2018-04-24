# class(類別) and object(物件)

[範例說明:圓形物件與面積](https://github.com/MyDearGreatTeacher/CPP/blob/master/20180424/TestCircle.cpp)

程式架構
```
[1]載入相關模組
[2]使用(標準)命名空間

[3]建立類別class
類別class包括
[3.1]屬性attribute:
[3.2]建構子(CONSTRUCTOR):兩個(含預設建構子DEFAULT)
[3.3]方法(METHOD/FUNCTION):

[4]main函式
[4.1]用類別class建立三個物件
[4.2]利用**物件.方法**及**物件.屬性**來執行運算
物件.屬性==>circle2.radius
物件.方法==>circle2.getArea()
```

[作業:球物件與體積及表面積]Sphere, getVolume 體積, getArea表面積

# 實作與定義分離(教科書9.6)

定義:Circle.h
```
class Circle
{
public:
  // The radius of this circle
  double radius;

  // Construct a default circle object
  Circle();

  // Construct a circle object
  Circle(double);

  // Return the area of this circle
  double getArea();
};
```

實作:Circle.cpp
```
#include "Circle.h"

// Construct a default circle object
Circle::Circle()
{
  radius = 1;
}

// Construct a circle object
Circle::Circle(double newRadius)
{
  radius = newRadius;
}

// Return the area of this circle
double Circle::getArea()
{
  return radius * radius * 3.14159;
}
```

主執行程式:
```
#include <iostream>
#include "Circle.h"
using namespace std;

int main()
{
  Circle circle1;
  Circle circle2(5.0);

  cout << "The area of the circle of radius "
    << circle1.radius << " is " << circle1.getArea() << endl;
  cout << "The area of the circle of radius "
    << circle2.radius << " is " << circle2.getArea() << endl;

  // Modify circle radius
  circle2.radius = 100;
  cout << "The area of the circle of radius "
    << circle2.radius << " is " << circle2.getArea() << endl;

  return 0;
}
```

# 封裝

[範例說明:圓形物件與面積](https://github.com/MyDearGreatTeacher/CPP/blob/master/20180424/TestCircle.cpp)
