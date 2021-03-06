### 面向对象

##### 设计思想

> 基本思想是,从现实世界中客观存在的事物来构造软件系统,并在系统的构造中尽可能运用人类的思维方式.
>
> 面向对象更加强调运用人类在日常思维逻辑中经常采用的思维方式,如抽象,分类,继承,聚合,多态,等.

##### 对象和类的概念

- 对象用计算机语言对问题域中事物的描述,对象通过`属性`和`方法`来分别对应事物所具有的静态属性和动态属性
- 类是用于描述描述同一类型的对象的抽象概念,类中定义了这一类对象应有的属性和方法
- 类可以看做是一类对象的模板,对象可以看作一个类的具体实例化.

**具体事务 --->抽象为`类`   --->  实例化为 `对象`**

##### 类(对象)间的关系

###### 关联关系

> (弱关系)  学院   教授  学生

###### 继承关系

> `(一般与特殊)`xxx 是 一种 xxx: 小狗是一种动物

###### 聚合关系

> `(整体和部分)`  聚集(松耦合): 球队中聚集队长和队员  组合(高耦合,必可不少):人的四肢组合成为完整的人

###### 实现关系

###### 多态

------

### 面向对象设计思想

#### 为什么用对象

- 面向对象的编程-一组对象互相配合通过沟通完成特定功能
  - 汇编是对机器语言的抽象
  - 面向过程是对汇编语言的抽象
  - 对象更符合对于现实问题的抽象
- 对象都有对外服务的接
  - 通过继承可以复用
- 对象隐藏内部服务的实现
  - 通过聚合可以复用
- OO更加容易使我们达到所追求的目的
  - Reusable , Extensibility , 维护和替换更加方便
- 组件--比对象更高层次的抽象(二进制级别)
  - EJB ,Web Service , CORBA, COM....



### 面向对象内存解析

#### 成员变量

- 可以是Java语言中任何一种数据类型(基本类型和引用类型)
- 定义成员变量时可以对其初始化,如果不初始化则默认赋值对应数据类型的默认值(局部变量遵循定义赋值使用)
- 成员变量的作用域为整个类体

| byte | short | int  | long | char     | float | double | boolean |
| ---- | ----- | ---- | ---- | -------- | ----- | ------ | ------- |
| 0    | 0     | 0    | 0L   | `\u0000` | 0.0F  | 0.0D   | false   |

#### 引用

- Java语言中除了基本数据类型都是引用类型
- Java中对象是通过引用对其操作的.

> String s;      // 声明一个String引用变量,没有指向任何对象,值为null
>
> s = new String("Get up!");  // new 一个对象并将s指向它

**如何在内存中区分类和对象**

- 类是静态概念,代码区
- 对象是new出来的,位于堆内存,各个对象的不同属性不同(静态变量除外),而方法只有一份,调用的时候才占用内存

#### 对象的创建和使用

- 必须使用new关键字创建对象
- 使用 `.`操作符操作成员变量和方法
- 同一类的每个对象有不同的成员变量存储空间
- 同一类的每个对象共享该类的方法

#### 构造方法

- 使用new + 构造函数创建一个新的对象

- 构造函数是定义在Java类中的一个用来初始化对象的函数

- 构造函数与类同名且没有返回值

  **没用指定构造函数系统自动指定一个不带参构造函数,一旦指定系统默认你处理所有情况下的构造函数**

> 命名规则:
>  类名首字母大写   函数,属性首字母小写,使用驼峰

####  新建对象内存分配:

```java
Test test = new Test();
int date = 9;
Birthday d1 = new Birthday(7,7,1970);
```

> 以上代码在执行`new Test`的时候在`栈`中分配一个test对象的空间指向`堆`空间;
>
> 并在栈空间上分配对应类对象属性的字段及默认数据类型的值;
>
> 调用构造函数将栈空间上的数据值赋值到堆空间上的对象对应属性字段和值中,删除栈空间上分配的对象属性字段及默认数据类型的值. 

