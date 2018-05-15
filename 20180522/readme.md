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

### ch10.9 整數類型的stack

>* [1]定義 ==> StackOfIntegers.h
>* [2]實作==> StackOfIntegers.cpp
>* [3]使用==> TestStackOfIntegers.cpp

[1]定義 ==> StackOfIntegers.h
```
#ifndef STACK_H
#define STACK_H

class StackOfIntegers
{
public:
  StackOfIntegers();
  bool isEmpty() const;
  int peek() const;
  void push(int value);
  int pop();
  int getSize() const;

private:
  int elements[100];
  int size;
};

#endif
```

[2]實作==> StackOfIntegers.cpp
```
#include "StackOfIntegers.h"

StackOfIntegers::StackOfIntegers()
{
  size = 0;
}

bool StackOfIntegers::isEmpty() const
{
  return (size == 0);
}

int StackOfIntegers::peek() const
{
  return elements[size - 1];
}

void StackOfIntegers::push(int value)
{
  elements[size++] = value;
}

int StackOfIntegers::pop()
{
  return elements[--size];
}

int StackOfIntegers::getSize() const
{
  return size;
}
```

[3]使用==>TestStackOfIntegers.cpp
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

Question:請撰寫浮點數的stack

### ch12.4 ==> class template類別樣版

>* [1]定義+實作 ==> GenericStack.h
>* [2]使用==>TestGenericStack.cpp


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
[2]使用==>TestGenericStack.cpp

```
#include <iostream>
#include <string>
#include "GenericStack.h"
using namespace std;

int main()
{
  // Create a stack of int values
  Stack<int> intStack;
  for (int i = 0; i < 10; i++)
    intStack.push(i);

  while (!intStack.empty())
    cout << intStack.pop() << " ";
  cout << endl;

  // Create a stack of strings
  Stack<string> stringStack;
  stringStack.push("Chicago");
  stringStack.push("Denver");
  stringStack.push("London");

  while (!stringStack.empty())
    cout << stringStack.pop() << " ";
  cout << endl;

  return 0;
}
```
