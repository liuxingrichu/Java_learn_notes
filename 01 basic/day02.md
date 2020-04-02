## 文档结构 ##
1. Java类概述
	1. 类中变量
	1. 构造方法
	2. 创建对象
2. 源文件声明规则
3. Java包
4. 程序运行条件



### Java类概述 ###
类有若干种访问级别，并且类也分不同的类型：*抽象类和final类等。*

Java还有一些特殊的类，如：*内部类、匿名类。*

#### 类中变量 ####
- 局部变量
	- 在方法、构造方法或者语句块中定义的变量被称为局部变量。变量声明和初始化都是在方法中，方法结束后，变量就会自动销毁。
- **成员变量（非静态变量）**
	- 成员变量是定义在类中，方法体之外的变量。这种变量在创建对象的时候实例化。成员变量可以被类中方法、构造方法和特定类的语句块访问。
- **类变量（静态变量）**
	- 类变量也声明在类中，方法体之外，但必须声明为static类型。


#### 构造方法 ####
每个类都有构造方法。如果没有显式地为类定义构造方法，Java编译器将会为该类提供一个默认构造方法。

在创建一个对象的时候，至少要调用一个构造方法。**构造方法的名称必须与类同名，一个类可以有多个构造方法。**

#### 创建对象 ####
对象是根据类创建的。在Java中，使用关键字new来创建一个新的对象。

- 创建对象需要以下三步：
	1. 声明：声明一个对象，包括对象名称和对象类型。
	2. 实例化：**使用关键字new来创建一个对象。**
	3. 初始化：使用new创建对象时，会调用构造方法初始化对象。

			public class Puppy{
			   public Puppy(String name){
			      //这个构造器仅有一个参数：name
			      System.out.println("小狗的名字是 : " + name ); 
			   }
			   public static void main(String[] args){
			      // 下面的语句将创建一个Puppy对象
			      Puppy myPuppy = new Puppy( "tommy" );
			   }
			}

### 源文件声明规则 ###

- 当在一个源文件中定义多个类，并且还有import语句和package语句时，要特别注意这些规则。
	- **一个源文件中只能有一个public类**
	- 一个源文件可以有多个非public类
	- **源文件的名称应该和public类的类名保持一致。**例如：源文件中public类的类名是Employee，那么源文件应该命名为Employee.java。
	- **如果一个类定义在某个包中，那么package语句应该在源文件的首行。**
	-** 如果源文件包含import语句，那么应该放在package语句和类定义之间。**如果没有package语句，那么import语句应该在源文件中最前面。
	- **import语句和package语句对源文件中定义的所有类都有效。在同一源文件中，不能给不同的类不同的包声明。**

### Java包 ###
包主要用来对类和接口进行分类。当开发Java程序时，可能编写成百上千的类，因此很有必要对类和接口进行分类。

- import语句
	- 在Java中，如果给出一个完整的限定名，包括包名、类名，那么Java编译器就可以很容易地定位到源代码或者类。Import语句就是用来提供一个合理的路径，使得编译器可以找到某个类。
	- 例如，下面的命令行将会命令**编译器载入java_installation/java/io路径下的所有类**

			import java.io.*;

### 程序运行条件 ###

**程序都是从main方法开始执行。为了能运行程序，必须包含main方法并且创建一个实例对象。**

	import java.io.*;
	public class EmployeeTest{
	 
	   public static void main(String[] args){
	      /* 使用构造器创建两个对象 */
	      Employee empOne = new Employee("RUNOOB1");
	      Employee empTwo = new Employee("RUNOOB2");
	 
	      // 调用这两个对象的成员方法
	      empOne.empAge(26);
	      empOne.empDesignation("高级程序员");
	      empOne.empSalary(1000);
	      empOne.printEmployee();
	   }
	}

