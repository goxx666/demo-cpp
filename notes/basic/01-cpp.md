# use cpp

## 准备
**前提进入到文件的目录中**

- 编译
  - `g++ name.cpp -o namea.exe`

- 执行
  - `run namea.exe`
 
## 基本点
- 代码编译前的准备工作
  - 文件头部需要含有以下预处理指令
  - #include “iostream”
  - using namespace std;
- 类型
  - int a=10
  - folat b=1.2f
  - double c=12.2
  - char d ='f'
  - bool e=0
  - char str[]="heloo"
  - string f ="heloo"  串自带‘\0‘作为结束标志，不属于串内容
- 注释
  - 单行注释 //
  - 多行注释/*……*/
- 引入库
  - #include “库名”

  
- 符号常量
  - #define 符号名 值
  - 多行注释/*……*/
- 运算
  - &&与；｜｜或；！非
  - 位运算： 与&  或｜ 非^  取反-  左移<<  右移>>
  - 条件运算        条件 ？X ：Y  条件真执行X；条件假执行Y
  - ( , , ) 顺序执行运算，返回逗号列表中最后一个表达式的值
  - sizeof（）返回字节数
- 条件
  - if（）{} else{}
  - switch(){case 结果1:语句；break；case 结果2:语句；break；……；default:语句； break；}
  - while(条件){语句}
  - for（；；）{}
  - do{ 语句 }while( 条件 )
  - break；结束循环；continue；结束当前轮进入下一轮


- 一维数组
  - 声明 type name[size]
  - 初始化 type name[size]={ 内容，个数不能大于size }
  - 初始化 type name[]={ 内容 }，size是内容个数
  - 赋值  name[号]= 内容
  - 访问  name[号]
- 多维数组
  - 声明 type name[size  1][size  2]……[size  n]
- 二维
  - 初始化 type name[size  1][size  2]={{,},{,},{,},……}
  - 赋值  name[号][号]= 内容
  - 访问  name[号][号]
- 注意
  - 字符数组，可以声明初始化时时可以整体赋值，其他赋值只能用name[号]= 内容
  - 分开定义的数组，不可以整体赋值，只能每个元素的赋值遍历
 
- goto
  - 无条件跳转  标签：    goto 标签；
 




## 函数
- 定义
  - 返回类型  函数名（参数）{ 函数内容；return 返回类型的数据；} 不需要返回值可使用void
  - 主函数main（）
- 声明
  - 返回类型  函数名（参数类型列表也可以）；
  - **注意**
    - 特别是在当前文件上声明，在别的函数文件中调用的函数
    - 参数可以设置默认值，有默认值当元素靠后定义 ，当没有传递值，使用默认值
    - 声明与定义分开处理时，函数声明提供默认值，定义不设置默认值
- 内联函数
  -  指定内联函数 inline 返回类型  函数名（参数）；
  -  常用于规模小、常调用的简单函数适用
## 指针
- 声明
  - 类型  *指针名；
  - **注意**
    - 值是一个变量的地址；是代表内存地址的的长的十六进制数
    - 变量地址  &变量名
- 赋值（给地址）
  - 指针名= &变量名
- 使用
  - 指针名   是   变量地址
  - *指针名   是   变量存放值
- const  修饰使用
  - 修饰指针 -- 指针指向p1可以修改，指向值*p1不可修改
    - const int *p1 = &a;
  - 修饰常量 -- 指针指向p2不可修改，指向值*p2可以修改
    - int * const p2 = &a;
  - 修饰指针和常量 -- p3、*p1  都不可修改
    - const int * const p3 = &a;
- 指针自增运算 
  - p++ 指针向前移动4个字节，指向下一个整型元素的地址，指向下一个元素的地址
- 指针向指针的指针 
  - 声明  类型  **指针名； 指向此类型指针的指针
- 空指针，指针赋值为NULL、nullptr;野指针，不赋值的指针

## 指针与数组
- **注意**
    - 数组名是数组起始地址、数组指针，可传递
- 指针p和数组d的赋值
  - 函数定义形参是指针
    - int *p1 = d;
  - 指向元素 
    - int *p2 = &d[0];
  - 定义与赋值分开
    - int *p3 ;
    - p3 = &d[0];

## 指针与函数
- **注意**
    - 指针做函数的参数，通过传递地址来修改参数值
- 函数形参 设为指针（地址传递）
  - 定义形参是指针
    - 如：void add（int * p1）;
  - 形参是指针与变量的区别 
    - 是指针：在函数中，指针指向的内容*p1，会在函数处理中保存处理
    - 是变量：在函数中，变量值不会改变，会在函数处理中使用但不保存
  - 调用
    - void add（&a）;
    - void add（a）;
- 函数返回值 设为指针
  - 定义返回是指针
    - 如：int *add（int x,inty）;
  - 返回值是指针与变量的区别 
    - 是指针：返回一个地址，可用于数组的返回，返回数组名
    - 是变量：在函数中，变量值不会改变，会在函数处理中使用但不保存
  - 调用
    - p1=add(1,2);


## 结构体
- 声明
  - struct 结构体名  {成员声明列表}结构体变量列表；
    - 如：struct student{int num;char sex;}student1,student2;
    - struct person{int count;char name[10];}leader[2]={{22,"we"},{33,"sh"}};
    - 可以直接使用student1、leader[]

## 共用体
- **注意**
    - 在相同内存位置存放不同类型数据，使用时只有一个成员带有值
    - 占用的内存是最大成员内存
    - 名首字母大写
    - 在函数体外定义
- 定义（名字、变量名可以省）
  - union 名字{类型 变量；……}变量名;
    - 如：union Data{int i;float f;char str[20]}data;
    - 如：union Data{int i;float f;char str[20]};
- 使用
  - union Data mm;
  - mm.f=10
  - 在给共用体赋值，赋值多个，只有最后一次赋值的内容与数据类型元素对应，读取其他元素是赋值的转译
 

## 枚举

- 定义（名字、变量名可以省）
  - enum 类型名{枚举常量表};
    - 如：enum week{sun,mon,tue,wed,thu,fri,sat};对应0，1，2，3，4，5，6
    - 如：enum week{sun,mon,tue=3,wed,thu,fri,sat};对应0，1，3，3，4，5，6
    - 如：enum week{sun=7,mon=1,tue,wed,thu,fri,sat};对应7，1，2，3，4，5，6
- 使用
  - union Data mm;
  - mm.f=10
  - 
- **注意**
    - 列举所有的取值项
    - 枚举常量有一个默认整数值，同数组下标；也可指定数值，未指定的按依次+1取值
 


## 类（对象的基础模板）和对象
- 类定义
  - class  类名（参数）{ 访问修饰:类型 变量元素；……；类方法(){} } ；
  - 访问修饰：public公共成员，在类外部可访问、private（默认）外部不可查看访问，类和友元函数（含子函数）可访问、protected在派生子类不可访问

- 对象声明--根据类创建
  - class  类名（参数）{ 访问修饰:类型 变量元素；……；类方法(){} } ；
  - 访问修饰：public公共成员，可以在类外部访问、private、protected

- 构造函数
  -  在创建新对象时执行，用于成员变量设置初始值，不会返回
  -  不带参数，或者带参数赋初始值   ：  函数名-与类名同（参数）；
  -  多个字段需要初始化
  -  类名::类名(类型 a,类型 b，……)：字段1（a），字段2（b）……{//构造函数}

- 析构函数
  -  在删除对象前执行，释放资源
  -  不返回，不带参数： ～ 函数名-与类名同；
  -  在使用结束后会调用
  
- 成员函数
  -  类中定义的方法，属于类
  -  可在类中声明和定义
  -  可在类中声明，在外部使用解析运算符::定义
    -  返回类型 类：：方法名（参数列表）{}

- 静态成员
  -  static定义类中成员 ，基于类创建对象，共享、操作同一份数据
  -  静态变量声明     static 变量名；
    - 基于类创建的对象，共享、操作同一份数据，类内声明，类外使用解析运算符::初始化
    - int Car：：a=0；
  -  静态成员函数声明     static 变量名；
    -  所有对象共享同一个函数，只能访问静态成员变量
 

 

 -  使用 `类构造` 函数案例

```cpp
class Car{
  public:
    Car(double size);//构造函数
    ～Car();//析构函数
    void setSize( double size );
    double getSize(void);
    
  private:
    int no;
    double slength;
  };

  Car::Car(int non,double size){//构造函数
    no=non;
    slength=size;
  }
  Car::～Car(){//析构函数
  }
  void Car::setSize( double size ){//成员函数， 设置/修改值
    slength=size;
  }
  double Car::getSize(void){//成员函数,  显示当前值（类外部使用范围解析运算符）
    return slength;
  }


int main() {
    Car bus(666,778.77);
    cout << "first" <<bus.getSize()<< endl;
    cout << "size" <<bus.no<< endl;

    return 0;
}
```

- const修饰（不可修改）
  - 修饰成员函数（为常函数）
    - 不可修改成员属性
  - 修饰对象（为常对象）
    - 只能调用常函数  

- 友元
  - 友元函数
    - 定义在类外部
    - 可访问类的所有私有和保护成员，可在类声明中使用，但不属于类
    - 声明friend 返回类型 函数名（参数列表）；
    - 可在类外定义，返回类型 函数名（参数列表）{}；

  - 友元类
    - 整个类和成员都是友元
   

  - 访问对象的成员
    - 使用 .元素，访问；但只有public使用这种访问
    - 私有和保护需要通过内部函数调用返回使用
    - 对象实例自带的指针this，通过此指针访问自己的地址，可以在类成员函数中使用，用于指向调用对象
    - 成员函数可使用this指针，友元函数不可使用
 


## 继承-基于一个基类定义另一个派生类
- 定义
  - class 派生类：继承方式 基类{派生内容}
  - 继承方式：public、protected、private
  - 共有继承-公用成员、保护成员在派生类中类型不变，私有类是基类不派生
  - 保护继承-公用成员、保护成员在派生类中变保护，私有类是基类不派生
  - 私有继承-公用成员、保护成员在派生类中变私有，私有类是基类不派生
  - 可以继承多个父类     class 派生类：继承方式 基类，继承方式 基类，……{派生内容}
  - **注意**
    - 不能继承析构函数，派生类的析构函数调用基类的析构函数
    - 继承：先调用基类的的构造函数再调用派生类的构造函数
    - 析构：先调用派生再调用基类的
    - 不能继承构造函数



## 多态
- 静态多态
  - 函数重载--复用函数名
    - 不同功能函数用同一个函数名，根据参数数量、类型、顺序不同，选择执行
  - 运算符重载--带特殊名称的函数，可以在类内/外定义
    - 声明   返回类型  operator重载运算符（参数列表）；
    - Car operator+（const Car&，const Car&）；     类外定义，需要两个传参，在类内定义定义一个参数再使用this，加法运算法把Car两个对象加，返回Car对象
    - 调用 Car3=Car1+Car2；
    - **注意**
      - 不可重载的运算符：  .  ,  .*  ,  ->* ,  ::  , sizeof ,  ?: , #<img width="276" height="261" alt="image" src="https://github.com/user-attachments/assets/f624d0f8-1643-4e73-8eeb-f5a22fa6d160" />

      - <img width="552" height="368" alt="image" src="https://github.com/user-attachments/assets/af43ec41-0614-407f-ae88-9bf658bb2c86" />

- 动态多态-派生类、虚函数使用，运行时多态
  - 虚函数在基类中用virtual声明，如果不使用此声明，不会调用派生类的同名方法
  - 派生类中可重新定义虚函数
  - 根据调用的对象类型选择调用的函数，函数名称同参数列表可同、可不同
  - 当基类中不需有内容的虚函数，可设置纯虚函数  virtual 返回类型 函数名（）=0；    （说明没有函数主体）



## 文件、流
- 头文件
  - <iostream>用于标准输入输出流
  - <iomanip>通过流操纵器，声明执行标准话有用的服务
  - <fstream>文件处理
  
- 标准输出流cout--是ostream的实例
  - cout << ""<<""<<endl；
  - endl换行
  - 中文输出乱码解决：
    - 法一：引入windows.h库；再main中设置 SetConsoleOutputCP( wCodePageD: CP_UTF8);
    - 法二：main中设置system ( Command: "chap 65001");
 
- 标准输入流cin--是istream的实例（对象），接收字符串
  - cin >> 数组变量；
  - 此对象有使用方法可用cin. 进行访问其附加函数
  - 中文输入乱码解决：修改注册表设置

- 文件输入输出流
  - <img width="655" height="127" alt="image" src="https://github.com/user-attachments/assets/987d7030-cf96-4f5c-9976-6c0d8555d401" />
    - 文件操作
    - 打开  open()是fstream、ifstream、ofstream对象成员
      - void open(const char *filename，iOS：：打开模式1 ｜ iOS：：打开模式2)；第一个参数是打开文件的名称和位置，第二个参数定义文件被打开的模式，也可以省略
      - 打开模式-可以把多种模式结合使用
      - <img width="655" height="169" alt="image" src="https://github.com/user-attachments/assets/d2fc2250-0398-4d62-8f06-dd6499e60644" />
    - 关闭（自动关闭刷新所有流，释放所有分配的内存，关闭所有打开的文件，用于程序终止前关闭所有已打开的文件）  close()是fstream、ifstream、ofstream对象成员
      - void close()；
      - 打开模式-可以把多种模式结合使用
      - <img width="655" height="169" alt="image" src="https://github.com/user-attachments/assets/d2fc2250-0398-4d62-8f06-dd6499e60644" />
 


##vscode中运行
- 函数需要加上 system ("pause");避免运行完直接结束关闭运行窗口






















