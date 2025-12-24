# 第一章节

```
//包含头文件
#include <iostream>
//main函数,程序从这里开始执行
int main()
{
    std::cout << "Hello World!\n";
    //std::cout     向控制台输出内容的指令
    //<<            输出的运算符
    //""            字符串内容的边界符
    //Hello world   输出字符串的内容
    //\n            输出一个换行
    //;             C++语句结束的标志
}
```

### 1)  数据的分类:

### 数字:100,23,45...

### 字符:用半角的单引号包含,如:'A'.'a'.'9'(数字用单引号包含就变成字符)

### 字符串:"hello world"

### 2)  输出数据:

### 1.std::cout	可以输出各种类型数据

### 2.操作符可以拼接多个数据项

### 3.std::endl	也可用于换行

### 4.using namespace std;	指定缺省的命名空间,即std::可以不用写了

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了

//main函数,程序从这里开始执行
int main()
{
    std::cout << "Hello World!\n";
    //std::cout     向控制台输出内容的指令
    //<<            输出的运算符
    //""            字符串内容的边界符
    //Hello world   输出字符串的内容
    //\n            输出一个换行
    //;             C++语句结束的标志
    cout << "姓名:" << "小石头" << ";年龄:" << "25" << "\n";
    cout << "姓名:" << "小石头" << ";年龄:" << "25" << std::endl; //std:endl相当于换行,与\n作用一致
}
```

### 3)  注释的注释

单行注释可以注释多行注释,多行注释也可以注释单行注释,但是不建议用

### 4) VS中的快捷键

添加注释:Ctrl+k+c

取消注释:Ctrl+k+u

### 5)  变量

变量是内存变量的简称,在使用变量之前要事先声明

### 声明变量:  数据类型  变量名;

C++常用的数据类型有五种:整型(int),浮点数(float和double),字符(char),字符串(string)和布尔(bool)

变量在声明的时候可以赋予初始值

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	string name;		//姓名
	int age;			//年龄
	double weight;		//体重
	char sex;			//性别
	bool yz;			//颜值,true漂亮,false不漂亮

	name = "小石头";
	age = 23;
	weight = 34;
	sex = 'X';
	yz = true;

	cout << "姓名:" << name << ";年龄:" << age << ";体重:" << weight << ";颜值:" << yz << endl;
}
```



### 使用常量:常量是程序中固定不变的量

### 6)  宏常量:一般在main函数上面声明,用大写命名

语法格式:# define 常量名 值

### const修饰的变量:

语法格式:const 数据类型 变量名=值;

### 常量特点:程序中不允许改变常量的值,否则报错

```
//包含头文件
#include <iostream>
#define MONTHS 12		//一年中的月份数
#define PI	3.14		//圆周率
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	const int days = 7;		//const常量定义
	cout << "一年有:" << MONTHS << "个月" << endl;
	cout << "圆周率是:" << PI << endl;
	cout << "一周有:" << days <<"天" << endl;
}
```



### 7)  标识符的命名:

C++规定标识符(常量,变量,函数,结构体,类等)命名时,必须遵守以下规则:

1. 名称中只能使用字母字符,数字和下划线;

2. 名称的第一个字符不能是数字;
3. 区分大写字符和小写字符;
4. 不能将C++关键字用作名称;
5. 以下划线和大写字母打头的名称被保留给编译器及其使用的资源使用,如果违反这一规则会导致行为的不确定性
6. C++对名称的长度无限制,某些平台对长度有限制

### 8)  关键字:

例如:bool,int,using,char,const,false,float,true,double,namespace等等





# 第二章节

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	string name;	//姓名
	cout << "请输入姓名:";
	cin >> name;
	cout << "输入的姓名是:"<<name<<endl;
	int age;	//年龄
	cout << "请输入年龄:";
	cin >> age;
	cout << "输入的年龄是:" << age << endl;
	double weight;	//体重
	cout << "请输入体重:";
	cin >> weight;
	cout << "输入的体重是:" << weight << endl;
	char sex;	//性别
	cout << "请输入性别:";
	cin >> sex;
	cout << "输入的性别是:" << sex << endl;
}
```

### 1)  输入数据:

语法格式:std::cin>>变量名

注意:

1. 布尔型变量的值在计算机内部用1(true)和0(false)存储,程序中可以书写true和false,也可以书写1和0,其他值将强转成1;cin输入时可以填1或0,其他值强转成1;cout输出时只显示1或0,不显示true和false
2. 如果输入的数据与变量的数据类型不匹配,会导致行为的不确定性(会输出莫名其妙的结果)

### 2)  算术运算:

算术运算有:+-*/%

注意事项:

1. 除法运算分母不能为0,否则程序异常退出
2. 浮点数进行除法运算时,分母若为0.0,则得到inf(无穷大)
3. 两个整数除法运算,会舍去小数部分,得到一个整数
4. 整数与浮点数进行除法运算,得到的结果是浮点数
5. 在整数前面加(float)或(double)可以将整数转换为float或者double类型
6. 取模运算只能用于整数(分母不可以为0)

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	int a=8;
	int b = 5;
	cout << (double)a / b << endl;
}
```

### 3)  自增和自减

运算格式:

++变量名:先自增在使用其值

变量名++:先使用其值,再自增

--变量名:先自减,再使用其值

变量名--:先使用其值,再自减

```c++
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	int i = 10;
	i++;		//先使用其值再自增
	cout << i;
}
```

注意:

1. 字符串只能使用等号=赋值,不可以使用其他的赋值运算符
2. 浮点数不能使用%=运算符
3. 等号赋值运算符可以连续使用
4. 如果赋值运算符两边操作数的数据类型不同,C++会自动转换数据类型,可能会损失精度,也可能会超出取值范围,如果转换不成功,编译时会报错

### 4)  C++初始化赋值

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	int a = 10;
	int b = (10);					//把值写在小括号中
	int c(10);						//把值写在小括号中且等号可以省略
	int d{10};						//把值写在花括号中且等号可以省略
	cout << "a=" << a << endl;
	cout << "b=" << b << endl;
	cout << "c=" << c << endl;		
	cout << "d=" << d << endl;		//这四种的效果都是一样的,值都是10
}
```

### 总结两点:

### 1.值可以写在小括号中,等号可以省略

### 2.值写在花括号中,等号可以省略

### 5)  关系运算:

等于		==

不等于	    !=

小于		<

小于等于	<=

大于		>	

大于等于	>=

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	int a = 10;
	int b = 8;
	bool result;
	result = a == b;	//a和b先做比较运算,然后再赋值给result
	cout << "result=" << result << endl;	//输出结果是0,因为a和b不相等
	cout << "result=" << (a == b) << endl;	//关系运算表达式需要括号,算术运算表达式可以不用括号
	cout << "result=" << a + b << endl;		//算数运算符可以不需要括号,但关系运算符需要括号
}
```

### 总结:所以给他加上括号肯定是没问题的,不管是关系运算符还是算数运算符,都给它加上括号

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	string str1 = "好啦";
	string str2 = "西瓜";
	cout << (str1 != str2) << endl;		//输出1,因为str1不等于str2是正确的,在运算的时候加括号一定没问题
}
```



### 5)  逻辑运算

运算符:

逻辑与:&&

逻辑或:||

逻辑非:!

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	bool a = true;
	bool b = true;
	bool c=a&&b;		//a和b结果都是真,则逻辑与的结果也是真
	bool d = 7 > 5 && b;		
	cout << "d=" << d << endl;		//d输出1,等号两侧也可以是表达式
	cout << "c=" << c << endl;		//c输出1
	cout << "a&&b=" << (a && b) << endl;	//记得加括号,且输出结果是1
}
```



```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	//满足四个条件:年龄25以下;身高165以上;体重50kg以下,颜值要漂亮
	int age = 23;
	int height = 168;
	double weight = 48.9;
	bool yz = true;
	cout << "result=" << (age < 25 &&height>165 && weight < 50 && yz == true) << endl;		//输出1
}
```



### 6)  逗号运算

把一行语句中的多个表达式连接起来,程序将从左到右执行表达式

语法格式:表达式一,表达式二.......表达式n

逗号常用于声明多个变量,也可以用于其他语句中,但是逗号运算符是所有运算符中级别最低的,以下两个表达式的效果是不同的.

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	int a, b,c;
	b = a = 2, a * 2;
	c = (a=2,a*2);
	cout << "b=" << b << endl;
	cout << "c=" << c << endl;//逗号优先级最低,所以b先处理前面,而c先处理括号里面的
}
```



### 7)  运算符的优先级

一个表达式可以包含多个运算符,运算符的优先级决定了表达式各部分的执行顺序

括号的优先级是最高的,如果表达式中操作符优先级相同,则从左到右依次执行,而赋值运算符的结合律是从右到左的

所以说,能加括号的地方就加括号

# 第三章

### 1)  if语句的基本结构

语法:

if(表达式){

​	语句

}else{

​	语句

}

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	bool yz;		//颜值信息
	cout << "请输入颜值:";
	cin >> yz;
	//用if语句判断颜值,若合格则晋级下一轮
	if (yz) {
		cout << "恭喜晋级" << endl;
	}
	else {
		cout << "晋级失败" << endl;
	}
}
```



注意:

1. 表达式必须使用括号
2. 表达式可以是具体的值
3. 表达式一般是关系运算和逻辑运算,也可以是赋值运算或其他的表达式
4. 不要把if(变量名==值)写成if(变量名=值)
5. 可以没有else语句的分支
6. {}中的代码如果只有一行,{}可以不写,如果一行代码也没有,{}必须要写,如果有多行,{}一定要写,如果不写,则除了第一行其他行的代码将不再是if语句的一部分
7. 如果多写了一个分号;那么该分号会被当成一条空语句

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	char sex;		//定义性别
	bool yz;		//定义颜值
	int sc;			//定义身材
	cout << "请输入性别:";
	cin >> sex;
	if (sex == 'X') {
		cout << "输入颜值:";
		cin >> yz;
		if (yz == true) {
			cout << "输入身材:";
			cin >> sc;
			if (sc == 1) {
				cout << "晋级成功" << endl;
			}
			else {
				if (sc == 2) {
					cout << "待定"<<endl;
				}
			}
		}
	}
}
```

### 3)  多条件的if语句

语法:

if(表达式){

​	语句;

}else if(表达式){

​	语句;

}else{

​	语句;

}

### 4)  if语句中的逻辑表达式

```
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	int age = 26;
	int height = 170;
	string sc = "火辣";
	string yz = "漂亮";
	if (age > 25 && age < 30) {
		if (height > 165 && height < 175) {
			if (sc == "火辣") {
				if (yz == "漂亮" || yz == "一般") {
					cout << "晋级成功!\n";
				}
			}
		}
	}
}
```

 ### 5)  三目运算

语法:

表达式一?表达式二:表达式三

先计算表达式一的值,若为真则为表达式二的值,否则为表达式三的值

```
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	int a = 7, b = 5, c = 0;
	//比较ab大小,将较大者赋给c
	c = a > b ? a : b;
	cout << "c=" << c << endl;
}
```

### 6)  switch语句

语法:

switch(表达式){

​	case 值一:

​		语句一;

​		break;

​	case 值二:

​		语句二;

​		break;

​	case 值n:

​		语句n;

​		break;

​	default:

​		上述条件都不满足时执行;

}

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	int sc;
	cout << "输入身材:" << endl;
	cin >> sc;
	switch (sc) {
	case 1:
		cout << "火辣\n";
		break;
	case 2:
		cout << "丰满\n";
		break;
	case 3:
		cout << "强壮\n";
		break;
	default:
		cout << "未知\n";
	}
}
```

注意:

1. case后面必须是整数和字符,或者是结果为整数和字符的表达式,但不能使用变量
2. default不是必须的,当没有default时,如果全部的case匹配失败,那么久什么都不执行
3. 每个分支不要漏写break语句



# 第四章

### 1) while循环结构

语法:

while(表达式){

​	语句块

}

### 2)  循环的跳转

break和continue两个关键字用于控制循环体中代码的执行流程

break:跳出(中止)当前循环语句

continue:回到当前循环语句的首部

### 3)  for循环

语法:

for(语句一;表达式;语句二){

​	语句块;

}

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	int no;
	no = 1;		//学生的编号
	while (no <= 10) {
		cout << "这是第" << no++ << "名学生的编号\n";
	}

	for (no = 1; no <= 10; no++) {
		cout << "这是第" << no << "名学生的编号\n";
	}
}
```

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	for (int i = 1; i <= 9; i++) {
		for (int j = 1; j <= i; j++) {
			cout << i << "*" << j << "=" << i * j<<" ";
		}
		cout << endl;
	}
}
```

### 4)  do...while循环语句

语法:

do{

​	语句块;

}while(表达式);

注意:

1. 进入循环时,先执行一次语句块,在计算表达式的值
2. 循环的首部写在循环的尾部,(表达式)后面还有一个分号
3. 综上,不管表达式的值是真是假,都会先执行一次语句块的值

### 5)  goto语句(不咋常用)

称为无条件转移语句,语法:goto 语句标号;

如果在程序中使用了goto,程序的流程将跳转到语句标号的位置,并执行它后面的代码.其中语句标号是按标识符规定书写的符号,放在某一语句行的前面,可以独占一行,标号后加半角冒号

```
//包含头文件
#include <iostream>
using namespace std; //这个的作用相当于底下的std::可以不用写了
//main函数,程序从这里开始执行
int main()
{
	cout << "第一次执行\n";
goto bbb;
	cout << "第二次执行\n";
	cout << "第三次执行\n";
	cout << "第四次执行\n";
bbb:		//会直接跳转到bbb行以下的代码开始执行
	cout << "第五次执行\n";
}
```

