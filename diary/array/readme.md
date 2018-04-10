# 陣列(array)

```
教科書
C++程式設計導論 (第三版)
Introduction to Programming with C++, 3rd Edition
作者： Y. Daniel Liang  譯者： 蔡明志
出版社：碁峰  出版日期：2014/07/29
```
```
參考書
最新C++物件導向程式設計實例入門(第四版)(附光碟)
作者： 高橋麻奈  譯者： 博碩文化  出版社：博碩  出版日期：2013/04/03
```
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
將其分開會導致語法錯誤。
 ```
 ```
錯在那? Answer Me!
double myList[4];
myList = {1.9, 2.9, 3.4, 3.5};
```
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

### 陣列元素的存取

```
陣列元素可透過索引做存取。
陣列索引是以 0 為基底；也就是說其範圍介於 0 到 arraySize-1 之間。
陣列大小的宣示式是用來指明陣列的元素個數。

double myList[10];
==>myList 儲存 10 個 double 值，索引範圍從 0 到 9。

陣列元素：
arrayName[index];

比方說，myList[9] 表示陣列 myList 的最後一個元素。


使用索引存取陣列元素時，若超出其範圍（如 myList[-1]與 myList[10]）都會發生超出範圍的錯誤。
此錯誤是相當嚴重的。不幸的是，C++ 不會告知，因此要非常小心確認索引在有效的範圍內。

```

### 陣列常用技術:

###### 印出陣列
```
for (int i = 0; i < ARRAY_SIZE; i++) 
{
  cout << myList[i] << " ";
}
```
###### 拷貝陣列

```
for (int i = 0; i < ARRAY_SIZE; i++) 
{
  list[i] = myList[i]; 
}

```

###### 加總陣列的所有元素
```
double total = 0;
for (int i = 0; i < ARRAY_SIZE; i++) 
{
  total += myList[i];
}

```

###### 找出最大元素

```
double max = myList[0];
for (int i = 1; i < ARRAY_SIZE; i++) 
{
  if (myList[i] > max) max = myList[i];
}

```


###### 找出最大元素的最小索引(如果有多個相同最大元素)

```
double max = myList[0];
int indexOfMax = 0;
for (int i = 1; i < ARRAY_SIZE; i++) 
{
  if (myList[i] > max) 
  {
    max = myList[i];
    indexOfMax = i;
  }
}


```

###### 隨機洗牌

```
srand(time(0));
for (int i = 0; i < ARRAY_SIZE; i++) 
{
  // Generate an index randomly
  int index = rand() % ARRAY_SIZE;
  double temp = myList[i];
  myList[i] = myList[index]; 
  myList[index] = temp;
}

```

###### 移動元素

```
double temp = myList[0]; 

for (int i = 1; i < myList.length; i++) 
{
  myList[i - 1] = myList[i];
}

myList[myList.length - 1] = temp;

```

### 包牌

```
Pick-10 樂透票上有 10 個 1 到 99 之間的唯一數字。

假設我們買了很多張，想讓它們涵蓋 1 到 99 之間的所有數字。
請撰寫一程式，從檔案讀取票上號碼，接著檢視是否涵蓋所有數字。

假設檔案裡的最後一個數字為 0。

```


```
#include <iostream>
using namespace std;

int main()
{
  bool isCovered[99];
  int number; // number read from a file

  // Initialize the array
  for (int i = 0; i < 99; i++)
    isCovered[i] = false;

  // Read each number and mark its corresponding element covered
  cin >> number;
  while (number != 0)
  {
    isCovered[number - 1] = true;
    cin >> number;
  }

  // Check if all covered
  bool allCovered = true; // Assume all covered initially
  for (int i = 0; i < 99; i++)
    if (!isCovered[i]) 
    {
       allCovered = false; // Find one number not covered
       break;
    }

  // Display result
  if (allCovered)
    cout << "The tickets cover all numbers" << endl;
  else
    cout << "The tickets don't cover all numbers" << endl;

  return 0;
}

```

執行

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
