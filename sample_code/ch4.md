#

```
#include <iostream>
using namespace std;
void main()
{
	int sum=0,i=1;
	while(i<=10)
	{
		sum=sum+i;
		i++;
	}
	cout << "the result :" << sum << endl;
}
```

#

```
#include <iostream>
using namespace std;
void main()
{
	int sum=0,i=1;
	do
	{
		sum=sum+i;
		i++;
	}while(i<=10);
	cout << "the result :" << sum << endl;
}

```
 

#

```
#include <iostream>
using namespace std;
void main()
{
	int i=0,j=0;
	cout << "before do_while j=" << j << endl;
	do
	{
		j++;
	}while(i>1);
	cout << "after do_while j=" << j << endl;
}


```

#

```
#include <iostream>
using namespace std;
void main()
{
	int i=0,j=0;
	cout << "before while j=" << j << endl;
	while(i>1)
	{
		j++;
	}
	cout << "after while j=" << j << endl;
}

```

#

```
#include <iostream>
using namespace std;
void main()
{
	int sum=0;
	int i;
	for(i=1;i<=10;i++) 
		sum+=i;
    cout << "the result :" << sum << endl;
}


```

#

```
#include <iostream>
using namespace std;
void main()
{
	int i,n,sum;
	sum=0;
	cout<< "input 10 number" << endl;
	for(i=1;i<=10;i++)
	{
		cout<< i<< ":" ;
			cin >> n;
		if(n<0) 	//判斷輸入是否為負數
			break;
		sum+=n; 	//對輸入的數進行累加
	}
	cout << "The Result :"<< sum << endl;
}
```

#

```
#include <iostream>
using namespace std;
void main()
{
	int i,n,sum;
	sum=0;
	cout<< "input 10 number" << endl;
	for(i=1;i<=10;i++)
	{
		cout<< i<< ":" ;
			cin >> n;
		if(n<0)	//判斷輸入是否為負數
			continue;
		sum+=n;	//對輸入的數進行累加
	}
	cout << "The Result :"<< sum << endl;
}
```
 
#
```
#include <iostream>
using namespace std;
void main()
{
	int ivar = 0 ;			//定義一個整型變數，初始化為0
	int num = 0;			//定義一個整型變數，初始化為0
label:  					//定義一個標籤
	ivar++;					//ivar自加1
	num += ivar;			//累加求和
	if (ivar <10)			//判斷ivar是否小於100
	{
		goto label;			//轉向標籤
	}
	cout << num << endl;
}
```

#

```
#include <iostream>
using namespace std;
void main()
{
    int i, j, k; 						
    for (i = 1; i <= 5; i++)					//控制行數
    {
        for (j = 1; j <= 5-i; j++)				//控制空格數
            cout << " ";
        for (k = 1; k <= 2 *i - 1; k++)			//控制列印*號的數量
            cout << "*";
        cout << endl;
    }
}
```

#
```
#include <iostream>
#include <iomanip>
using namespace std;
void main(void)
{
	int i,j;
	i=1;
	j=1;
	for(i=1;i<10;i++)
	{
		for(j=1;j<i+1;j++)
			cout  << setw(2) << i << "*" << j << "=" << setw(2) << i*j ;
		cout << endl;
	}
}
```

#
```
#include <iostream>
using namespace std;
int main()
{
	int a,b,c;
	int input;
	for(input=100;input<=999;input++)
	{
		a=input / 100;			//求百位
		b=(input % 100) /10;		//求十位
		c=input %10;			//求個位
		if(a*a*a+b*b*b+c*c*c == input)
			cout << input<< endl;
	}
	return 0;
}
```

#

```
#include <iostream>
#include <iomanip>
using namespace std;
long combi(int n,int r)
{
	int i;
	long p=1;
	for(i=1;i<=r;i++)
		p=p*(n-i+1)/i;
	return p;
}
void main()
{
	int n,r,t;
	for(n=0;n<=12;n++)//控制行數
	{
		for(r=0;r<=n;r++)
		{
			int i;
			if(r==0)
			{
				for(i=0;i<=(12-n);i++)
					cout << "  " ;//每行第一個元素的位置
			}else
				cout << "  " ; //每個數之間空兩個格
		cout << setw(3) << combi(n,r);		
		}
		cout << endl;
	}
}
```
 
#

```
#include <iostream>
using namespace std;
void main()
{
	int score[101]={0};
	int juni[102]={0};
	int count =0,i;
	do{
		cout << "Input score: " ;
			cin >> score[count++];
	}while(score[count-1]!=-1);
	count--;
	for(i=0;i<count;i++)
		juni[score[i]]++;
	juni[101]=1;
	for(i=100;i>=0;i--)
		juni[i]=juni[i]+juni[i+1];
	cout << "Result: " <<endl;
	for(i=0;i<count;i++)
	{
		cout << score[i] << "is";
		cout << juni[score[i]+1] << endl;
	}
}
```
 
#

```
#include <iostream.h>
#include <iomanip.h>

int main()
{
	char cTmp;
	int iASCII;
	for(int i=1;i<=26;i++)
	{
		cTmp='A'+i-1;
		cout << setw(5) << cTmp;
		cout << ":";
		iASCII=cTmp;
		cout.setf(ios::uppercase);
		cout << hex << iASCII;
		if(i%4==0)
			cout << endl;
	}
	cout << endl;
	return 1;
}
```
 
#

```
#include<iostream>
using namespace std;
int main()
{
	for(int i=0;i<=100;i++)
	{
		if(i%3==0)
			continue;
		cout << i << endl;
	}
	return 1;
}
```

 
#
```
#include<iostream>
using namespace std;
int main()
{
	
	for(int i=1;i<=4;i++)
	{
		for(int m=0;m<4-i;m++)
		{
			cout << " " ;	
		}
		for(int n=0;n<(2*i-1);n++)
		{
				cout << "*" ;
		}
			cout << endl;
	}
	
	for(int j=3;j>=1;j--)
	{
		for(int m=0;m<4-j;m++)
		{
			cout << " " ;	
		}
		for(int n=0;n<(2*j-1);n++)
		{
				cout << "*" ;
		}
			cout << endl;
	}
	return 1;
}




/*
       *
      ***
     *****
	*******
     *****
      ***
       *

*/

```
 
