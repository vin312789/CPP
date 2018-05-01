# C++ 的 string 類別

建立字串

# 字串的處理(功能)

字串的附加

指定(assign)一字串

at、clear、erase 以及 empty 函式

length、size、capacity 以及 c_str() 函式

字串比較

取得子字串

字串搜尋(find)


插入字串與取代字串

字串運算子

數值轉換為字串

字串分割


字串合併

從螢幕讀取字串


### 從螢幕讀取字串
```
string city;
cout << "Enter a city: ";
cin >> city; // Read to array city
cout << "You entered " << city << endl;

```


```
string city;
cout << "Enter a city: ";
getline(cin, city, '\n'); // Same as getline(cin, city)
cout << "You entered " << city << endl;

```


```

```


```

```
