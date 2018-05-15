### string類別(class)的方法的使用

# template樣版==>see 教科書ch12

問題：
```
想要找出兩整數、兩浮點數、兩字元以及兩字串中的最大者。您會怎麼撰寫多載的函式
```

第一種寫法：
```
int maxValue(const int& value1, const int& value2)
{
  if (value1 > value2)
    return value1;
  else
    return value2;
}


double maxValue(const double& value1, const double& value2)
{
  if (value1 > value2)
    return value1;
  else
    return value2;
}


char maxValue(const char& value1, const char& value2)
{
  if (value1 > value2)
    return value1;
  else
    return value2;
}

```


第二種寫法：泛型(generic type)的函式
```
GenericType maxValue(
  const GenericType& value1, const GenericType& value2)
{
  if (value1 > value2)
    return value1;
  else
    return value2;
}
```

# template樣版

>* function template函式樣版==>上述的maxValue()函式
>* class template類別樣版==>參考下說明

# class template類別樣版:ch10.9 vs ch12.4

### ch10.9

### ch12.4 ==> class template類別樣版

>* [1]定義+實作 ==> GenericStack.h
>* [2]使用==> BMI.cpp


[1]定義+實作 ==> GenericStack.h
```
#ifndef STACK_H
#define STACK_H

template<typename T>
class Stack
{
public:
  Stack();
  bool empty() const;
  T peek() const;
  void push(T value);
  T pop();
  int getSize() const;

private:
  T elements[100];
  int size;
};

template<typename T>
Stack<T>::Stack()
{
  size = 0;
}

template<typename T>
bool Stack<T>::empty() const
{
  return (size == 0);
}

template<typename T>
T Stack<T>::peek() const
{
  return elements[size - 1];
}

template<typename T>
void Stack<T>::push(T value)
{
  elements[size++] = value;
}

template<typename T>
T Stack<T>::pop()
{
  return elements[--size];
}

template<typename T>
int Stack<T>::getSize() const
{
  return size;
}

#endif
```

使用==>TestStackOfIntegers.cpp
```
#include <iostream>
#include "StackOfIntegers.h"
using namespace std;

int main()
{
  StackOfIntegers stack;

  for (int i = 0; i < 10; i++)
    stack.push(i);

  while (!stack.isEmpty())
    cout << stack.pop() << " ";

  return 0;
}
```
