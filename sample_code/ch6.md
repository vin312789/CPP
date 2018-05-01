#

```
#include <iostream>
using namespace std;
void main()
{
	int i,a[10];
	//利用迴圈，分別為10個元素賦值
	for(i=0;i<10;i++)
		a[i]=i;
	//將陣列中的10的元素輸出到顯示裝置
	for(i=0;i<10;i++)
		cout << a[i] << endl;
}
```

 
#
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
void main()
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
}
```
#

```
#include<iostream>
using namespace std;
void main()
{
	int i;
	char array[12];
	array[0]='a';
	array[1]='b';
	printf("%s\n",array);
}

```

#

```
#include<iostream>
using namespace std;
void main()
{
	int i;
	char array[12]={'H','E','L','L','O',' ','W','O','R','L','D'};
	for(i=0;i<12;i++)
		cout<<array[i];
	cout << endl;
}
```
 
#

```
#include<iostream>
#include<string>
using namespace std;
void main()
{
	char str1[30],str2[20];
	cout<<"please input string1:"<< endl;
	gets(str1);
	cout<<"please input string2:"<<endl;
	gets(str2);
	strcat(str1,str2);
	cout <<"Now the string1 is:"<<endl;
	puts(str1);
}

```

 
#
```
#include<iostream>
using namespace std;
void main()
{
	int i=0,j=0;					//定義整型變數
	char a[100],b[50];			//定義字元型陣列			
	cout <<"please input string1:" << endl;
	cin >> a;					//輸入字串存於陣列a中
	cout  << "please input string2:" << endl;
	cin >> b;					//輸入字串存於陣列b中
	while(a[i]!='\0')				//逐個遍歷陣列a中的元素，直到遇到字串結束標誌
		i++;
	while(b[j]!='\0')				//逐個遍歷陣列b中的元素，直到遇到字串結束標誌
		a[i++]=b[j++];			//將陣列b中的元素存入陣列a中並從陣列a原來存放'\0'位置開始，覆蓋'\0'
		a[i]='\0';				//在合併後的兩個字串的最後加'\0'
	cout << a << endl;			//輸出合併後的字串
} 

```

 
#

```
#include<iostream>
#include<string>
using namespace std;
void main()
{
	char str1[30],str2[20];
	cout<<"please input string1:"<< endl;
	gets(str1);
	cout<<"please input string2:"<<endl;
	gets(str2);
	strcpy(str1,str2);
	cout<<"Now the string1 is:\n"<<endl;
	puts(str1);
}

```
 
#

```
#include<iostream>
#include <string>
using namespace std;

#include<string>
void main()
{
	char str1[30],str2[20];
	int i=0;
	cout<<"please input string1:"<< endl;
	gets(str1);
	cout<<"please input string2:"<<endl;
	gets(str2);
	i=strcmp(str1,str2);
	if(i>0)
	cout <<"str1>str2"<<endl;
	else
	if(i<0)
	cout <<"str1<str2"<<endl;
	else
	cout <<"str1=str2"<<endl;
}

```

 
#

```
#include<iostream>
#include <string>
using namespace std;
void main()
{
	char str1[30],str2[20];
	int len1,len2;
	cout<<"please input string1:"<< endl;
	gets(str1);
	cout<<"please input string2:"<<endl;
	gets(str2);
	len1=strlen(str1);
	len2=strlen(str2);
	cout <<"the length of string1 is:"<< len1 <<endl;
	cout <<"the length of string2 is:"<< len2 <<endl;
}

```

#

```
#include <iostream>
using namespace std;
void main()
{
	int a=100;
	int *p=&a;
	printf("%d\n",p);
}

```
 
#

```
#include <iostream>
using namespace std;
void main()
{
	int *p1,*p2;
	int	*p;  
	int a,b;
	cout << "input a: " << endl;
	cin >> a;
	cout << "input b: " << endl;
	cin >> b;
	p1=&a;p2=&b;
	if(a<b)
	{
		p=p1;
		p1=p2;
		p2=p;
	}
	cout << "a=" << a;
	cout << " ";
	cout << "b=" << b;
	cout << endl;
	cout << "max=" << *p1 << ",min=" << *p2 <<endl;
}
```

 
#

```
#include <iostream>
using namespace std;
void main()
{
	int a=100;
	int *p=&a;
	cout << " a=" << a <<endl;
	cout << "*p=" << *p <<endl;
}
```

#

```
#include <iostream>
using namespace std;
void main()
{
	int a=100;
	int *p=&a;
	printf("address:%d\n",p);
	p++;
	printf("address:%d\n",p);
	p--;
	printf("address:%d\n",p);
	p--;
	printf("address:%d\n",p);
}
```

 
#

```
#include <iostream>
using namespace std;
void main()
{
	int i,a[10];
	int *p;
	//利用迴圈，分別為10個元素賦值
	for(i=0;i<10;i++)
		a[i]=i;
	//將陣列中的10的元素輸出到顯示裝置
	p=&a[0];
	for(i=0;i<10;i++,p++)
		cout << *p << endl;
}
```

 
#
```
#include <iostream>
using namespace std;
void main()
{
	int array1[3][4]={{1,2,3,4},
	{5,6,7,8},
	{9,10,11,12}};
	int array2[12]={0};
	int row,col,i;
	cout << "array old" <<endl;
	for(row=0;row<3;row++)
	{
		for(col=0;col<4;col++)
		{
			cout << array1[row][col];
		}
		cout << endl;
	}
	cout << "array new" << endl;
	for(row=0;row<3;row++)
	{
		for(col=0;col<4;col++)
		{
			i=col+row*4;
			array2[i]=array1[row][col];
		}
	}
	for(i=0;i<12;i++)
		cout << array2[i] << endl;
}
```

 
#

```
#include <iostream>
#include <iomanip>
using namespace std;
void main()
{
	int a[4][3]={1,2,3,4,5,6,7,8,9,10,11,12};
	int *p;
	p=a[0];
	for(int i=0;i<sizeof(a)/sizeof(int);i++)
	{
		cout << "address:";
		cout << a[i] ;
		cout << " is " ;
		cout << *p++ << endl;
	}
}
```

#

```
#include<iostream>
using namespace std;
void main()
{
	int i,j;
	int a[4][3]={{1,2,3},{4,5,6},{7,8,9},{10,11,12}};
	cout << "the array is: " << endl;
	for(i=0;i<4;i++)//лл
	{
		for(j=0;j<3;j++)//┴л
			cout <<*(*(a+i)+j) << endl;
	}
}
```
#

```
#include<iostream>
using namespace std;
void main()
{
	char str1[50],str2[30],*p1,*p2;
	p1=str1;
	p2=str2;
	cout << "please input string1:"<< endl;
	gets(str1);
	cout << "please input string2:"<< endl;
	gets(str2);
	while(*p1!='\0')
	p1++;
	while(*p2!='\0')
	*p1++=*p2++;
	*p1='\0';
	cout << "the new string is:"<< endl;
	puts(str1);
}
```

 
#
```
/*
#include <iostream>
#include <iomanip>
using namespace std;
int avg(int a,int b);
void main()
{
	int iWidth,iLenght,iResult;
	i=10;
	j=30;
	iResult=avg(i,j);
	cout << iResult <<endl;
}

int avg(int a,int b)
{
	return (a+b)/2;
}

*/
#include <iostream>
#include <iomanip>
using namespace std;
int avg(int a,int b);
void main()
{
	int iWidth,iLenght,iResult;
	iWidth=10;
	iLenght=30;
	int (*pFun)(int,int);  
	pFun=avg;

	iResult=(*pFun)(iWidth,iLenght);
	cout << iResult <<endl;
}
int avg(int a,int b)
{
	return (a+b)/2;
}
```

#

```
#include <iostream>
using namespace std;
void main()
{
	int a;
	int & ref_a =a;
	a=100;
	cout << "a= "<< a <<endl;
	cout << "ref_a="<< ref_a << endl;
	a=2;
	cout << "a= "<< a <<endl;
	cout << "ref_a="<< ref_a << endl;
	int b=20;
	ref_a=b;
	cout << "a= "<< a <<endl;
	cout << "ref_a="<< ref_a << endl;
	ref_a--;
	cout << "a= "<< a <<endl;
	cout << "ref_a="<< ref_a << endl;
}
```

 
#

```
#include <iostream>
using namespace std;
swap(int & a,int & b)
{
	int tmp;
	tmp=a;
	a=b;
	b=tmp;

}
void main()
{
	int x,y;
	cout << "input two number " << endl;
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
swap(int *a,int *b)
{
	int tmp;
	tmp=*a;
	*a=*b;
	*b=tmp;
}
void main()
{
	int x,y;
	int *p_x,*p_y;
	cout << " input two number " << endl;
	cin >> x;
	cin >> y;
	p_x=&x;p_y=&y;
	if(x<y)
		swap(p_x,p_y);
	cout << "x=" << x <<endl;
	cout << "y=" << y <<endl;
}
```

 
#

```
#include<iostream>
using namespace std;
void main(int argc,char *argv[])
{
	cout << "the list of parameter:" << endl;
	while(argc>1)
	{
		++argv;
		cout << *argv << endl;
		--argc;
	}
}
```

 
#
```
#include<iostream>
using namespace std;
#define N 4
void mix(int (*a)[N],int m)//進行比較和交換的函數
{
	int value,i,j;
	for(i=0;i<m;i++)
	{
		value=*(*(a+i));
		for(j=0;j<N;j++)
		if(*(*(a+i)+j)<value)
		value=*(*(a+i)+j);
		cout <<"line " << i ;
		cout <<":the mix number is " << value << endl;//輸出最小值
	}
}
void main()
{
	int a[3][N],i,j;
	int (*p)[N];
	p=&a[0];
	cout << "please input:" << endl;
	for(i=0;i<3;i++)
	for(j=0;j<N;j++)
	cin >> a[i][j];
	mix(p,3);
}
```

 
#
```
#include <iostream>
using namespace std;
void sort(char *name[],int n) //對字串進行排序
{ 
	char *temp;
	int i,j,k;
	for(i=0;i<n-1;i++)
	{
		k=i;
		for(j=i+1;j<n;j++)
		if(strcmp(name[k],name[j])>0) k=j;
		if(k!=i)
		{ 
			temp=name[i];name[i]=name[k];name[k]=temp;
		}
	}
}
void print(char *name[],int n)//輸出字串陣列中的元素
{ 
	int i=0;
	char *p;
	p=name[0];
	while(i<n)  
	{
		p=*(name+i++);
		cout<<p<<endl;
	}
}
int main( )
{ 
	char *name[]={"mingri","soft","C++","mr"};  //定義指標陣列
	int n=4;
	sort(name,n);
	print(name,n);
	return 0;
}
```

#

```
#include<iostream>
using namespace std;

int main()
{
	char name[10][10];//存儲十個學生的姓名，每個學生姓名不超過10個字元
	/*
	char buf[10];
	for(int i=0;i<10;i++)
	{
		cin >> buf;
		strncpy(name[i],buf,10);//通過輸入將學生姓名錄入
	}
	*/
	strcpy(name[0],"Mary");
	strcpy(name[1],"Jam");
	strcpy(name[2],"Jack");
	strcpy(name[3],"Jose");
	strcpy(name[4],"Hery");
	strcpy(name[5],"Mark");
	strcpy(name[6],"Dobbs");
	strcpy(name[7],"Steven");
	strcpy(name[8],"Stanly");
	strcpy(name[9],"John");

	/*
	int score[10][2];
	for(int i=0;i<10;i++)
	{
		score[i][0]=i;
		score[i][1]=i*10;
	}
	*/
	cout << "開始輸入分數：" << endl;
	int score[10][2];
	int scoretmp,itmp;
	for(int i=0;i<10;i++)
	{
		score[i][0]=i;
		cout << name[i] << endl;
		cin >> score[i][1];
	}
	
	for(int m=1;m<10;m++)
		for(int n=9;n>=m;n--)
		{
			if(score[n][1]<score[n-1][1])
			{
				scoretmp=score[n-1][1];
				itmp=score[n-1][0];
				score[n-1][1]=score[n][1];
				score[n-1][0]=score[n][0];
				score[n][1]=scoretmp;
				score[n][0]=itmp;
			}
		}
	for(int j=0;j<10;j++)
	{
		cout << name[score[j][0]] ;
		cout << score[j][1] << endl;
	}
}

```

 
#

```
#include<iostream>
using namespace std;

int main()
{
	int i;
	cin >> i;
	char buf[7][10];
//{"Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"};
	strcpy(buf[0],"Sunday\0");
	strcpy(buf[1],"Monday\0");
	strcpy(buf[2],"Tuesday\0");
	strcpy(buf[3],"Wednesday\0");
	strcpy(buf[4],"Thursday\0");
	strcpy(buf[5],"Friday\0");
	strcpy(buf[6],"Saturday\0");
	if(i>7 || i<0)
	{
		cout << "Input Error" << endl;
		return 0;
	}
	else
		cout << buf[i] << endl;
	return 1;
}

```

 
#

```
#include<iostream>
using namespace std;

int main()
{
	int buf[3][4]={1,3,5,7,9,11,13,15,17,19,21,23};
	int *p;
	p=buf[0];
	for(int i=0;i<sizeof(buf)/sizeof(int);i++,p++)
		cout << *p << endl;
	return 1;
}

```

 
