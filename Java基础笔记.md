# IDEA快捷键

## 常规

| 功能                                       | 快捷键                     |
| ------------------------------------------ | :------------------------- |
| 复制一行                                   | 光标指定目标行，Ctrl+Alt+↓ |
| 生成构造器、批量生成setXxx()，getXxx()函数 | Alt+Insert                 |
| 查看继承关系                               | Ctrl+H                     |
| 查看类结构                                 | Alt+横排7                  |
| 项目结构栏显示/隐藏                        | Alt+横排1                  |
| 显示所有快捷键                             | Ctrl+J                     |
| 生成遍历集合的while语句                    | itit                       |
| 增强for语句                                | iter 或 (集合/数组名).for  |

##  断点调试快捷键

| 功能                         | 快捷键   |
| ---------------------------- | -------- |
| 跳入（跳入方法内）           | F7       |
| 跳过（逐行执行代码）         | shift+F8 |
| 执行到下一个断点（跳出方法） | F9       |
|                              |          |

![QQ浏览器截图20240208120915](C:\Users\LENOVO\Desktop\QQ浏览器截图20240208120915.png)

## 查看类结构体系图

1、找到该类，Ctrl+左键  或者  Ctrl+b  进入该类

2、右键，图表—>显示图，生成基本类图

3、空格，搜索并添加类

# 包

## 包命名规则

​	数字、字母、下划线、小圆点，不能以数字开头、不能是关键字、保留字

## 规范

​	com.公司名.项目名.业务模块                        

比如：

​	com.sina.crm.user//用户模块

​	com.sina.crm.order//订单模块

​	com.sina.crm.utils//工具类

## 常用包

​	java.lang.*            //lang包是基本包，默认引入，不需要在引入

​	java.util.*              //util包，系统提供的工具包，工具类，使用Sacnner

​	java.net.*              //网络包，网络开发

​	java.awt.*              //做java的界面开发，GUI

## 导入建议

​	需要哪个类就导入相应的包，不建议使用*导入

# this关键字

1、可用来访问本类的属性、方法、构造器

2、用于区分当前类的属性和局部变量

3、访问成员方法：this.方法名(参数列表)

4、访问构造器：this(参数列表) ； 只能在构造器中使用—只能在一个构造器里调用去访问另一个构造器

且必须放在第一行

5、this不能在类定义的外部使用，只能在类定义的方法中使用——只能在构造方法和类方法中使用

# 访问修饰符

  用于控制方法和属性（成员变量）的访问权限（范围）

1.公开级别：用public修饰，对外公开

2.受保护级别：用protected修饰，对子类和同一个包中的类公开

3.默认级别：没有修饰符，向同一个包的类公开

4.私有级别：用private修饰，只有类本身可以访问，不对外公开 

​	注：

​	1） 修饰符可以修饰类的属性，成员方法已经类

​	2）只用默认的和public才能修饰类

# 面向对象编程——封装

封装（encapsulation）：把抽象出来的数据（属性）和对数据的操作（方法）封装在一起，数据被保护在内部，程序的其他部分只能通过被授权的操作（方法），才能对数据进行操作。

## 实现步骤

1）将属性进行私有化private   （不能直接修改属性）

2）提供一个公共的（public）set方法，用于对属性判断并赋值

​	public void setXxx(类型  参数名){  //Xxx表示某个属性

​		//加入数据验证的业务逻辑

​		属性 = 参数名

}

3）提供一个公共(public)的get方法，用于获取属性的值

​	public 数据类型 getXxx(){          //权限判断，Xxx某个属性

 			return xx;

}

# 面向对象编程——继承

继承（extend）可以解决代码复用，让编程思维更接近人类思维。当多个类存在相同的属性（变量）和方法，可以从这些类中抽象出父类，在父类中定义这些相同的属性和方法，所有的子类不需要重新定义这些属性和方法，只需要通过extends来声明继承父类即可



## 基本语法

class 子类 extends 父类{

}

1）子类就会自动拥有父类定义的属性和方法

2）父类又叫超类，基类

3）子类又叫派生类

## 细节注意

1、子类继承了所有的属性和方法，非私有的属性和方法可以在子类直接访问，但私有（private）属性和方法不能在子类直接访问，要通过公共(public)的方法去访问

2、子类必须调用父类的构造器，完成父类的初始化

3、当创建子类对象时，不管使用子类的哪个构造器，默认情况下总会去调用父类的无参构造器，如果父类没有提供无参构造器，则必须在子类的构造器中用super去指定使用父类的哪个构造器完成对父类的初始化工作，否则，编译不会通过

4、如果希望指定去调用父类的某个构造器，则显式的调用一下：super(参数列表)

5、super在使用时，必须放在构造器的第一行        super()只能在构造器中使用

6、super()和this()都只能放在构造器的第一行，因此这两个方法能共存在一个构造器

7、java所有类都是Object类的子类，Object是所有类的基类

8、父类构造器的调用不限于直接父类！将一直往上追溯直到Object（顶级父类）

9、子类最多只能继承一个父类（指直接继承关系），即java中是单继承机制——如何让A类继承B类和C类——A继承B，B继承C

10、不能滥用继承，子类和父类之间必须满足A is B 逻辑关系

# super关键字

## 基本介绍

super代表父类的引用，用于访问父类的属性、方法、构造器

## 基本语法

1、访问父类的属性，但不能访问父类的private属性 —— super.属性名

2、访问父类的方法，不能访问private方法——super.方法名（参数列表）

3、访问父类的构造器——super（参数列表）——只能放在构造器第一句

## 细节

1、调用父类构造器 的好处  （分工明确，父类属性有父类初始化，子类属性由子类初始化）

2、当子类中有和父类中成员重名时，为了要访问父类的成员，必须通过super。如果没有重名，使用super、this、直接访问是一样的效果

3、super的访问不限于直接父类，如果爷爷类和本类有同名的成员，也可以使用super去访问爷爷类的成员；如果多个基类（上级类）中都有同名的成员，使用super访问遵循就近原则，A->B->C

## super和this的比较

![QQ浏览器截图20240131173440](C:\Users\LENOVO\Desktop\QQ浏览器截图20240131173440.png)

# 方法重写/覆盖(override)

## 基本介绍

子类有方法，和父类的某个方法的名称、返回类型、参数一样。那么称子类的这个方法覆盖了父类的那个方法。（不仅仅只是父子关系才算重写）

## 细节

1、子类的参数、方法名称。要和父类的参数，方法名称完全一致

2、子类方法的返回类型和父类方法返回类型一样，或是是父类返回类型的子类，比如：父类返回类型是Object，子类方法的返回类型是String				public Object getInfo(){}              public String getInfo({})

3、子类方法不能缩小父类方法的访问权限

public>protected>默认

# 面向对象编程——多态

## 具体表现

* 方法的多态：重写和重载体现

* 对象的多态(核心、重点)

  1、一个对象的编译类型和运行类型可以不一致

  2、编译类型在定义对象时，就确定了，不能改变

  3、运行类型是可以变化的，可以通过getClass()来查看运行类型

  4、编译类型看定义时 = 号的左边，运行类型看 = 号的右边

  ```java
  Animal animal=new Dog();   //animal编译类型是Animal,运行类型Dog
  animal=new Cat();    //animal的运行类型变成了Cat，编译类型仍然是Animal
  ```

  

  ![QQ浏览器截图20240131222437](C:\Users\LENOVO\Desktop\QQ浏览器截图20240131222437.png)

  ## 


## 细节

* 多态的前提：两个对象（类）存在继承关系

  

  ### 多态的向上转型

  1、本质：**父类的引用指向子类的对象**

  2、语法：父类类型	引用名 = new  子类类型（）

  3、特点：编译类型看左边，运行类型看右边

  > * 调用父类中的所有成员（需遵循访问权限）
  >
  > * 调用父类中的特有成员
  >
  > * 最终运行效果看子类的具体实现！

![QQ浏览器截图20240201152530](C:\Users\LENOVO\Desktop\QQ浏览器截图20240201152530.png)



### 多态的向下转型

1、语法：子类类型	引用名 = （子类类型）父类引用；

2、只能强转父类的引用，不能强转父类的对象

3、要求父类的引用必须指向的是当前目标类型的对象

4、可以调用子类类型中所有的成员

![QQ浏览器截图20240201153255](C:\Users\LENOVO\Desktop\QQ浏览器截图20240201153255.png)



### 属性重写问题

1、属性没有重写之说。属性的值看编译类型

![QQ浏览器截图20240201153738](C:\Users\LENOVO\Desktop\QQ浏览器截图20240201153738.png)

2、instanceof 比较操作符，用于判断对象的类型是否为XX类型或XX类型的子类型

```java
public class p {
    public static void main(String[] args) {
        BB bb = new BB();
        System.out.println(bb instanceof BB);//true
        System.out.println(bb instanceof AA);//true

        //aa 编译类型 AA ，运行类型是BB
        AA aa = new BB();
        System.out.println(aa instanceof AA);//true
        System.out.println(aa instanceof BB);//true

        Object object = new Object();
        System.out.println(object instanceof AA);//false
        String str = "hh";
        System.out.println(str instanceof Object);//true
    }
}
class AA {}//父类
class BB extends AA {}

```

### 总结

访问属性看编译类型  访问方法看运行类型

## Java动态绑定机制(重要）

> * 当调用对象方法时，**该方法会和该对象的内存地址/运行类型**绑定
> * 当调用对象属性时，**没有动态绑定机制**，哪里声明，那里用



## 多态的应用

### 1.多态数组

* 数组的定义类型为父类类型，里面保存的实际元素类型为子类类型

### 2.多态参数

* 方法定义的形参类型为父类类型，实参类型允许为子类类型



# Object类详解

## equals方法

==和equals的对比

### ==

​	1、既可以判断基本类型，又可以判断引用类型

​	2、如果判断基本类型，判断的是值是否相等

​	3、如果判断引用类型，判断的是地址是否相等，即判断是不是同一对象

![QQ浏览器截图20240202155348](C:\Users\LENOVO\Desktop\QQ浏览器截图20240202155348.png)

​		

### equals

1、是Object类中的方法，只能判断引用类型

2、默认判断的是地址是否相等，子类中往往重写该方法，用于判断内容是否相等

3、若是判断系统没有自带的类型，则equals()调用Object类中的原始方法，即判断对象是否相同

### ![QQ浏览器截图20240202160003](C:\Users\LENOVO\Desktop\QQ浏览器截图20240202160003.png)

### 总结

==	——判断是否为同一对象（引用类型时），

​										值相等（基本类型时）

equals（）——若该类中没有重写，则调用Object类中的equals（判断对象是否相同）

​							若重写了，则直接判断内容是否相同

## hashCode

1、提高具有哈希结构的容器的效率

2、两个引用，如果指向同一个对象，则哈希值肯定是一样的

3、两个引用，如果指向的是不同对象，则哈希值是不一样的

4、哈希值主要根据地址号来的，不能完全将哈希值等价于地址

5、在集合中，hashCode 如果需要的话，也会重写

## toString

默认返回：全类名+@+哈希值的十六进制			子类往往重写toString方法，用于返回对象的属性信息

**重写toString（），打印对象或拼接对象时，都会自动调用该对象的toString**

当直接输出一个对象,toString()会被默认的调用，比如：System.out.println(monster);     	就会默认调用monster.toString()

```java
package com.my8.Object;

public class toString {
    public static void main(String[] args) {
        /*
        Object的toString()源码:

        public String toString() {
        return getClass().getName() + "@" + Integer.toHexString(hashCode());
        }

        (1)getClass().getName() 类的全类名(包名+类名)
        (2)Integer.toHexString(hashCode())将对象的hashCode值转成16进制字符串
         */

        Monster monster = new Monster("小妖怪", "巡山", 20000);
//        System.out.println(monster.toString() + "\t hashCode:" + monster.hashCode());
//        以上toString没有重写的输出：com.my8.Object.Monster@723279cf	hashCode1915910607

//        通过输出对象，即可调用重写的toString方法
        System.out.println(monster);
//        重写toString后的输出：Monster{name='小妖怪', job='巡山', sal=20000.0}
    }
}

class Monster {
    private String name;
    private String job;
    private double sal;

    public Monster(String name, String job, double sal) {
        this.name = name;
        this.job = job;
        this.sal = sal;
    }

    //快捷键：Alt+Insert
    @Override
    public String toString() {
        return "Monster{" +
                "name='" + name + '\'' +
                ", job='" + job + '\'' +
                ", sal=" + sal +
                '}';
    }
}
```



## finalize

1、当对象被回收时，系统自动调用该对象的finalize方法。子类可以重写该方法，做一些释放资源的操作

2、什么时候被回收：当某个对象没有任何引用时，则 JVM就认为这个对象是一个垃圾对象，就会使用垃圾回收机制来销毁该对象，在销毁该对象前，会先调用finalize方法

3、垃圾回收机制的调用，是由系统来决定，也可以通过System.gc() 主动触发垃圾回收机制

# 房屋租赁项目

![image-20240208130852843](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240208130852843.png)

# 类变量

## 基本

![QQ浏览器截图20240203220233](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203220233.png)

注意：jdk8开始不能通过对象名访问静态变量了，只能通过类名访问

## 细节

![image-20240203220449880](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240203220449880.png)

![QQ浏览器截图20240203220642](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203220642.png)

# 类方法

## 基本

![QQ浏览器截图20240203220815](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203220815.png)

## 最佳实践

![QQ浏览器截图20240203222650](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203222650.png)

## 细节

![QQ浏览器截图20240203222738](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203222738.png)

![QQ浏览器截图20240203222749](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203222749.png)

# main方法

## 深入理解

![image-20240203223309967](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240203223309967.png)

## 特别提示

![QQ浏览器截图20240203223146](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203223146.png)

# 代码块

![QQ浏览器截图20240203223653](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203223653.png)

## 细节AND注意事项

![image-20240203223836827](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240203223836827.png)

![QQ浏览器截图20240203223935](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203223935.png)

![QQ浏览器截图20240203224035](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203224035.png)

# ![QQ浏览器截图20240203224123](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203224123.png)

# final

## 基本使用

![QQ浏览器截图20240203224610](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203224610.png)

## 细节

![QQ浏览器截图20240203224424](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203224424.png)

![QQ浏览器截图20240203224455](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203224455.png)

# 抽象类











# 接口

## 基本介绍

> 接口即给出一些没有实现的方法，封装在一起，到某个类要使用的时候，再根据具体情况把这些方法实现

* 小结

  1、在JDK7.0之前 接口里的所有方法都没有方法体

  2、JDK8.0后接口类可以有静态方法，默认方法，即接口中可以有方法的具体实现（接口中的方法可以有1、抽象方法	2、默认实现方法	3、静态方法）

## 实现接口VS继承类

### 解决的问题不同

* 继承的价值主要在于：解决代码的复用性和可维护性
* 接口的价值主要在于：设计、设计好各种规范（方法），让其他类去实现这些方法

### 接口比继承更加灵活

继承是满足 is - a 的关系，而接口只需满足 like - a 的关系

### 接口在一定程度上实现代码解耦

即：接口的规范性 + 动态绑定

## 细节

1、接口不能被实例化

2、接口中所有的方法是public方法，接口中抽象方法，可以不用abstract修饰

> void aaa()   <==>   abstract void a()

3、一个普通类实现接口，就必须将接口的所有方法都实现

**4、抽象类实现接口，可以不用实现接口的方法**

5、一个类同时可以实现多个接口   A implements B,C

6、接口中的属性，只能是final的，而且pulic static final修饰符

> int a=1    <==>   public static  final  int  a=1;(必须初始化)

7、接口中属性的访问形式：接口名.属性名

8、一个接口不能继承其他类，但是可以继承多个别的接口

```java
interface A extends B,c{}
```

9、接口的修饰符 只能是public和默认，这点和类的修饰符是一样的

## 接口的多态特性

![QQ浏览器截图20240203205606](C:\Users\LENOVO\Desktop\QQ浏览器截图20240203205606.png)



# 四种内部类

## 局部内部类

## 匿名内部类

## 成员内部类

## 静态内部类

# 枚举类

## 自定义类实现

![QQ浏览器截图20240216150817](C:\Users\LENOVO\Desktop\QQ浏览器截图20240216150817.png)

### 步骤

![QQ浏览器截图20240216123540](C:\Users\LENOVO\Desktop\QQ浏览器截图20240216123540.png)

类加载在实例化对象前发生

## enum关键字实现

![image-20240216150741431](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240216150741431.png)

# 注解类

# 异常

体系结构图：

![image-20240209104232362](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240209104232362.png)

![QQ浏览器截图20240209104445](C:\Users\LENOVO\Desktop\QQ浏览器截图20240209104445.png)

![QQ浏览器截图20240209104549](C:\Users\LENOVO\Desktop\QQ浏览器截图20240209104549.png)

## 常见运行时异常

1、NullPointerException——空指针异常		当应用程序试图在需要对象的地方使用 null 时，抛出异常

2、ArithmeticException——数学运算异常		当出现异常的运算条件时，抛出此异常。如，一个整数"除以零"时，抛出此类的一个实例

3、ArrayIndexExceptionBoundsException——数组下标越界异常		访问数组时的索引为负或大于等于数组大小

4、ClassCastException——类型转换异常		当试图将对象强制转换为不是实例的子类时，抛出该异常

5、NumberFormatException——数字格式不正确异常		当应用程序试图将字符串转换成一种数值类型，但该字符串不能转换为适合格式时，抛出该异常—>使用tryCatch异常可以确保输入满足条件数字

# 八大Wrapper(包装)类

![QQ浏览器截图20240211132023](C:\Users\LENOVO\Desktop\QQ浏览器截图20240211132023.png)

![QQ浏览器截图20240211132130](C:\Users\LENOVO\Desktop\QQ浏览器截图20240211132130.png)

# String类

## 结构剖析

![image-20240213094245035](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240213094245035.png)

## 细节

![QQ浏览器截图20240211132634](C:\Users\LENOVO\Desktop\QQ浏览器截图20240211132634.png)

## 两种创建String对象的区别

![QQ浏览器截图20240211132944](C:\Users\LENOVO\Desktop\QQ浏览器截图20240211132944.png)

# StringBuffer类

## 结构剖析

![image-20240212232732821](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240212232732821.png)

![image-20240212232742353](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240212232742353.png)

![image-20240212232751837](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240212232751837.png)

## String对比StringBuffer

![QQ浏览器截图20240212232816](C:\Users\LENOVO\Desktop\QQ浏览器截图20240212232816.png)

## 构造器

![QQ浏览器截图20240212233252](C:\Users\LENOVO\Desktop\QQ浏览器截图20240212233252.png)

## String—>StringBuffer

![QQ浏览器截图20240212233332](C:\Users\LENOVO\Desktop\QQ浏览器截图20240212233332.png)

## Stringbuffer—>String

![image-20240212233611415](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240212233611415.png)

## 常用方法

![QQ浏览器截图20240212233741](C:\Users\LENOVO\Desktop\QQ浏览器截图20240212233741.png)

![QQ浏览器截图20240212233758](C:\Users\LENOVO\Desktop\QQ浏览器截图20240212233758.png)

# StringBuilder类

![QQ浏览器截图20240212234306](C:\Users\LENOVO\Desktop\QQ浏览器截图20240212234306.png)

![QQ浏览器截图20240212234235](C:\Users\LENOVO\Desktop\QQ浏览器截图20240212234235.png)

# 注（）

单线程推荐使用StringBuilder，多线程直接StringBuffer

![QQ浏览器截图20240213085020](C:\Users\LENOVO\Desktop\QQ浏览器截图20240213085020.png)

# Math类

Math类包含用于执行基本数学运算方法，如初等指数、对数、平方根和三角函数

abs(绝对值)、pow(求幂)、ceil(向上取整)、floor(向下取整)、round(四舍五入)、sqrt(求平方)、random(求随机数)、max(求两个数的最大值)、min(求两个数的最小值)

返回 a 到 b 之间的整数的公式：(int)(a + Math.random()*(b-a+1))

# Array类

Arrays里面包含了一系列静态方法用于管理或操作数组（比如排序和搜索）

1、toString返回数组的字符串形式————Arrays.toString(str)

2、sort排序(自然排序和定制排序)

3、binarySearch通过二分搜索法进行查找，要求必须排好序——int index = Arrays.binarySearch(arr,3);



# System类

## 常用方法

1、exit退出当前程序

2、arraycopy：复制数组元素，比较适合底层调用，一般使用Arrays.copyOf完成复制数组

3、currentTimeMillens：返回当前时间距离1970-1-1的毫秒数

4、gc：运行垃圾回收机制	System.gc()

# BigInteger和BigDecimal类

## 应用场景

1、BigInteger适合保存比较大的整型

2、BigDecimal适合保存精度更高的浮点型（小数）

## 常用方法

1、add 加

2、substract 减

3、multiply 乘

4、divide 除

# Date(日期)类



# Calendar类



# 第三代日期类

LocalDate（日期/年月日）、LocalTime（时间/时分秒）、LocalDateTime（日期时间/年月日时分秒）JDK8加入



# 集合

## 基本功能

1、可以动态保存任意多个对象，使用比较方便				2、提供了一系列方便的操作对象的方法：add、remove、set、get等			3、使用集合添加，删除新元素的简洁

## 分类

Java的集合类有很多，主要分为两类：

### 单列集合

![image-20240213103022061](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240213103022061.png)

### 双列集合

![image-20240213103107389](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240213103107389.png)

# Collection

 ## Collection接口实现类的特点

![QQ浏览器截图20240214123051](C:\Users\LENOVO\Desktop\QQ浏览器截图20240214123051.png)

## Collection接口常用方法

![QQ浏览器截图20240213103421](C:\Users\LENOVO\Desktop\QQ浏览器截图20240213103421.png)

以下以ArrayList类来演示：

```java
package phase2.my7.Collection;

import java.util.ArrayList;
import java.util.List;

public class CollectionMethod {
    @SuppressWarnings({"all"})
    public static void main(String[] args) {
        List list = new ArrayList();
        //  1、add：添加单个元素
        list.add("jack");
        list.add(10);   //本质：list.add(new Integer(10))
        list.add(true);
        System.out.println("list=" + list);    // list=[jack, 10, true]
        //  2、remove：删除指定元素
        //  3、list.remove(0)————删除第一个元素
        list.remove(true);  //删除指定某个元素
        System.out.println("list=" + list);     // list=[jack, 10]
        //  4、contains：查找元素是否存在
        System.out.println(list.contains("jack"));  //true
        //  5、size：获取某个元素
        System.out.println(list.size());    //2
        //  6、isEmpty：判断是否为空
        System.out.println(list.isEmpty());   //false
        //  7、clear：清空
        list.clear();
        System.out.println("list=" + list);    // list=[]
        //  8、addAll：添加多个元素
        ArrayList list2 = new ArrayList();
        list2.add("红楼梦");
        list2.add("三国演义");
        list.addAll(list2);
        System.out.println("list=" + list);    // list=[红楼梦, 三国演义]
        //  9、containsAll：查找多个元素是否都存在
        list.add("水浒传");
        System.out.println(list.containsAll(list2));    //true
        //  10、removeAll：删除多个元素
        list.removeAll(list2);
        System.out.println("list=" + list);   // list=[水浒传]
    }
}

```

## 迭代器—遍历

```java 
package phase2.my7.Collection;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

public class Iterator_ {
    @SuppressWarnings({"all"})
    public static void main(String[] args) {
        Collection col = new ArrayList();
        col.add(new Book("红楼梦", "曹雪芹", 20.6));
        col.add(new Book("水浒传", "施耐庵", 56.6));
        col.add(new Book("三国演义", "罗贯中", 23.6));
        //利用迭代器遍历
        //1、先得到 col 对应的迭代器
        Iterator iterator = col.iterator();
        //2、用 while 循环遍历
        //方法一
        while (iterator.hasNext()) {  //判断是否还用数据元素
            //  iterator.next() 返回下一个元素对象，可用 Object的类来接收,因为 ArrayList集合类中可能不是存放的同一种类型对象
            System.out.println(iterator.next());
        }

        //方法二
        // 快捷件 itit
        while (iterator.hasNext()) {
            Object next = iterator.next();
            System.out.println("obj=" + next);
        }
    }
}

class Book {
    private String name;
    private String author;
    private double price;

    public Book(String name, String author, double price) {
        this.name = name;
        this.author = author;
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getAuthor() {
        return author;
    }

    public void setAuthor(String author) {
        this.author = author;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }

    @Override
    public String toString() {
        return "Book{" +
                "name='" + name + '\'' +
                ", author='" + author + '\'' +
                ", price=" + price +
                '}';
    }
}

```

### 执行原理

![QQ浏览器截图20240214123608](C:\Users\LENOVO\Desktop\QQ浏览器截图20240214123608.png)

## for循环增强—遍历

特点：增强for循环就是简化版的iterator，本质一样

> 只能用于遍历集合或者数组

![QQ浏览器截图20240214124127](C:\Users\LENOVO\Desktop\QQ浏览器截图20240214124127.png)

元素名随意命名

## 补充

1、在Java中，不能直接实例化一个接口，但可以实例化实现了该接口的类的对象。这些类的对象可以被当作接口类型的引用来使用，这就是多态性的一个体现

2、生成遍历集合的while语句——快捷键—— itit+回车

## Collections工具类

![QQ浏览器截图20240218121336](C:\Users\LENOVO\Desktop\1\QQ浏览器截图20240218121336.png)

![image-20240218121442426](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218121442426.png)

# List接口

![image-20240217102901993](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240217102901993.png)

![image-20240217102926496](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240217102926496.png)

## 遍历

![image-20240217102940864](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240217102940864.png)

## 排序练习

![QQ浏览器截图20240217103233](C:\Users\LENOVO\Desktop\QQ浏览器截图20240217103233.png)

## ArrayList

### 底层操作机制源码分析

![QQ浏览器截图20240217110533](C:\Users\LENOVO\Desktop\QQ浏览器截图20240217110533.png)

### 序列化

序列化就是串行化，Serialization的另一种翻译；序列化就是存储到硬盘；序列化就是保存数据的时候连同类型一起保存；序列化简单来说就是把对象转为二进制字节，方便传输

# Map

使用非常广泛，Map无论是框架底层还是以后开发 增删改查的时候，经常用到

## Map接口实现类的特点

![QQ浏览器截图20240218115507](C:\Users\LENOVO\Desktop\1\QQ浏览器截图20240218115507.png)

## Map接口常用方法

![QQ浏览器截图20240218120250](C:\Users\LENOVO\Desktop\1\QQ浏览器截图20240218120250.png)

## Map遍历方式

![QQ浏览器截图20240218120654](C:\Users\LENOVO\Desktop\1\QQ浏览器截图20240218120654.png)

## HashMap

### 小结

![QQ浏览器截图20240218121001](C:\Users\LENOVO\Desktop\1\QQ浏览器截图20240218121001.png)

### 底层机制

![image-20240218121135919](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218121135919.png)

# 泛型

generic

（内容不多，难度不大；实际应用比较多）

传统方法缺点：

![image-20240218121712061](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218121712061.png)

## 好处

![image-20240218121840875](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218121840875.png)

## 介绍

![image-20240218121918388](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218121918388.png)

## 语法

![QQ浏览器截图20240218122833](C:\Users\LENOVO\Desktop\1\QQ浏览器截图20240218122833.png)

## 注意事项和细节

![image-20240218123858973](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218123858973.png)

![image-20240218123941654](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218123941654.png)

![image-20240218124102121](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218124102121.png)

![image-20240218124348443](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218124348443.png)

# 自定义泛型

![image-20240218174742784](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218174742784.png)

![image-20240218174834136](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218174834136.png)

![image-20240218174704639](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218174704639.png)

![image-20240218175057000](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218175057000.png)

# Junit

![image-20240218203643106](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218203643106.png)

## 我的使用

快捷键：Alt+Enter

![image-20240218203920750](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218203920750.png)

![image-20240218204006780](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218204006780.png)

加载动态：

![image-20240218204049107](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20240218204049107.png)

根据报错信息，加入了Junit4，并导入包之后

@Test	不再报错，在方法上添加此注释，即可单独运行方法

## 注意

这里不能连接联通的wifi，联通屏蔽了maven；第一次用要有网络