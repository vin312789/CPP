#

```
#include <iostream>
using namespace std;
void main()
{
	struct PersonInfo
	{
		int index;
		char name[30];
		short age; 
	} pInfo;
	pInfo.index=0;
	strcpy(pInfo.name,"桲");
	pInfo.age=20;
	cout << pInfo.index << endl;
	cout << pInfo.name << endl;
	cout << pInfo.age << endl;
}
```

 
#

```
#include <iostream>
using namespace std;
void main()
{
	struct PERSONINFO
	{
		int index;
		char name[30];
		short age; 
	}*pPersonInfo, pInfo={0,"桲",20};
	pPersonInfo=&pInfo;
	cout << pPersonInfo->index << endl;
	cout << pPersonInfo->name << endl;
	cout << pPersonInfo->age << endl;
}
```

 
#

```
#include <iostream>
using namespace std;
void main()
{
	struct PersonInfo
	{
		int index;
		char name[30];
		short age;
		struct WorkPlace
		{
			char Address[150];
			char PostCode[30];
			char GateCode[50];
			char Street[100];
			char Area[50];
		}WP;
};

	PersonInfo pInfo;
	strcpy(pInfo.WP.Address,"House");
	strcpy(pInfo.WP.PostCode,"10000");
	strcpy(pInfo.WP.GateCode,"302");
	strcpy(pInfo.WP.Street,"Lan Tian");
	strcpy(pInfo.WP.Area,"china");

	cout << pInfo.WP.Address << endl;
	cout << pInfo.WP.PostCode << endl;
	cout << pInfo.WP.GateCode<< endl;
	cout << pInfo.WP.Street << endl;
	cout << pInfo.WP.Area << endl;
}
```

 
#

```
#include <iostream>
using namespace std;
struct PersonInfo  //定義結構體
{
	int index;
	char name[30];
	short age;
};
void ShowStuctMessage(struct PersonInfo MyInfo) //自訂函數，輸出結構體變數成員
{
	cout << MyInfo.index << endl;
	cout << MyInfo.name << endl;
	cout << MyInfo.age<< endl;

}
void main()
{
	
	PersonInfo pInfo; //聲明結構體
	pInfo.index=1;
	strcpy(pInfo.name,"張三");
	pInfo.age=20;
	ShowStuctMessage(pInfo); //調用自訂函數
}
```

 
#

```
#include <iostream>
using namespace std;
struct PersonInfo
{
	int index;
	char name[30];
	short age;
};
void ShowStuctMessage(struct PersonInfo *pInfo)
{
	cout << pInfo->index << endl;
	cout << pInfo->name << endl;
	cout << pInfo->age<< endl;

}
void main()
{
	
	PersonInfo pInfo;
	pInfo.index=1;
	strcpy(pInfo.name,"桲");
	pInfo.age=20;
	ShowStuctMessage(&pInfo);
}
```

 
#

```
#include <iostream>
using namespace std;
void main()
{
	struct PersonInfo
	{
		int index;
		char name[30];
		short age;
	}Person[5]={{1,"張三",20},
				{2,"李可哥",21},
				{3,"宋橋",22},
				{4,"元員",22},
				{5,"王冰冰",22}};

	struct PersonInfo *pPersonInfo;
	pPersonInfo=Person;
	for(int i=0;i<5;i++,pPersonInfo++)
	{
		cout << pPersonInfo->index << endl;
		cout << pPersonInfo->name << endl;
		cout << pPersonInfo->age << endl;
	}
}
```

 
#

```
#include<iostream>
using namespace std;
union myUnion
{
	int iData;
	char chData;
	float fData;
}uStruct;
int main()
{
	uStruct.chData='A';
	uStruct.fData=0.3;
	uStruct.iData=100;
	cout << uStruct.chData << endl;
	cout << uStruct.fData << endl;
	cout << uStruct.iData << endl; //正確顯示
	uStruct.iData=100;
	uStruct.fData=0.3;
	uStruct.chData='A';
	cout << uStruct.chData << endl; //正確顯示
	cout << uStruct.fData << endl;
	cout << uStruct.iData << endl;
	uStruct.iData=100;
	uStruct.chData='A';
	uStruct.fData=0.3;
	cout << uStruct.chData << endl;
	cout << uStruct.fData << endl;//正確顯示
	cout << uStruct.iData << endl;
	return 0;
}
```

 
#
```
#include <iostream>
using namespace std;
void main()
{
	enum Weekday {Sunday,Monday,Tuesday,Wednesday,Thresday,Friday,Saturday};
	int a=2,b=1;
	Weekday day;
	day=(Weekday)a;
		cout << day << endl;
	day=(Weekday)(a-b);
		cout << day << endl;
	day=(Weekday)(Sunday+Wednesday);
		cout << day << endl;
	day=(Weekday)5;
	cout << day << endl;
}
```
#
```
#include <iostream>
using namespace std;
enum Weekday {Sunday,Monday,Tuesday,Wednesday,Thresday,Friday,Saturday};
void main()
{
	Weekday day1,day2;
	day1=Monday;
	day2=Saturday;
	int n;
	n=day1;
	n=day2+1;
	if(n>day1)//褫眕掀誕
		cout << "n>day1" <<endl;
	if(day1<day2)
		cout << "day1<day2" <<endl;
}
```
#
```
#include <iostream>
using namespace std;
void main()
{
	enum  weekday{Sunday=2,Monday=3,Tuesday=4,Wednesday=5,Thursday=0,Friday=1,Saturday=6};

	weekday m_eType1;
	weekday m_eType2;
	m_eType1=Sunday;//Sunday=2
	m_eType2=Friday;//Friday=1
	cout << m_eType1-m_eType2 << endl;
}
```

#

```
typedef char * CString;
#include <iostream.h>
void main()
{
	CString str;
	char temp[]="Hello World";
	str=temp;
	cout << str << endl;
}
```

 
#
```
#include<iostream>
using namespace std;
int main()
{
	struct StudentScore
	{
		char name[128];
		int MidScore;
		int FinalScore;
		int DailyScore;
	};
	
	StudentScore std[10];
	
	int iCount;
	cout << "輸入學生數量" << endl;
	cin >> iCount;
	if(iCount>=10)
	{
		cout << "Over Max" << endl;
		return 0;
	}
	for(int i=0;i<iCount;i++)
	{
		cout << i <<"輸入學生姓名" << endl;
		cin >> std[i].name;
		cout << "輸入期中成績" << endl;
		cin >> std[i].MidScore;
		cout << "輸入期末成績" << endl;
		cin >> std[i].FinalScore;
		cout << "輸入平時成績" << endl;
		cin >> std[i].DailyScore;
	}
	for(int j=0;j<iCount;j++)
	{
		cout << std[j].name << ":";
		cout << "綜合成績：" << (std[j].MidScore*0.3+std[j].FinalScore*0.5+ std[j].DailyScore*0.2)/3 << " ";
	}
	return 1;
}

```

 
#

```
#include<iostream>
using namespace std;
struct Person
{
	char name[128];
	int iVote;
};
int main()
{
	Person p[3];
	for(int k=0;k<3;k++)
	{
		p[k].iVote=0;
	}
	int iCount;
	int iInput;
	cout << "輸入參選人數量:" << endl;
	cin >> iCount ;
	for(int j=0;j<3;j++)
	{
		cout << "輸入第"<<j+1<<"個候選人姓名:" << endl;
		cin >> p[j].name;
	}
	//候選人輸入模組
	for(int i=0;i<iCount;i++)
	{
		for(int n=0;n<3;n++)
			cout << "選" << p[n].name<< "按" << n<< endl;
		cin >> iInput;
		if(iInput>2)
		{
			cout << "Err" << endl;
			return 0;
		}
		else
			p[iInput].iVote++;
	}
	//統計模組
	for(int m=0;m<3;m++)
	{
		cout << p[m].name << "選票數為:" << p[m].iVote << endl;
	}
	return 1;
}

```

 
