# java疯狂讲义

## 一、概述和开发环境

### 1.运行

java文件→javac编译→.class文件(和平台无关的字节码文件)→java解释(jvm)→特定平台的机械码

jdk1.5以上不用设置classpath

### 2.组织形式

必须要有 public static void main(String[] args)这个入口函数

主文件名和文件中public类名相同

### 3.垃圾回收

当没有引用变量指向某个对象内存时，内存就会被释放

通常将对象的引用变量设置为null，暗示可回收

## 二、理解面向对象

### 1.结构化和面向对象的区别

结构化:自上而下，采用数据流的数据处理方式，唯一入口和唯一出口

面向对象:最小的是类(成员变量+方法=类定义)

封装，继承，多态

除了八个基本的数据类型，一切都是对象

## 三、数据类型和运算符

先声明后使用；指定变量的数据类型

注释

### 1.数据类型

基本数据类型:boolean和数值类型(整型(byte，short，long，int，char)和浮点型(double，float))

char是使用单引号括起来，string是使用双引号括起来

数值下面可以使用下划线分割

boolean型只可以是true和false，不可以是0或非0

范围小的数据类型可以向范围大的数据类型转换

byte→short→int→long→float→double

char→int→long→float→double

任何数值类型和字符串做运算，都会转换成字符串

强制转化:(数据类型)数值

#### 随机数

Math.random()生成的是0~1之间的数

Math.random()*26生成的是0~26之间的数

再用char把生成的随机数转换成字符类型，进行拼接

5.6默认是double类型，使用float转换成float型

字符串默认无法转换成基本类型，例如int类型需要Integer.parseInt()强制转换

转换成Int型
int/Integer num  =  Integer.parseInt(String str);
转换成long型
Long/long num    =  Long.parseLong(String str);
转换成short型
short/Short num  =  Short.parseShort(String str);
转换成float型
float/Float num  =  Float.parseFloat(String str);
转换成double型
double/Double num = Double.parseDouble(String str);

####自动提升

整个算数表达式的数据类型自动提升到与表达式中最高等级操作数同样的类型

#### 求余

如果有小数的话，小数点前后分别求余

#### 自加(自减)

放左面会先自加(自减)，再放入表达式运算，放右面会先自加(自减)，再放入表达式运算

#### 位运算符

都是根据二进制码运算

两个>是右移一定位数后，符号位补充左面

三个>是右移一定位数后，使用0补充左面

对于int来说，如果大于32，则求余后再进行计算

对于long来说，如果大于64，则求余之后再进行计算

#### 其他补充运算符

如果是 byte b = 5      b+=5    这样就不会报错

#### 逻辑运算符

不短路或和或

不短路或左右都会计算

或是只要第一个为true，剩下的就不会计算

## 四、流程控制和数组

if...else

把范围小的放在前面处理

switch...case...default

switch后只能是int char byte short，枚举类型和java.lang.string类型，不能是boolean类型

while

do...while

for

由于continue没有和循环体在一起，即使使用continue，for循环也依旧会执行

不要在循环体中对循环变量进行修改，应该新声明一个临时变量，把循环变量值给临时变量，再对临时变量进行修改

#### 嵌套循环

外层循环n次，内层循环m次，实际内层循环n*m次

break

不仅可以结束当前循环体，也可以根据标签结束外层循环体

标签:标签名:

continue

忽略这次循环后的语句

也可以结合标签使用

return

直接结束方法

#### 数组

元素必须都是相同类型

长度不可变

最好只用 数据类型[]数组名    定义数组

只有初始化才能使用数组

静态初始化:数据类型[]数组名={元素}

动态初始化：数据类型[]数组名=new 数据类型{数组长度}

foreach:for(数据类型 形参:数组名)

