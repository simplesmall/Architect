#### 循环语句举例

```java
// 输出1~100内前5个可以被3整除的数.
public class Test{
    public static void main(String args[]){
        int num = 0,i = 1;
        while(i<=100){
            if(i % 3 == 0){
                sout(i + " ");
                num++;
            }
            if(num == 5){
                break;
            }
            i++;
        }
    }
}
```

```java
// 输出101~200内的质数
public class Test{
    public static void main(String args[]){
        // += 2因为现在是奇数,+1是偶数肯定不是质数
        for(int i=101;i<200;i+=2){
            boolean f = true;
            // 此处优化只用判断到一半就知道是否是质数
            for(int j = 2;j<(i/2);j++){
                if(i % j == 0){
                    f = false;
                    break;
                }
            }
            if (!f) {continue;}
            System.out.pprint(" " + i);
        }
    }
}
```

#### switch语句(条件语句补充)

- switch(){

  ​     case xx :

  ​			...

  ​	case  xx:

  ​			...

  ​	default:

  ​			.....

  }

- 小心case穿透,推荐使用break语句

  > case 1:
  >
  > ​	sout("AAA");
  >
  > case 2:
  >
  > ​	sout("BBB");

- 多个case可以合并到一起

  > case 1:
  >
  > case 2:
  >
  > case 3:

- default可以省略,但不推荐省略

- switch

- java 中switch 语句只能探测int类型值

#### 方法

> 方法类似于其他语言的函数,是一段用来实现特定功能的代码片段
>
> 形参 实参 返回值  返回值类型
>
> Java中进行函数调用中传递参数时,遵循值传递的原则:
>
> 基本类型传递的是该数据值本身,应用类型传递的是对象的引用,而不是对象本身.



#### 递归调用

> 在函数执行中调用函数本身的过程叫递归调用

```java
public class Test{
    public static void main(String args[]){
        System.out.println(method(5))
    }
    public static int method(int n){
        if(n<=1){
            return 1;
        }else{
            return n*method(n-1);
        }
    }
}
```

2021-4-13