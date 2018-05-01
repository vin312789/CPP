#

```
#include <iostream>
using namespace std;
void main()
{
	int iInput;
	cout << "Input a value:" << endl;
	cin >> iInput; //輸入一整型數
	if(iInput%2!=0) 
		cout << "The value is odd number" << endl;
}
```

#

```
#include <iostream>
using namespace std;
void main()
{
	int iInput;
	cin >> iInput;
	if(iInput>90)
		cout << "It is Good" << endl;
	else
		cout << "It is not Good" << endl;
}
```
 

#

```
#include <iostream>
using namespace std;
void main()
{
	int iInput;
	cout << "Input a value:" << endl;
	cin >> iInput; //輸入一整型數
	if(iInput%2!=0) 
		cout << "The value is odd number" << endl;
	else
		cout << "The value is even number" << endl;
}
```
 

#

```
#include <iostream>
using namespace std;
void main()
{
	int iInput;
	cin >> iInput;
	if(iInput>=90)
	{
		cout << "very good" <<endl;
	}
	else if(iInput>=80&& iInput<90)
	{
		cout << "good" <<endl;
	}
	else if(iInput>=70 && iInput <80)
	{
		cout << "good" <<endl;
	}
	else if(iInput>=60 && iInput <70)
	{
		cout << "normal" <<endl;
	}
	else if(iInput<60)
	{
		cout << "failure" <<endl;
	}
}

```
 

#

```
#include<iostream>
using namespace std;
void main()
{
    int iInput;
    cout << "Input number" << endl;
	cin >> iInput;//從鍵盤中輸入一個數
	(iInput%2!=0) ? cout << "The value is odd number" : cout << "The value is even number" ;
	cout << endl;
}

```

#

```
#include<iostream>
using namespace std;
void main()
{
	int iInput;
	cout << "Input number" << endl;
	cin >> iInput;//從鍵盤中輸入一個數
	(iInput%3==0 && iInput%5==0)?cout << "yes" : cout<<"no";	
	cout << endl;
}

```
 

#

```
#include<iostream>
using namespace std;
void main()
{
	int iInput;
    cout << "Input number" << endl;
	cin >> iInput;//從鍵盤中輸入一個數
	(iInput%3==0)? 
		((iInput%5==0) ? cout << "yes" : cout << "no" )
		: cout << "no";	
	cout << endl;
}

```
 

#

```
#include <iostream>
#include <iomanip>
using namespace std;
void main()
{
	char iInput;
	cin >> iInput;
	switch (iInput)
	{
	case 'A':
	cout << "very good" << endl;
	break;
	case 'B':
	cout << "good" << endl;
	break;
	case 'C':
	cout << "normal" << endl;
	break;
	case 'D':
	cout << "failure" << endl;
	break;
	default:
		cout << "input error" << endl;
	}
}


```
 

#

```
#include <iostream>
using namespace std;
void main()
{
	int iInput;
	cin >> iInput;
	if(iInput = 'A')
	{
		cout << "very good" <<endl;
		return ;
	}
	if(iInput = 'B')
	{
		cout << "good" <<endl;
		return ;
	}
	if(iInput = 'C')
	{
		cout << "normal" <<endl;
		return ;
	}
	if(iInput = 'D')
	{
		cout << "failure" <<endl;
		return ;
	}
	cout << "input error" << endl;
}


```
 

#

```
#include <iostream>
using namespace std;
void main()
{
	char iInput;
	cin >> iInput;
	if(iInput == 'A')
	{
		cout << "very good" <<endl;
		return ;
	}else if(iInput == 'B')
	{
		cout << "good" <<endl;
		return ;
	}else if(iInput == 'C')
	{
		cout << "normal" <<endl;
		return ;
	}else if(iInput == 'D')
	{
		cout << "failure" <<endl;
		return ;
	}else
	cout << "input error" << endl;
}

```
 

#

```
#include <iostream>
using namespace std;
void main()
{
	int iYear;
	cout << "please input number" << endl;
	cin >> iYear;
	if(iYear%4==0)
	{
		if(iYear%100==0)
		{
			if(iYear%400==0)
				cout << "It is a leap year" << endl;
			else
				cout << "It is not a leap year" << endl;
		}
		else
			cout << "It is not a leap year" << endl;
	}
	else
		cout << "It is not a leap year" << endl;
}

```
 

#

```
#include <iostream>
using namespace std;
void main()
{
	int iYear;
	cout << "please input number" << endl;
	cin >> iYear;
	if(iYear%4==0 && iYear%100!=0 || iYear%400==0)
		cout << "It is a leap year" << endl;
	else
		cout << "It is not a leap year" << endl;
}

```
 

#

```
#include<iostream>
using namespace std;
int main()
{
	double iResult=0;
	int iInput=0;
	cout << "輸入工資" << endl;
	cin >> iInput;
	if(iInput <=0)
	{
		cout << "輸入錯誤" << endl;
		return 0;
	}
	if(iInput >= 5000)
	{
		iResult=1.1*iInput;
		cout<< "調整後工資為：" << iResult <<endl;
	}
	else if(iInput >= 2500 && iInput < 5000)
	{
		iResult=1.15*iInput;
		cout << "調整後工資為：" <<  iResult << endl;
	}
	else if(iInput < 2500)
	{
		iResult=1.2*iInput;
		cout << "調整後工資為：" << iResult << endl;
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
	int i,j;
	cin >> i >> j;
	if(i>j)
		cout << "The Max:" << i << endl;
	else 
		cout << "The Max:" << j << endl;
}
```
 

#

```
#include<iostream>
using namespace std;
int main()
{
	int tmp[4];
	int a=0,b=0,c=0;
	cin >>a >> b >> c;
	tmp[0]=a;
	tmp[1]=b;
	tmp[2]=c;
	tmp[3]=-1;
	for(int i=1;i<3;i++)
	{
		for(int j=2;j>=i;j--)
		{
			if(tmp[j]<tmp[j-1])
			{
				tmp[3]=tmp[j-1];
				tmp[j-1]=tmp[j];
				tmp[j]=tmp[3];
			}
		}
	}

	for(int k=0;k<3;k++)
		cout << tmp[k] << endl;

}
```
 
