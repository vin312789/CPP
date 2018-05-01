#

```
#include <iostream>
using namespace std;
class CEmployee							//定義員工類
{
public:
	int m_ID;								//定義員工ID
	char m_Name[128];						//定義員工姓名
	char m_Depart[128];						//定義所屬部門
	CEmployee()							//定義預設構造函數
	{
		memset(m_Name,0,128);				//初始化m_Name
		memset(m_Depart,0,128);			//初始化m_Depart
	}
void OutputName()							//定義共有成員函數
{
	cout <<"員工姓名"<<m_Name<<endl;		//輸出員工姓名
}
};
class COperator :public CEmployee				//定義一個操作員類，從CEmployee類派生而來
{
public:
	char m_Password[128];					//定義密碼
	bool Login()							//定義登錄成員函數
	{
		if (strcmp(m_Name,"MR")==0 &&		//比較用戶名
 			strcmp(m_Password,"KJ")==0)		//比較密碼
		{
		cout<<"登錄成功!"<<endl;			//輸出資訊
			return true;					//設置返回值
		}
		else
		{
			cout<<"登錄失敗!"<<endl;			//輸出資訊
			return false;					//設置返回值
		}
	}
};
int main(int argc, char* argv[])
{
	COperator optr;							//定義一個COperator類物件
	strcpy(optr.m_Name,"MR");				//訪問基類的m_Name成員
	strcpy(optr.m_Password,"KJ");				//訪問m_Password成員
	optr.Login();							//調用COperator類的Login成員函數
	optr.OutputName();						//調用基類CEmployee的OutputName成員函數
	return 0;
}
```

 
#
```
#include <iostream>
using namespace std;
class CEmployee								//定義CEmployee類
{
public:
	int m_ID;									//定義資料成員
	char m_Name[128];							//定義資料成員
	char m_Depart[128];							//定義資料成員
	CEmployee()								//定義構造函數
	{
		cout << "CEmployee類構造函數被調用"<< endl;		//輸出資訊
	}
	~CEmployee()								//析構函數
	{
		cout << "CEmployee類析構函數被調用"<< endl;		//輸出資訊
	}
};
class COperator :public CEmployee					//從CEmployee類派生一個子類
{
public:
	char m_Password[128];						//定義資料成員
	COperator()								//定義構造函數
	{
		strcpy(m_Name,"MR");					//設置數據成員
		cout << "COperator類構造函數被調用"<< endl;		//輸出資訊
	}
	~COperator()								//析構函數
	{
		cout << "COperator類析構函數被調用"<< endl;		//輸出資訊
	}
};
int main(int argc, char* argv[])						//主函數
{
	COperator optr;								//定義一個COperator物件
	return 0;
}
```

#

```
#include <iostream>
using namespace std;
class CEmployee								//定義CEmployee類
{
public:
	int m_ID;									//定義資料成員
	char m_Name[128];						//定義資料成員
	char m_Depart[128];						//定義資料成員
	CEmployee()								//定義構造函數
	{
		cout << "CEmployee類構造函數被調用"<< endl;		//輸出資訊
	}
	~CEmployee()								//析構函數
	{
		cout << "CEmployee類析構函數被調用"<< endl;		//輸出資訊
	}
};
class COperator :public CEmployee			//定義COperator類
{
public:
	char m_Password[128];			//定義資料成員
	void OutputName()					//定義OutputName成員函數
	{
		cout << "操作員姓名: "<< m_Name<< endl;	//輸出操作員姓名
	}
	bool Login()						//添加成員函數
	{
		if (strcmp(m_Name,"MR")==0 &&	//比較用戶名
			strcmp(m_Password,"KJ")==0)	//比較密碼
		{
			cout << "登錄成功"<< endl;			//輸出資訊
			return true;				//返回結果
		}
		else
		{
			cout << "登錄失敗"<< endl;			//輸出資訊
			return false;				//返回結果
		}
	}
};
int main(int argc, char* argv[])				//主成員函數
{
	COperator optr;						//定義COperator物件
	strcpy(optr.m_Name,"MR");			//設置m_Name數據成員
	optr.OutputName();					//調用COperator類的OutputName成員函數
	return 0;
}
```

 
#

```
#include <iostream>
using namespace std;
class CBook
{
public:
	CBook (int iPage)
	{
		m_iPage=iPage;
	}
	CBook operator+( CBook b)
	{
		return CBook (m_iPage+b.m_iPage);
	}
	void display()
	{
		cout << m_iPage << endl;
	}
protected:
	int m_iPage;
};

void main()
{
	CBook bk1(10);
	CBook bk2(20);
	CBook tmp(0);
	tmp= bk1+bk2;
	tmp.display();
}
```

 
#

```
#include <iostream>
using namespace std;
class CBook
{
public:
	CBook (double iPage=0);
	operator double()
	{
		return m_iPage;
	}

protected:
	int m_iPage;
};
CBook:: CBook (double iPage)
{
	m_iPage=iPage;
}
void main()
{
	CBook bk1(10.0);
	CBook bk2(20.00);
	cout << "bk1+bk2=" << double(bk1)+double(bk2) << endl;
}
```

 
#

```
#include <iostream>
using namespace std;
class CBicycle
{
public:
	CBicycle()
	{
		cout << "Bicycle Construct" << endl;
	}
	CBicycle(int iWeight)
	{
		m_iWeight=iWeight;
	}
	void Run()
	{
		cout << "Bicycle Run" << endl;
	}

protected:
	int m_iWeight;
};

class CAirplane
{
public:
	CAirplane()
	{
		cout << "Airplane Construct " << endl;
	};
	CAirplane(int iWeight)
	{
		m_iWeight=iWeight;
	}
	void Fly()
	{
		cout << "Airplane Fly " << endl;
	}

protected:
	int m_iWeight;
};

class CAirBicycle : public CBicycle, public CAirplane
{
public:
	CAirBicycle()
	{
		cout << "CAirBicycle Construct" << endl;
	}
	void RunFly()
	{
		cout << "Run and Fly" << endl;
	}
};
void main()
{
	CAirBicycle ab;
	ab.RunFly();
}
```

 
#

```
#include <iostream>
using namespace std;
class CEmployee								//定義CEmployee類
{
public:
	int m_ID;									//定義資料成員
	char m_Name[128];							//定義資料成員
	char m_Depart[128];							//定義資料成員
	CEmployee()								//定義構造函數
	{
		memset(m_Name,0,128);					//初始化資料成員
		memset(m_Depart,0,128);				//初始化資料成員
	}
	virtual void OutputName()						//定義一個虛成員函數
	{
		cout << "員工姓名: "<<m_Name << endl;			//輸出資訊
	}
};
class COperator :public CEmployee					//從CEmployee類派生一個子類
{
public:
	char m_Password[128];						//定義資料成員
	void OutputName()							//定義OutputName虛函數
	{
		cout << "操作員姓名: "<<m_Name<< endl;			//輸出資訊
	}
};
int main(int argc, char* argv[])
{
	CEmployee *pWorker = new COperator();	//定義CEmployee類型指標，調用COperator類構造函數
	strcpy(pWorker->m_Name,"MR");		//設置m_Name資料成員資訊
	pWorker->OutputName();				//調用COperator類的OutputName成員函數
	delete pWorker;					//釋放對象
	return 0;
}
```

#

```
#include <iostream>
using namespace std;
class CAnimal								//定義一個動物類
{
public:
CAnimal()								//定義構造函數
{
	cout << "動物類被構造"<< endl;				//輸出資訊
}
	void Move()							//定義成員函數
	{
		cout << "動物能夠移動"<< endl;				//輸出資訊
	}
};
class CBird : virtual public CAnimal			//從CAnimal類虛繼承CBird類
{
public:
	CBird()								//定義構造函數
{
	cout << "鳥類被構造"<< endl;				//輸出資訊
}
void FlyInSky()							//定義成員函數
	{
		cout << "鳥能夠在天空飛翔"<< endl;			//輸出資訊
	}
	void Breath()							//定義成員函數
	{
		cout << "鳥能夠呼吸"<< endl;				//輸出資訊
	}
};
class CFish: virtual public CAnimal			//從CAnimal類虛繼承CFish
{
public:
	CFish()								//定義構造函數
	{
		cout << "魚類被構造"<< endl;				//輸出資訊
	}
	void SwimInWater()						//定義成員函數
	{
		cout << "魚能夠在水裡遊"<< endl;			//輸出資訊
	}
	void Breath()							//定義成員函數
	{
		cout << "魚能夠呼吸"<< endl;				//輸出資訊
	}
};
class CWaterBird: public CBird, public CFish		//從CBird和CFish類派生子類CWaterBird
{
public:
	CWaterBird()							//定義構造函數
	{
		cout << "水鳥類被構造"<< endl;				//輸出資訊
	}
void Action()							//定義成員函數
	{
		cout << "水鳥即能飛又能遊"<< endl;			//輸出資訊
	}
};
int main(int argc, char* argv[])						//主函數
{
	CWaterBird waterbird;						//定義水鳥物件
	return 0;
}
```

 
#

```
#include <iostream>
using namespace std;
class CFigure
{
public:
	virtual double getArea() =0;
};
const double PI=3.14;
class CCircle : public CFigure
{
private:
	double m_dRadius;
public:
	CCircle(double dR){m_dRadius=dR;}
	double getArea()
	{
		return m_dRadius*m_dRadius*PI;
	}
};
class CRectangle : public CFigure
{
protected:
	double m_dHeight,m_dWidth;
public:
	CRectangle(double dHeight,double dWidth)
	{
		m_dHeight=dHeight;
		m_dWidth=dWidth;
	}
	double getArea()
	{
		return m_dHeight*m_dWidth;
	}
};
void main()
{
	CFigure *fg1;
	fg1= new CRectangle(4.0,5.0);
	cout << fg1->getArea() << endl;
	delete fg1;
	CFigure *fg2;
	fg2= new CCircle(4.0);
	cout << fg2->getArea() << endl;
	delete fg2;
}
```

 
#

```
#include <iostream>
using namespace std;

class CEmployee						//定義CEmployee類
{
public:
	int m_ID;							//定義資料成員
	char m_Name[128];					//定義資料成員
	char m_Depart[128];					//定義資料成員
	virtual void OutputName() = 0;			//定義抽象成員函數
};

class COperator :public CEmployee				//定義COperator類，派生於CEmployee類
{
public:
	char m_Password[128];				//定義資料成員
	void OutputName()						//實現父類中的純虛成員函數
	{
		cout << "操作員姓名: "<<m_Name<< endl;		//輸出資訊
	}
	COperator()							//定義COperator類的預設構造函數
	{
		strcpy(m_Name,"MR");				//設置資料成員m_Name資訊
	}
};
class CSystemManager :public CEmployee		//定義CSystemManager類
{
public:
	char m_Password[128];				//定義資料成員
	void OutputName()						//實現父類中的純虛成員函數
	{
		cout << "系統管理員姓名: "<<m_Name<< endl;	//輸出資訊
	}
	CSystemManager()						//定義CSystemManager類的預設構造函數
	{
		strcpy(m_Name,"SK");				//設置資料成員m_Name資訊
	}
};
int main(int argc, char* argv[])					//主函數
{
	CEmployee *pWorker;					//定義CEmployee類型指標物件
	pWorker = new COperator();				//調用COperator類的構造函數為pWorker賦值
	pWorker->OutputName();				//調用COperator類的OutputName成員函數
	delete pWorker;						//釋放pWorker對象
	pWorker = NULL;						//將pWorker對象設置為空
	pWorker = new CSystemManager();			//調用CSystemManager類的構造函數與為pWorker賦值
	pWorker->OutputName();				//調用CSystemManager類的OutputName成員函數
	delete pWorker;						//釋放pWorker對象
	pWorker = NULL;						//將pWorker對象設置為空
	return 0;
}
```

 
#

```
#include<iostream>
using namespace std;
class CSale
{
public :
	CSale();
	CSale(char *cName,int iPrice)
	{
		strncpy(m_cName,cName,128);
		m_iPrice=iPrice;
	}
	friend ostream& operator<<(ostream& os,const CSale s)
	{
		cout << "Name: " << s.m_cName << ' ' ;
		cout << "Price: " << s.m_iPrice<< ' ';
		return os;
		
	}

protected:
	char m_cName[128];
	int m_iPrice;
};
int main()
{
	CSale sale("apple",900);
	cout << sale << endl;
	return 0;
}

```

 
#

```
#include <iostream>
using namespace std;
class Teacher
{
public:
	Teacher(int i)
	{
		iZhiWu=i;
	}
protected:
	int iZhiWu;
};
class Level
{
public:
	Level(int j)
	{
		iZhiCheng=j;
	}
protected:
	int iZhiCheng;
};

class Teacher_Level : public Teacher,Level
{
public:
	Teacher_Level(int a,int b,int c):Teacher(a),Level(b)
	{
		iGongZi=c;
	}
	Show()
	{
		cout << "職務:" << iZhiWu << endl;
		cout << "職稱:" << iZhiCheng << endl;
		cout << "工資:" << iGongZi << endl;
	}
protected:
	int iGongZi;
};
void main()
{
	Teacher_Level myObj(20,30,40);
	myObj.Show();
}
```
 
