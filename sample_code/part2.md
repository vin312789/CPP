#

```
#include<iostream>
using namespace std;
void main()
{
	int i=5,j=8,k=12,l=4,x1,x2;
	x1=i>j&&k>l;
	x2=!(i>j)&&k>l;
	printf("%d,%d\n",x1,x2);
}
```

#

```
#include<iostream>
using namespace std;
void main()
{
	int a=0x40,b;
	b=a<<1;
	cout << b << endl;
}
```
 

#

```
#include <iostream>
using namespace std;
void main()
{
	long nWord=0x12345678;
	int nBits;
	nBits=nWord & 0xFFFF;
	printf("low bits are 0x%x\n",nBits);
	nBits=(nWord & 0xFFFF0000)>>16;
	printf("hight bits is 0x%x\n",nBits);
}
```

#

```
#include<iostream>
using namespace std;
void main()
{
	int a=4,b=6,c=8,res1,res2;
	res1=a,res2=b+c;
	for(int i=0,j=0;i<2;i++)
	{
		printf("y=%d,x=%d\n",res1,res2);
	}
}
```
 

#

```
#include<iostream>
using namespace std;
void main()
{
	double result;
	char a='k';
	int b=10;
	float e=1.515;
	result=(a+b)-e;
	printf("%f\n",result);
}
```

#

```
#include<iostream>
using namespace std;
void main()
{
	float i,j;
	int k;
	i=60.25;
	j=20.5;
	k=(int)i+(int)j; 	
	cout << k << endl;
}
```
 
#

```
#include<iostream>
using namespace std;
int main()
{
	int a,b;
	cout << "inPut a and b:" << endl;
	cin >> a >> b;
	cout << "a:" << a <<endl;
	cout << "b:" << b <<endl;
	
	if(a>b)
	{
		b=a-b;
		a=a-b;
		b=a+b;
	}
	cout << "a:" << a <<endl;
	cout << "b:" << b <<endl;
	return 0;
}
```

#

```
#include<iostream>
using namespace std;
int main()
{
	int a=8;
	a+=a*=a/=a-6;
	cout << "Result :" << a << endl;
	return 1;
}
```
