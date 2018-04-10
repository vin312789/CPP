# 陣列(array)

```
陣列是一種用於儲存相同型態資料的資料儲存結構。
```
```
宣告陣列

datatype arrayRefVar[arraySize];

double myarray[10];


在標準的 C++，宣告陣列的大小必須是一常數運算式。
```
```
錯在那? Answer Me!
不合法的程式碼：
int size = 4;
double myList[size]; 
```
```
合法的程式碼：
const int size = 4;
double myList[size];
```
```
當宣告一陣列時，其元素將會有任意值。

```
### 宣告及初始化陣列
```
陣列初始化器
double myList[4] = {1.9, 2.9, 3.4, 3.5};


double myList[4];
myList[0] = 1.9;
myList[1] = 2.9;
myList[2] = 3.4;
myList[3] = 3.5;

使用陣列初始化器，必須在同一行敘述進行宣告與初始化的動作。
將其分開會導致語法錯誤。比方說，以下這段敘述是錯的：
  
 ```
 ```
錯在那? Answer Me!
double myList[4];
myList = {1.9, 2.9, 3.4, 3.5};
```
當使用陣列初始化器來宣告與初始化時，C++ 允許您省略陣列大小。

double myList[] = {1.9, 2.9, 3.4, 3.5};

編譯器將自動計算陣列有多少個元素。

```

```
C++允許您初始部分陣列的元素值。

底下敘述指定 1.2 與 3.7 給陣列的前二個元素。而其他元素的初始值將為 0。

double myList[4] = {1.2, 3.7};

```

```
隨機數值初始化陣列

for (int i = 0; i < ARRAY_SIZE; i++) 
{
  myList[i] = rand() % 100;
}
利用 0 到 99 的隨機數值，對陣列myList 進行初始化動作
```
```
```
#include <iostream>
using namespace std;

int main()
{
  const int NUMBER_OF_ELEMENTS = 2;
  double numbers[NUMBER_OF_ELEMENTS];
  double sum = 0;

  for (int i = 0; i < NUMBER_OF_ELEMENTS; i++)
  {
    cout << "Enter a new number: ";
    cin >> numbers[i];
    sum += numbers[i];
  }

  double average = sum / NUMBER_OF_ELEMENTS;

  int count = 0; // The number of elements above average
  for (int i = 0; i < NUMBER_OF_ELEMENTS; i++)
    if (numbers[i] > average)
      count++;

  cout << "Average is " << average << endl;
  cout << "Number of elements above the average " << count << endl;

  return 0;
}
```

### 宣告及初始化陣列



```

```




```

```




```

```




```

```



```

```



```

```



```

```



```

```



```

```


```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```
