# use cpp

## 准备
**前提进入到文件的目录中**

- 编译
  - `g++ name.cpp -o namea.exe`

- 执行
  - `run namea.exe`
 
## 基本点
- 类型
  - int a=10
  - folat b=1.2f
  - double c=12.2
  - char d ='f'
  - bool e=0
  - char str[]="heloo"
  - string f ="heloo"  串自带‘\0‘作为结束标志，不属于串内容
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
## 函数
- 定义
  - 返回类型  函数名（参数）{ 函数内容；return 返回类型的数据；} 不需要返回值可使用void
  - 主函数main（）
- 声明
  - 返回类型  函数名（参数类型列表也可以）；
  - **注意**
    - 特别是在当前文件上声明，在别的函数文件中调用的函数
    - 参数可以设置默认值，有默认值当元素靠后定义 ，当没有传递值，使用默认值
    - 声明与定义分开做时，函数声明提供默认值，定义不设置默认值
    - 
















  


