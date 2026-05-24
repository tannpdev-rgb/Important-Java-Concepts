# Toàn bộ 50 Từ khóa Java kèm theo Ví dụ

Bảng bên dưới liệt kê 48 Từ khóa (Keywords) trong Java; ngoại trừ các từ khóa `goto` và `const` vì chúng hiện tại không được sử dụng.

<!--![keywords-in-java](https://user-images.githubusercontent.com/2780145/34911899-785e9aa8-f8f9-11e7-8970-87ebd9e02574.jpg)-->

| <!-- -->    | <!-- -->    | <!-- -->    | <!-- -->    | <!-- -->    |
|-------------|-------------|-------------|-------------|-------------|
|abstract|default|if|private|this|
|assert|do|implements|protected|throw|
|boolean|double|import|public|throws|
|break|else|instanceof|return|transient|
|byte|enum|int|short|try|
|case|extends|interface|static|void|
|catch|final|long|strictfp|volatile|
|char|finally|native|super|while|
|class|float|new|switch|-|
|continue|for|package|synchronized|-|

## 1) abstract

Từ khóa `abstract` được sử dụng để triển khai tính trừu tượng (abstraction) trong java. Một phương thức không có phần định nghĩa bắt buộc phải được khai báo là `abstract` và class chứa nó cũng phải được khai báo là `abstract`. Bạn không thể khởi tạo instance (thực thể) của các abstract classes. Các phương thức `abstract` bắt buộc phải được implement ở trong các lớp con (sub classes). Bạn không thể sử dụng từ khóa `abstract` đối với các biến (variables) và các hàm khởi tạo (constructors).

```java
abstract class AbstractClass
{
    abstract void abstractMethod();
}
```

## 2) assert

Từ khóa `assert` được sử dụng trong các câu lệnh khẳng định (assertion statements). Những câu lệnh này sẽ cho phép bạn kiểm tra các giả định của mình về một chương trình. Các câu lệnh Assertion cung cấp phương thức tốt nhất để phát hiện và sửa chữa các lỗi lập trình (programming errors). Câu lệnh Assertion nhận đầu vào là một biểu thức boolean (boolean expression) và giả định rằng điều này sẽ luôn luôn đúng (true). Nếu biểu thức boolean trả về false, `AssertionError` sẽ bị ném ra.

```java
System.out.println("Nhập vào điểm số của bạn");
         
Scanner sc = new Scanner(System.in);
         
int marks = sc.nextInt();
         
assert marks > 35 : "FAIL";
```

## 3) boolean

Từ khóa `boolean` được sử dụng để định nghĩa các biến thuộc kiểu boolean. Các biến kiểu boolean chỉ có thể lưu giữ hai giá trị – là `true` (đúng) hoặc `false` (sai).

```java
boolean isActive = true;
```

## 4) break

Từ khóa `break` được sử dụng để dừng quá trình thực thi của một vòng lặp (for, while, switch-case) dựa trên một số điều kiện nhất định.

```java
for (int i = 0; i < 100; i++)
{
    System.out.println(i);
             
    if(i == 50) break;
}
```

## 5) byte

Từ khóa `byte` được sử dụng để khai báo các biến thuộc kiểu byte. Một biến byte có thể chứa một giá trị số (numeric value) trong phạm vi từ -128 cho đến 127.

```java
byte b = 50;
```

## 6) switch       7) case

Cả hai từ khóa `switch` và `case` đều được dùng trong câu lệnh switch-case.

```java
Scanner sc = new Scanner(System.in);

System.out.println("Nhập Ngày :");

int day = sc.nextInt();

switch (day) 
{
    case 1:
        System.out.println("CHỦ NHẬT");
        break;

    case 2:
        System.out.println("THỨ HAI");
        break;

    //...

    case 7:
        System.out.println("THỨ BẢY");
        break;

    default:
        System.out.println("Không hợp lệ");
        break;
}
```

## 8) try     9) catch     10) finally

Các từ khóa `try`, `catch` và `finally` được sử dụng để xử lý các ngoại lệ (exceptions) trong java. Các câu lệnh cần được theo dõi (monitored) để tìm ngoại lệ sẽ được đặt ở trong khối `try`. Các ngoại lệ ném ra bởi khối `try` sẽ được bắt (caught) ở trong khối `catch`. Khối `finally` thì luôn luôn được thực thi.

```java
try 
{
    int i = Integer.parseInt("abc");
} 
catch (NumberFormatException ex) 
{
    System.out.println(ex);
} 
finally 
{
    System.out.println("Phần này sẽ luôn được thực thi");
}
```

## 11) char

Từ khóa `char` được sử dụng để khai báo các biến kiểu nguyên thủy (primitive) char. Biến `char` đại diện cho các ký tự (characters) trong java.

```java
char a = 'A';
         
char b = 'B';
         
char c = 'C';
```

## 12) class

Từ khóa `class` được sử dụng để định nghĩa các lớp (classes) trong java.

```java
class MyClass
{
    class MyInnerClass
    {
        //Lớp lồng bên trong (Inner Class)
    }
}
```

## 13) continue

Từ khóa `continue` được sử dụng để kết thúc quá trình thực thi của vòng lặp hiện tại (current iteration) và bắt đầu thực thi vòng lặp tiếp theo bên trong một cấu trúc lặp (loop).

```java
for (int i = 0; i <= 100; i++)
{
    if(i % 5 != 0)  continue;
             
    System.out.println(i);
}
```

## 14) default

Từ khóa `default` được dùng để định nghĩa các phương thức mặc định (default methods) ở trong một interface (Kể từ phiên bản Java 8). Từ khóa `default` cũng được dùng ở trong các câu lệnh switch-case.

```java
interface MyInterface 
{
    public default void myDefaultMethod() 
    {
        System.out.println("Phương thức mặc định (Default Method)");
    }
}
```

## 15) do

Từ khóa `do` được dùng bên trong một vòng lặp do–while. Vòng lặp do-while dùng để thực thi lặp đi lặp lại một hay nhiều câu lệnh (statements) cho đến khi một điều kiện trả về `false`.

```java
int a = 10;

int b = 20;

do {
    a = a + b;

    b = b + 10;

    System.out.println("a = " + a);

    System.out.println("b = " + b);

} while (a <= 100);
```

## 16) double

Từ khóa `double` được dùng để khai báo biến kiểu nguyên thủy double.

```java
double d1 = 23.56;
         
double d2 = 56.23;
         
double d3 = d1 + d2;
         
System.out.println(d3);
```

## 17) if         18) else

Các từ khóa `if` và `else` được dùng trong khối lệnh if-else.

```java
Scanner sc = new Scanner(System.in);
         
System.out.println("Nhập vào một chuỗi (string) :");
         
String input = sc.next();
         
if(input.equalsIgnoreCase("JAVA"))
{
    System.out.println("Đây là JAVA");
}
else
{
    System.out.println("Không phải JAVA");
}
```

## 19) enum

Từ khóa `enum` được dùng để định nghĩa các kiểu enum.

```java
enum Color
{
    RED, GREEN, BLUE;
}
 
public class Test
{
    public static void main(String[] args)
    {
        Color c1 = Color.RED;
        System.out.println(c1);
    }
}
```

## 20) extends

Từ khóa `extends` được dùng trong tính kế thừa (inheritance). Nó được dùng khi một class kế thừa lại một class khác.

```java
class SuperClass
{
    //Lớp cha (Super Class)
}
 
class SubClass extends SuperClass
{
    //Lớp con (Sub Class)
}
```

## 21) final

Từ khóa `final` được dùng khi một class hoặc một phương thức (method) hoặc một trường (field) không cần các sửa đổi về sau này nữa. `final` class không thể bị mở rộng (extended), `final` method không thể bị ghi đè (overridden) và giá trị của một `final` field không thể bị thay đổi.

```java
final class FinalClass
{
    final int finalVariable = 10;
     
    final void finalMethod()
    {
        //final method
    }
}
```

## 22) float

Từ khóa `float` biểu thị cho các biến kiểu nguyên thủy float.

```java
float f1 = 45.26f;
         
float f2 = 84.25f;
         
float f3 = f2 - f1;
         
System.out.println(f3);
```

## 23) for

Vòng lặp `for` được dùng để thực thi một tập hợp các câu lệnh cho đến chừng nào một điều kiện nào đó là `true`.

```java
for (int i = 0; i <= 10; i++)
{
    System.out.println(i);
}
```

## 24) implements

Từ khóa `implements` được dùng trong khi thực thi (implementing) một interface.

```java
interface MyInterface
{
    void myMethod();
}
 
class MyClass implements MyInterface
{
    public void myMethod()
    {
        System.out.println("My Method");
    }
}
```

## 25) import

Từ khóa `import` được dùng để nạp (import) các thành viên của một gói (package) cụ thể vào file java hiện tại.

```java
import java.sql.*;
import java.util.Arrays;
import java.util.Scanner;
```

## 26) instanceOf

`instanceOf` được dùng để kiểm tra xem liệu một object có thuộc một kiểu được chỉ định hay không. Cú pháp để dùng từ khóa `instanceOf` là `Object_Reference instanceOf Type`.

```java
class A
{
     //...
}
 
public class MainClass
{
    public static void main(String[] args) 
    {
        A a = new A();
         
        if(a instanceof A)
        {
            System.out.println("a thuộc kiểu A (a is of type A)");
        }
    }
}
```

## 27) int

Từ khóa `int` được dùng để khai báo các biến kiểu nguyên thủy số nguyên (integer).

```java
int i1 = 10;
         
int i2 = 20;
         
int i3 = i1 *  i2;
         
System.out.println(i3);
```

## 28) interface

Từ khóa `interface` được dùng để định nghĩa các giao diện (interfaces) trong java. Nó là một cơ chế giúp đạt được sự trừu tượng hóa (abstraction). Chỉ có thể có các abstract methods trong Java interface, chứ không chứa nội dung (body) của method.

```java
interface MyInterface
{
    void myMethod();
}
```

## 29) long

Từ khóa `long` được dùng để định nghĩa các biến kiểu nguyên thủy long.

```java
long l1 = 101;
         
long l2 = 202;
         
long l3 = l1 +  l2;
         
System.out.println(l3);
```

## 30) native

Từ khóa `native` được dùng cùng với một method để chỉ định rằng một method cụ thể nào đó được triển khai dưới dạng mã gốc (native code) thông qua việc sử dụng các Java Native Interfaces(JNI).

```java
class AnyClass
{
    public native void anyMethod(int i, double d);
}
```

## 31) new

Từ khóa `new` được dùng trong lúc khởi tạo các instance của một class.

```java
class A
{
     //...
}
 
public class MainClass
{
    public static void main(String[] args) 
    {
        A a = new A();
    }
}
```

## 32) package

Từ khóa `package` được dùng để chỉ định một gói mà tệp (file) hiện tại trực thuộc.

```java
package pack1;
 
class A
{
     //...
}
```

## 33) private

Từ khóa `private` được dùng để khai báo thành viên của một class ở dạng riêng tư (private). Các methods và các trường private chỉ có thể nhìn thấy (hoặc gọi) trong chính class mà chúng được định nghĩa.

```java
class A
{
    private int i = 111;   //private field
     
    private void method()
    {
        //private method
    }
}
```

## 34) protected

Từ khóa `protected` được dùng để khai báo một thành viên của class ở dạng protected. Các thành viên protected của một class có thể được nhìn thấy trong chính package của chúng mà thôi, tuy nhiên chúng có thể được kế thừa sang cho bất kỳ class con (sub classes) nào.

```java
class A
{
    protected int i = 111;   //protected field
     
    protected void method()
    {
        //protected method
    }
}
```

## 35) public

Từ khóa `public` được dùng để khai báo các thành viên của một class hoặc chính bản thân class đó ở mức công khai (public). Các thành viên public của một class có thể nhìn thấy từ bất cứ đâu và chúng có thể được kế thừa lại bởi bất kỳ sub classes nào.

```java
public class A
{
    public int i = 222;   //public field
     
    public A()
    {
        //public constructor
    }
     
    public void method()
    {
        //public method
    }
}
```

## 36) return

Từ khóa `return` được dùng để trả quyền điều khiển về lại cho người gọi (caller) từ một method.

```java
class A
{
    int method(int i)
    {
        return i*i;     //phương thức (method) trả về một giá trị
    }
}
```

## 37) short

Từ khóa `short` được dùng để khai báo các biến kiểu nguyên thủy short.

```java
short s1 = 11;
         
short s2 = 22;
```

## 38) static

Từ khóa `static` được dùng để định nghĩa các thành viên cấp độ lớp (class level members) của một class. Các thành viên `static` của class được lưu trữ trong bộ nhớ của class đó và bạn có thể truy cập chúng trực tiếp thông qua tên của class. Không cần thiết phải khởi tạo instance của class để xài nó.

```java
class A
{
    static int staticField = 555;    //Static Field (Trường Tĩnh)
     
    static void staticMethod()
    {
        //Static method (Hàm Tĩnh)
    }
}
 
public class MainClass
{
    public static void main(String[] args) 
    {
        System.out.println(A.staticField);    //Truy cập staticField qua tên class
         
        A.staticMethod();     //Truy cập staticMethod qua tên class
    }
}
```

## 39) strictfp

Từ khóa `strictfp` được dùng để đảm bảo độ chính xác nghiêm ngặt đối với các phép tính dấu phẩy động (floating point calculations) ở trên nhiều nền tảng (platforms) khác nhau. `strictfp` có thể được dùng với classes, interfaces và methods.

```java
strictfp interface I
{
    //strictfp áp dụng lên interface
}
 
strictfp class C
{
    //strictfp áp dụng lên class
}
 
class A
{
    strictfp void method()
    {
        //strictfp áp dụng lên method
    }
}
```

## 40) super

Từ khóa `super` được dùng để truy cập vào các thành viên của lớp cha (super class) từ bên trong của một lớp con (sub class).

```java
class A
{
    int i;
     
    public A(int i) 
    {
        this.i = i;
    }
     
    void methodA()
    {
        System.out.println(i);
    }
}
 
class B extends A
{
    public B()
    {
        super(10);    //Gọi hàm khởi tạo (constructor) của super class
    }
     
    void methodB()
    {
        System.out.println(super.i);    //truy cập field của super class
         
        super.methodA();    //Gọi method của super class
    }
}
```

## 41) synchronized

Từ khóa `synchronized` được dùng để triển khai sự đồng bộ hóa (synchronization) trong java. Tại một thời điểm, chỉ có duy nhất một thread có thể chạy lọt vào trong một method hoặc một khối lệnh được khai báo với `synchronized`. Bất kỳ thread nào muốn nhảy vào chạy method hoặc khối đó đều bắt buộc phải chiếm (acquire) được khóa (lock) của object thuộc những method hay khối block đó.

```java
class AnyClass
{
    synchronized void synchronizedMethod()
    {
        //Synchronized method
    }
     
    void anyMethod()
    {
        synchronized (this) 
        {
            //Synchronized block
        }
    }
}
```

## 42) this

Từ khóa `this` được dùng để truy cập vào các thành viên khác nằm trong cùng một class.

```java
class AnyClass
{
    int i;
  
    AnyClass()
    {
        System.out.println("First Constructor (Hàm khởi tạo Đầu tiên)");
    }
  
    AnyClass(int j)
    {
        this();    //câu lệnh gọi (calling statement) tới First Constructor
        System.out.println("Second Constructor (Hàm khởi tạo Thứ hai)");
    }
  
    void methodOne()
    {
        System.out.println("Từ method one");
    }
  
    void methodTwo()
    {
        System.out.println(this.i);  //Truy cập field trong cùng một class
        this.methodOne();      //Truy cập method trong cùng một class
    }
}
```

## 43) throw

Từ khóa `throw` được dùng để ném ra các lỗi ngoại lệ (exceptions) một cách thủ công (manually).

```java
public class MainClass
{
    public static void main(String[] args) 
    {
        try
        {
            //ném NumberFormatException thủ công 
             
            throw new NumberFormatException();
        }
        catch(Exception ex)
        {
            System.out.println(ex);
        }
    }
}
```

## 44) throws

Từ khóa `throws` được dùng để định danh cho các exceptions mà phương thức hiện hành (current method) có thể ném ra.

```java
class A
{
    void method() throws NumberFormatException
    {
        int i = Integer.parseInt("abc");
    }
}
```

## 45) transient

Từ khóa `transient` được dùng trong quá trình tuần tự hóa (serialization). Một biến đã được khai báo với mác `transient` sẽ không còn đủ điều kiện đáp ứng cho khâu tuần tự hóa nữa.

```java
class MyClass implements Serializable
{
    int a;
     
    transient String s;   //Phần này sẽ KHÔNG được serialize
     
    double d;
}
```

## 46) void

Từ khóa `void` được dùng để thông báo biểu thị rằng method hiện hành sẽ không trả lại bất cứ giá trị nào cả (returns nothing).

```java
class A
{
    void methodReturnsNothing()
    {
        //Method không trả về (returns) giá trị nào
    }
}
```

## 47) volatile

Từ khóa `volatile` được sử dụng trong lĩnh vực lập trình đồng thời (concurrent programming). Giá trị của một biến (variable) một khi được ấn định (declared) là `volatile` sẽ được ghi đè thẳng (written into) hoặc lấy truy xuất (read from) cội rễ trực tiếp từ the main memory (bộ nhớ chính).

```java
class A
{
    public volatile int counter = 0;
}
```

## 48) while

Từ khóa `while` được đem dùng phục vụ cho thể loại vòng lặp (while loop).

```java
int i = 10;
         
while (i <= 100)
{
    System.out.println(i);
             
    i = i + 10;
}
```

## 49) goto        50) const

Cả hai từ `goto` và `const` đều là các từ khóa dành riêng (reserved words) của ngôn ngữ lập trình java, cơ mà hiện ở thời điểm thực tại chúng đều đang đắp chiếu bỏ không (currently not used).
