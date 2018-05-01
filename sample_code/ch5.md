#

```
#include <iostream>
using namespace std;
void ShowMessage(); //函式宣告語句
void ShowAge(); //函式宣告語句
void ShowIndex(); //函式宣告語句
void main()
{
	ShowMessage(); //函式呼叫語句
	ShowAge(); //函式呼叫語句
	ShowIndex(); //函式呼叫語句
}
void ShowMessage()
{
	cout << "HelloWorld!" << endl;
}
void ShowAge()
{
	int iAge=23;
	cout << "age is :" << iAge << endl;
}
void ShowIndex()
{
	int iIndex=10;
	cout << "Index is :" << iIndex << endl;
}
```
 
#

```
#include <iostream>
using namespace std;
void OutputInfo(const char* pchData = "One world,one dream!")
{
	cout << pchData << endl;	//輸出資訊
}
void main()
{
	OutputInfo();							//利用預設值作為函數實際參數
	OutputInfo("Beijing 2008 Olympic Games!");	//直接傳遞實際參數
}
```
 
#

```
#include <iostream>
#include <STDARG.H> //需要包含該標頭檔
using namespace std;
void OutputInfo(int num,...)						//定義一個省略號參數的函數
{
	va_list arguments;							//定義va_list類型變數
	va_start(arguments,num);
	while(num--)								//讀取所有參數的資料
	{
		char* pchData = va_arg(arguments,char*);	//獲取字串資料
		int iData = va_arg(arguments,int);			//獲取整型資料
		cout<< pchData << endl;					//輸出字串
		cout << iData << endl;						//輸出整數
	}
	va_end(arguments);
}

void main()
{
	OutputInfo(2,"Beijing",2008,"Olympic Games",2008);	//調用OutputInfo函數
}
```
 
#

```
#include <iostream.h>
void swap(int a,int b)
{
	int tmp;
	tmp=a;
	a=b;
	b=tmp;

}
void main()
{
	int x,y;
	cout << "懷謗跺杅" << endl;
	cin >> x;
	cin >> y;

	if(x<y)
		swap(x,y);
	cout << "x=" << x <<endl;
	cout << "y=" << y <<endl;
}
```
 
#

```
#include <iostream>
using namespace std;
long lCount;
void move(int n,char x,char y,char z)//將n個盤子從x針借助y針移到z針上。
{
	if(n==1)
		cout << "Times:" << ++lCount << x << "->" << z << endl;
	else
	{
		move(n-1,x,z,y);
		cout << "Times:" << ++lCount << x << "->" << z <<endl;
		move(n-1,y,x,z);
	}
}
void main()
{
	int n ;
	lCount=0;
	cout << "please input a number" << endl;
	  cin >> n ;
	move(n,'a','b','c');
}
```
 
#

```
#include <iostream>
using namespace std;
long Fac(int n)
{
	if(n==0)
		return 1;
	else
		return n*Fac(n-1);
}
void main()
{
	int n ;
	long f;
	cout << "please input a number" << endl;
	  cin >> n ;
	f=Fac(n);
	cout << "Result :" << f << endl;
}
```
 
#

```
#include <iostream>
using namespace std;
typedef unsigned int UINT; 		//自訂類型
long Fac(const UINT n)		//定義函數
{
	long ret = 1;				//定義結果變數
	for(int i=1; i<=n; i++)			//累計乘積
	{
		ret *= i;
	}
	return ret;					//返回結果
}

void main()
{
	int n ;
	long f;
	cout << "please input a number" << endl;
	  cin >> n ;
	f=Fac(n);
	cout << "Result :" << f << endl;
}
```
 
#

```
#include <iostream>
using namespace std;
int Add(int x ,int y)				//定義第一個重載函數
{
	cout << "int add" << endl;	//輸出資訊
	return x + y;				//設置函數返回值
}
double Add(double x,double y)		//定義第二個重載函數
{
	cout << "double add" << endl;	//輸出資訊
	return x + y;				//設置函數返回值
}
int main()
{
	int ivar = Add(5,2);			//調用第一個Add函數
	float fvar = Add(10.5,11.4);	//調用第二個Add函數
	return 0;
}
```

 
#

```
#include<iostream>
using namespace std;
void main()
{
	auto int i,j,k;
	cout <<"input the number:" << endl;
	cin >> i >> j;
	k=i+j;
	if( i!=0 && j!=0 )
	{
		auto int k;
		k=i-j;
		cout << "k :" << k << endl;//輸出變數K的值
	}
	cout << "k :" <<k << endl;//輸出變數k的值
}
```

 
#

```
#include<iostream>
using namespace std;
int add(int x)
{
	static int n=0;
	n=n+x;
	return n;
}
void main()
{
	int i,j,sum;
	cout << " input the number:" << endl;
	cin >> i;
	cout << "the result is:" << endl;
	for(j=1;j<=i;j++)
	{
		sum=add(j);
		cout << j << ":" <<sum << endl;
	}
}
```

 
#
```
#include<iostream>
using namespace std;
int subtration(int ,int );
int main()
{
	int i,j;
	cin >> i >> j;
	cout << subtration(i,j) <<endl;
	return 1;
}

int subtration(int a,int b)
{
	return a-b;
}
```
#

```
#include<iostream>
using namespace std;
int Max(int ,int );
int main()
{
	int i,j;
	cin >> i >> j;
	cout << Max(i,j) <<endl;
	return 1;
}

int Max(int a,int b)
{
	return a>b ? a : b ;
}
```
