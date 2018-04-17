# 程式閱讀題(2018.4.17)
```
執行並說明下列程式的功能

```

### ex.array_1:(2018.4.17)
```
#include <iostream>
using namespace std;
int main()
{
	int i,a[10];

	for(i=0;i<10;i++)
		a[i]=i;

	for(i=0;i<10;i++)
		cout << a[i] << endl;
		
    return 0;
}
```

### ex.array_1:
```

```

### ex.array_1:
```

```


### ex.array_1:
```

```


### ex.array_2d_1:(2018.4.17)
```
#include <iostream>
#include <iomanip>
using namespace std;
int fun(int array[3][3])
{
	int i,j,t;
	for(i=0;i<3;i++)
		for(j=0;j<i;j++)
		{
			t=array[i][j];
			array[i][j]=array[j][i];
			array[j][i]=t;
		}
		return 0;
}
int main()
{
	int i,j;
	int array[3][3]={{1,2,3},{4,5,6},{7,8,9}};
	cout << "Converted Front" <<endl;
	for(i=0;i<3;i++)
	{
		for(j=0;j<3;j++)
			cout << setw(7) << array[i][j] ;
		cout<< endl;
	}
	fun(array);
	cout << "Converted result" <<endl;
	for(i=0;i<3;i++)
	{
		for(j=0;j<3;j++)
			cout << setw(7) << array[i][j] ;
		cout<< endl;
	}
    return 0;
}
```


### ex.array_1:
```

```


### ex.array_1:
```

```


### ex.array_1:
```

```


### ex.array_1:
```

```


### ex.array_1:
```

```


### ex.array_1:
```

```


### ex.array_1:
```

```


### ex.array_1:
```

```
