# 

```
#include<iostream>
using namespace std;
void main()
{
	char c1,c2;
	c1='a';
	c2='b'; 
	int i1,i2;
	printf("%c,%d\n%c,%d",c1,c1,c2,c2);
}

```

#

```
#include<iostream>
using namespace std;
void main()
{
  char ch1,ch2;
  ch1='a'; ch2='B';							/*給ch1、ch2賦值*/
  printf("ch1=%c,ch2=%c\n",ch1-32,ch2+32);		/*用字元形式輸出一個大於256的數值*/
  printf("ch1+10=%d\n", ch1+10);
  printf("ch1+10=%c\n", ch1+10);
  printf("ch2+10=%d\n", ch2+10);
  printf("ch2+10=%c\n", ch2+10);
}
```
 

#

```
#include <iostream.h>
void main()
{
	int i=0;
cout << i<< endl;
	cout << "HelloWorld" <<endl;
}
```

#

```
#include <iostream>
#include <iomanip>
using namespace std;
void main()
{
	double a=123.456789012345;
	cout << a << endl;  
	cout << setprecision(9) << a << endl;
	cout << setprecision(6);//恢復默認格式(精度為6)
	cout << setiosflags(ios::fixed); 
	cout << setiosflags(ios::fixed) << setprecision(8) << a << endl;
	cout << setiosflags(ios::scientific) << a << endl;
	cout << setiosflags(ios::scientific) << setprecision(4) << a << endl; 
}
```
 

#

```
#include <iostream>
#include <iomanip>
using namespace std;
void main()
{
	int b=123456;//對b賦初值
	cout << b << endl;//輸出： 123456
	cout << hex << b << endl; //輸出： 1e240     
	cout << setiosflags(ios::uppercase) << b << endl; //輸出： 1E240     
	cout << setw(10) << b <<','<< b << endl; //輸出：     123456，123456
	cout << setfill('*') << setw(10) << b << endl; //輸出： **** 123456
	cout << setiosflags(ios::showpos) << b << endl; //輸出： +123456
}
```

#

```
#include <iostream.h>
#include <iomanip.h>
void main()
{
	int i=0x2F,j=255;
	cout << i << endl;
	cout << hex << i << endl;
	cout << hex << j << endl;
	cout << hex << setiosflags(ios::uppercase) << j << endl;
}
```
 

#

```
#include <iostream>
using namespace std;
void main()
{
	int x=123;
	double y=-3.1415;
	cout << "x=";
	cout.width(10);
	cout << x;
	cout << "y=";
	cout.width(10);
	cout << y <<endl;
	cout.setf(ios::left);
	cout << "x=";
	cout.width(10);
	cout << x;
	cout << "y=";
	cout << y <<endl;
	cout.fill('*');
	cout.precision(4);
	cout.setf(ios::showpos);
	cout << "x=";
	cout.width(10);
	cout << x;
	cout << "y=";
	cout.width(10);
	cout << y <<endl;
}
```
 

#

```
#include <iostream>
using namespace std;
void main()
{
	float x=20,y=-400.00;
	cout << x <<' '<< y << endl;
	cout.setf(ios::showpoint);//強制顯示小數點和無效0
	cout << x <<' '<< y << endl;
	cout.unsetf(ios::showpoint);
	cout.setf(ios::scientific);//設置按科學標記法輸出
	cout << x <<' '<< y << endl;
	cout.setf(ios::fixed);//設置按定點標記法輸出
	cout << x <<' '<< y << endl;
}
```

#

```
#include <iostream>
void main()
{
	printf("%4d\n",1);//用空格做預留位置
	printf("%04d\n",1);//用0來做預留位置
	int a=10,b=20;
	printf("%d%d\n",a,b);//相當於字元連接
}
```
 

#

```
#include<iostream>
void main()
{
	char *str="helloworld";
	printf("%s\n%10.5s\n%-10.2s\n%.3s",str,str,str,str);
}
```

#

```
#include <iostream>
void main()
{
	float i=2998.453257845;
	double j=2998.453257845;
	printf("%f\n%15.2f\n%-10.3f\n%f",i,i,i,j); 		/*以指定的格式輸出i和j*/
}
```

#

```
#include <iostream>
void main()
{
	float i=2998.453257845;
	double j=2998.453257845;
	printf("%e\n%15.2e\n%-10.3e\n%e",i,i,i,j);
}
```
 

#

```
#include <iostream.h>
int main()
{
	cout << "NiceWork!" << endl;
	return 1;
}
```

#

```
#include<iostream>
using namespace std;
int mul(int x)
{
	static int n=1;
	n=n*x;
	return n;
}
void main()
{
	int i=3;
	int	j=0;
	int iResult;
	for(j=0;j<3;j++)
	{
		iResult=mul(i);
	}
	cout << "Result :" << iResult << endl;
}
```
 

#

```
#include<iostream>
using namespace std;
int main()
{
	int i=123;
	printf("printf result :%d\n",123);
	cout << "cout result :" << i << endl;
	return 1;
}
```
