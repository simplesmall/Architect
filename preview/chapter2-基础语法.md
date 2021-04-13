#### 变量

**变量必须先声明再赋值最后才能使用**

变量的声明: variableType  variable = value

> 程序执行过程
>
> 1. Load到内存区
> 2. 找到main方法开始执行
> 3. 执行过程中的内存管理

|      存放内容      |      内存中分区      |
| :----------------: | :------------------: |
|   new 出来的东西   |       heap(堆)       |
|      局部变量      |      stack(栈)       |
| 静态变量字符创常量 | data segment(数据区) |
|      存放代码      | code segment(代码区) |

#### Java变量的分类:

> `方法体内部`声明的变量(包括形参)称为局部变量:

> 在方法体外,`类体内`声明的变量称为成员变量

#### 数据类型

数据类型  	基本数据类型	数值型	整数类型(byte,short,int,long)

​																浮点类型(float,double)

​												字符型(char)

​												布尔型(boolean)

​					引用数据类型	类(class)

​												接口(interfdace)

​												数组

------

`boolean`只允许true或false,不可以0或非0的整数替代true

##### 字符型 char

- char型数据用来表示通常意义上的"字符"

- 字符常量为用单引号括起来的单个字符.例如:

  char eChar = 'a';

- Java字符采用Unicode编码,每个字符占两个字节,因而可用十六进制编码形式表示;

  例如: char c1 = '\u0061'; `注: Unicode是全球语言统一编码`

- Java语言中允许使用转义字符`'\'`来将字符转义为其它的含义,例如:

  char c2 = '\n';

##### 整数类型

**Java里面没有无符号的整数**

| 类型  | 占用存储空间 |   表数范围   |
| ----- | ------------ | :----------: |
| byte  | 1字节        |   -128~127   |
| short | 2字节        | -2^15~2^15-1 |
| int   | 4字节        | -2^31~2^31-1 |
| long  | 8字节        | -2^63~2^63-1 |

##### 浮点类型

**默认是double类型,如果声明一个float型,后面加f或F  float f = 12.3f**

> 因为浮点数有一定误差,所以一般不直接比较float类型的变量,而是做减法之后判断

| 类型   | 占用存储空间 | 表数范围             |
| ------ | ------------ | -------------------- |
| float  | 4字节        | -3.403E38~-.403E38   |
| double | 8字节        | -1.798E308~1.798E308 |

#### 基本数据类型转换

- boolean类型不可以转换为其它的数据类型

- 整形,字符型,浮点型的数据在混合运算中相互转,转换时遵循一下规则:

  - 容量小的类型自动向大的类型转换,排序为:

    **byte,short,char -> int -> long -> float ->double**

    byte,short,char 之间不会互相转换,他们三者在计算时首先转换为int类型

  - 容量大的数据转换为小的时要加强制转换符,但可能会造成精度降低或溢出

  - 有多种数据类型一起参与运算时,系统默认将所有数据转换为容量最大的数据类型,再进行计算

  - 实数常量默认为double  (如: 1.34)

  - 整数常量默认为int   (如 422)

```java
public class TestConvert{
    public void main(String arg[]){
        int i1 = 123;
        int i2 = 456;
        double d1 = (i1+i2)*1.2; // 系统将转换为double型运算
        float f1 = (float)(i1+i2)*1.2;//double->float 加强制转换符
        
        byte b1 = 1;
        byte b2 = 2;
        byte b3 = (byte)(b1+b2);//int->byte 
        
        double d2 = 1e200;
        float f2 = (float)d2;//会产生溢出 超出-3.403E38~-.403E38
        System.out.println(f2);
        
        float f3 = 1.232f; // 必须加f
        long l1 = 123;
        long l2 = 30000000000l; // 必须加l(小写的L)
        float f = l1 + l2 + f3; // 系统转换为float型计算
        long l = (long)f; // 强制转换会直接舍去小数部分(不是四舍五入)
    }
}
```

#### 语句

##### 条件语句

> 根据不同条件,执行不同语句  只有一句需要执行时可以省略  { }

- if
- if ... else
- if ... else if
- if ... else if ...else if ... else
- switch

##### 循环语句

> 重复执行某些动作

- for(JDK1.5语法)

  for(初始条件;判断条件;运算式)

- while

  while(逻辑表达式){语句;....;}

- do ... while

  do{语句;...;}while(逻辑表达式);

##### break & continue语句

- break 

  > 用于终止某个语句块的执行,强行退出循环

- continue

  > 用于终止某次循环过程,跳过循环体中continue语句下面未执行的循环,开始下一次循环过程.

2021-4-13