#

```
#include <iostream.h>
#include "Person.h"
void main()
{
	int iResult=-1;
	CPerson p;
	iResult=p.setAge(25); 
	if(iResult>=0)
		cout << "m_shAge is:" << p.getAge() << endl;

	iResult=p.setIndex(0); 
	if(iResult>=0)
		cout << "m_iIndex is:" << p.getIndex() << endl;

	char bufTemp[]="Mary";
	iResult=p.setName(bufTemp); 
	if(iResult>=0)
		cout << "m_cName is:" << p.getName() << endl;

	iResult=p.setSalary(1700.25); 
	if(iResult>=0)
		cout << "m_dSalary is:" << p.getSalary() << endl;
}
```

#

```
#include "Person.h"
#include <stdlib.h>
#include <string.h>

short CPerson::getAge() 
{ 
	return m_shAge; 
}
int CPerson::setAge(short sAge)
{
	m_shAge=sAge;
	return 0;								//執行成功返回0
}
int CPerson::getIndex() 
{ 
	return m_iIndex; 
}
int CPerson::setIndex(int iIndex)
{
	m_iIndex=iIndex;
	return 0;//執行成功返回0
}
char* CPerson::getName() 
{ 
	return m_cName; 
}
int CPerson::setName(char cName[25])
{
	strcpy(m_cName,cName);
	return 0;//執行成功返回0
}
double CPerson::getSalary() 
{ 
	return m_dSalary; 
}
int CPerson::setSalary(double dSalary)
{
	m_dSalary=dSalary;
	return 0;//執行成功返回0
}
```

 
#

```
#include <iostream>
using namespace std;
//定義CPerson類
class CPerson
{
	public:
		CPerson();
	CPerson(int iIndex,short m_shAge,double m_dSalary);
	int m_iIndex;
	short m_shAge;
	double m_dSalary;
	int getIndex();
	short getAge();
	double getSalary();
};
//在預設構造函數中初始化
CPerson::CPerson()
{
	m_iIndex=0;
	m_shAge=10;
	m_dSalary=1000;
}
//在帶參數的構造函數中初始化
CPerson::CPerson(int iIndex,short m_shAge,double m_dSalary)
{
	m_iIndex=iIndex;
	m_shAge=m_shAge;
	m_dSalary=m_dSalary;
}
int CPerson::getIndex() 
{ 
	return m_iIndex; 
}
//在main函數中輸出類的成員值
void main()
{
	CPerson p1;
	cout << "m_iIndex is:" << p1.getIndex() << endl;

	CPerson p2(1,20,1000);
	cout << "m_iIndex is:" << p2.getIndex() << endl;
}
```

 
#
```
#include <iostream>
#include "Person.h"
using namespace std;
void main()
{
	CPerson p1(20,30,100);
	CPerson p2(p1);
	cout << "m_iIndex of p1 is:" << p2.getIndex() << endl;
	cout << "m_shAge of p1 is:" << p2.getAge() << endl;
	cout << "m_dSalary of p1 is:" << p2.getSalary() << endl;
	cout << "m_iIndex of p2 is:" << p2.getIndex() << endl;
	cout << "m_shAge of p2 is:" << p2.getAge() << endl;
	cout << "m_dSalary of p2 is:" << p2.getSalary() << endl;
}
```

#

```
#include "Person.h"
#include <stdlib.h>
#include <string.h>

short CPerson::getAge() 
{ 
	return m_shAge; 
}
int CPerson::setAge(short sAge)
{
	m_shAge=sAge;
	return 0;								//執行成功返回0
}
int CPerson::getIndex() 
{ 
	return m_iIndex; 
}
int CPerson::setIndex(int iIndex)
{
	m_iIndex=iIndex;
	return 0;//執行成功返回0
}
char* CPerson::getName() 
{ 
	return m_cName; 
}
int CPerson::setName(char cName[25])
{
	strcpy(m_cName,cName);
	return 0;//執行成功返回0
}
double CPerson::getSalary() 
{ 
	return m_dSalary; 
}
int CPerson::setSalary(double dSalary)
{
	m_dSalary=dSalary;
	return 0;//執行成功返回0
}
```

 
#

```
#include <iostream>
using namespace std;
#include "Person.h"
void main()
{
	CPerson p;
	p.ShowFrameMessage();
	p.ShowStartMessage();
	p.ShowFrameMessage();
}
```

#

```
#include "Person.h"
#include <stdlib.h>
#include <string.h>

short CPerson::getAge() 
{ 
	return m_shAge; 
}
int CPerson::setAge(short sAge)
{
	m_shAge=sAge;
	return 0;								//執行成功返回0
}
int CPerson::getIndex() 
{ 
	return m_iIndex; 
}
int CPerson::setIndex(int iIndex)
{
	m_iIndex=iIndex;
	return 0;//執行成功返回0
}
char* CPerson::getName() 
{ 
	return m_cName; 
}
int CPerson::setName(char cName[25])
{
	strcpy(m_cName,cName);
	return 0;//執行成功返回0
}
double CPerson::getSalary() 
{ 
	return m_dSalary; 
}
int CPerson::setSalary(double dSalary)
{
	m_dSalary=dSalary;
	return 0;//執行成功返回0
}
```

 
#

```
#include <iostream>
class CItem;								//前導聲明CItem類
class CList								//定義CList類
{
private:
	CItem * m_pItem;						//定義私有資料成員m_pItem
public:
	CList();								//定義預設構造函數
	~CList();								//定義析構函數
	void OutputItem();						//定義OutputItem成員函數
};
class CItem								//定義CItem類
{
friend void CList::OutputItem();				//聲明友元函數
private:
	char m_Name[128];						//定義私有資料成員
	void OutputName()						//定義私有成員函數
	{
		printf("%s\n",m_Name);				//輸出資料成員資訊
	}
public:
	void SetItemName(const char* pchData)		//定義共有方法
	{
		if (pchData != NULL)					//判斷指針是否為空
		{
			strcpy(m_Name,pchData);		//賦值字串
		}
	}
	CItem()								//構造函數
	{
		memset(m_Name,0,128);				//初始化資料成員m_Name
	}
};
void CList::OutputItem()						//CList類的OutputItem成員函數的實現
{
	m_pItem->SetItemName("BeiJing");			//調用CItem類的共有方法
	m_pItem->OutputName();				//在友元函數中訪問CItem類的私有方法OutputName
}
CList::CList()								//CList類的預設構造函數
{
	m_pItem = new CItem();					//構造m_pItem物件
}
CList::~CList()								//CList類的析構函數
{
	delete m_pItem;						//釋放m_pItem對象
	m_pItem = NULL;						//將m_pItem對象設置為空
}
int main(int argc, char* argv[])					//主函數
{
	CList list;								//定義CList物件list
	list.OutputItem();						//調用CList的OutputItem方法
	return 0;
}
```

 
#

```
#include<iostream>
using namespace std;

namespace MyName1						//定義命名空間
{
	int iValue=10;
};

namespace MyName2						//定義命名空間
{
	int iValue=20;
};

int iValue=30;								//全域變數

int main()
{
	cout<<MyName1::iValue<<endl;			//引用MyName1命名空間中的變數
	cout<<MyName2::iValue<<endl;			//引用MyName2命名空間中的變數
	cout<<iValue<<endl;
	return 0;
}
```

 
# Detach.cpp

```
#include<iostream>

namespace MyName						//定義命名空間
{
	int iValue=10;							//定義整型變數
}

using namespace std;						//使用命名空間std
using namespace MyName;					//使用命名空間MyName

int main()
{
	cout<<iValue<<endl;						//輸出命名空間中的變數
	return 0;
}
```

#

```
#include<iostream>
#include"Detach.h"
using namespace std;

void Output::Demo()							
{
	cout<<"This is a  function!\n";
}
```

# main.cpp

```
#include "Detach.h"
int main()
{
	Output::Demo();						
	return 0;
}
```

# Detach.h

```
namespace Output		
{
	void Demo();							
}
```

 
#

```
#include<iostream>
using namespace std;

namespace Output							//定義命名空間
{
	void Show()							//定義函數
	{
		cout<<"Output's function!"<<endl;
	}
	namespace MyName					//定義嵌套命名空間
	{
		void Demo()						//定義函數
		{
			cout<<"MyName's function!"<<endl;
		}
	}
}

int main()
{
	Output::Show();						//調用Output命名空間中的函數
	Output::MyName::Demo();				//調用MyName命名空間中的函數
	return 0;
}
```

 
#

```
#include<iostream>
using namespace std;
#define PI 3.14
class CCylinder
{
public :
	CCylinder()
	{
		m_iRadius=0;
		m_iHeight=0;
	}
	CCylinder(int iRadius,int iHeight)
	{
		m_iRadius=iRadius;
		m_iHeight=iHeight;
	}
	int getArea()
	{
		return PI*m_iRadius*m_iRadius*m_iHeight;
	}
	void setRadius(int iRadius)
	{
		m_iRadius=iRadius;
	}
	void setHeight(int iHeight)
	{
		m_iHeight=iHeight;
	}
	int getRadius()
	{
		return m_iRadius;
	}
	int getHeight()
	{
		return m_iHeight;
	}
protected:
	int m_iRadius;
	int m_iHeight;
};
int main()
{
	CCylinder cld;
	int i,j;
	cout << "輸入圓柱的半徑" << endl;
		cin >> i;
		cld.setRadius(i); //設置圓柱的半徑
	cout << "輸入圓柱的高度" << endl;
		cin >> j;
		cld.setHeight(j); //設置圓柱的高
	cout << "圓柱的半徑為：" << cld.getRadius()<<endl;
	cout << "圓柱的高度為：" << cld.getHeight()<< endl;
	cout << "圓柱的體積為：" << cld.getArea()<< endl;
	return 1;
}

```

 
#

```
#include<iostream>
using namespace std;
class Student
{
public:
void SetInfor(char* cName,short sSex,int iGrade,int iClass)
{
	strcpy(m_cName,cName);
	if(sSex!=1)
		m_sSex=0;
	else
		m_sSex=1;
	m_iGrade=iGrade;
	m_iClass=iClass;
}
void ShowInfor()
{
	cout << "姓名:" <<m_cName << endl;
	if(m_sSex==1)
		cout << "性別:男" << endl;
	else
		cout << "性別:女" << endl;
	cout << "年級:" << m_iGrade << endl;
	cout << "班級:" << m_iClass << endl;
}
protected:
	char m_cName[128];
	short m_sSex;//1代表男孩，0代表女孩
	int m_iGrade;
	int m_iClass;
	
};

int main()
{
	Student st;
	char cName[128];
	int iGrade=0;
	int iClass=0;
	short sSex=0;
	cout << "輸入姓名" << endl;
	cin >> cName;
	cout << "輸入性別，1代表男孩，0代表女孩" << endl;
	cin >> sSex;
	cout << "輸入年級" << endl;
	cin >> iGrade;
	cout << "輸入班級" << endl;
	cin >> iClass;
	st.SetInfor(cName,sSex,iGrade,iClass);
	st.ShowInfor();
	
	
}

```
