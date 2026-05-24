# Nền tảng Java và Lập trình Hướng đối tượng

Lập trình Hướng đối tượng (Object-Oriented Programming) là một phương pháp luận hoặc mô hình để thiết kế một chương trình sử dụng các lớp (classes) và đối tượng (objects). Nó làm đơn giản hóa việc phát triển và bảo trì phần mềm. Các khái niệm chính - Kế thừa (Inheritance), Đa hình (Polymorphism), Trừu tượng (Abstraction), Đóng gói (Encapsulation).

## Các Kiểu Dữ liệu trong Java

<table class="alt"> 
<tbody><tr> 
  <th id="table_dvpt_datatype"><strong>Kiểu Dữ liệu (Data Type)</strong></th> 
  <th id="table_dvpt_defaultvalue"><strong>Giá trị Mặc định (Default Value)</strong></th> 
  <th id="table_dvpt_defaultsize"><strong>Kích thước Mặc định (Default Size)</strong></th> 
</tr> 
<tr> 
<td headers="table_dvpt_datatype">boolean</td> 
<td headers="table_dvpt_defaultvalue">false</td> 
<td headers="table_dvpt_defaultsize">1 bit</td> 
</tr> 
<tr> 
<td headers="table_dvpt_datatype">char</td> 
<td headers="table_dvpt_defaultvalue">'\u0000'</td> 
<td headers="table_dvpt_defaultsize">2 byte</td> 
</tr> 
<tr> 
<td headers="table_dvpt_datatype">byte</td> 
<td headers="table_dvpt_defaultvalue">0</td> 
<td headers="table_dvpt_defaultsize">1 byte</td> 
</tr> 
<tr> 
<td headers="table_dvpt_datatype">short</td> 
<td headers="table_dvpt_defaultvalue">0</td> 
<td headers="table_dvpt_defaultsize">2 byte</td> 
</tr> 
<tr> 
<td headers="table_dvpt_datatype">int</td> 
<td headers="table_dvpt_defaultvalue">0</td> 
<td headers="table_dvpt_defaultsize">4 byte</td> 
</tr> 
<tr> 
<td headers="table_dvpt_datatype">long</td> 
<td headers="table_dvpt_defaultvalue">0L</td> 
<td headers="table_dvpt_defaultsize">8 byte</td> 
</tr> 
<tr> 
<td headers="table_dvpt_datatype">float</td> 
<td headers="table_dvpt_defaultvalue">0.0f</td> 
<td headers="table_dvpt_defaultsize">4 byte</td> 
</tr> 
<tr> 
<td headers="table_dvpt_datatype">double</td> 
<td headers="table_dvpt_defaultvalue">0.0d</td> 
<td headers="table_dvpt_defaultsize">8 byte</td> 
</tr> 
</tbody></table>

LƯU Ý : UTF-8 là chuẩn mã hóa ký tự unicode phổ biến nhất với 90% các trang web đang sử dụng.

## Sự thăng cấp Kiểu Dữ liệu (Data Type Promotion) trong Java :

![data type promotion small](https://user-images.githubusercontent.com/2780145/34364362-403e9db4-eaab-11e7-914b-7acc9007cf41.png)

## Các Wrapper Class trong Java

<table class="alt">
<tbody><tr><th>Kiểu Nguyên thủy (Primitive Type)</th><th>Wrapper class</th></tr>
<tr><td>boolean</td><td>Boolean</td></tr>
<tr><td>char</td><td>Character</td></tr>
<tr><td>byte</td><td>Byte</td></tr>
<tr><td>short</td><td>Short</td></tr>
<tr><td>int</td><td>Integer</td></tr>
<tr><td>long</td><td>Long</td></tr>
<tr><td>float</td><td>Float</td></tr>
<tr><td>double</td><td>Double</td></tr>
</tbody></table>

## Các Toán tử trong Java

<table class="alt"> 
<tbody><tr><th>Loại Toán tử (Operator Type)</th><th>Danh mục (Category)</th><th>Độ ưu tiên (Precedence)</th></tr> 
<tr> 
<td rowspan="2">Một ngôi (Unary)</td><td>hậu tố (postfix)</td><td><code><em>expr</em>++ <em>expr</em>--</code></td> 
</tr>  
<tr> 
<td>tiền tố (prefix)</td><td headers="precedence"><code>++<em>expr</em> --<em>expr</em> +<em>expr</em> -<em>expr</em> ~ !</code></td> 
</tr> 
<tr> 
<td rowspan="2">Số học (Arithmetic)</td><td>nhân chia (multiplicative)</td><td headers="precedence"><code>* / %</code></td> 
</tr> 
<tr> 
<td>cộng trừ (additive)</td><td headers="precedence"><code>+ -</code></td> 
</tr> 
<tr> 
<td>Dịch (Shift)</td><td>dịch bit (shift)</td><td headers="precedence"><code>&lt;&lt; &gt;&gt; &gt;&gt;&gt;</code></td>  
</tr> 
<tr> 
<td rowspan="2">Quan hệ (Relational)</td><td>so sánh (comparison)</td><td headers="precedence"><code>&lt; &gt; &lt;= &gt;= instanceof</code></td> 
</tr> 
<tr> 
<td>bằng nhau (equality)</td><td headers="precedence"><code>== !=</code></td> 
</tr>  
<tr> 
<td rowspan="3">Thao tác bit (Bitwise)</td><td>bitwise AND</td><td headers="precedence"><code>&amp;</code></td> 
</tr> 
<tr> 
<td>bitwise exclusive OR</td><td headers="precedence"><code>^</code></td> 
</tr> 
<tr> 
<td>bitwise inclusive OR</td><td headers="precedence"><code>|</code></td> 
</tr>  
<tr> 
<td rowspan="2">Logic (Logical)</td><td>logical AND</td><td headers="precedence"><code>&amp;&amp;</code></td> 
</tr> 
<tr> 
<td>logical OR</td><td headers="precedence"><code>||</code></td> 
</tr> 
<tr> 
<td>Ba ngôi (Ternary)</td><td>ternary</td><td headers="precedence"><code>? :</code></td> 
</tr> 
<tr> 
<td>Gán (Assignment)</td><td>assignment</td><td headers="precedence"><code>= += -= *= /= %= &amp;= ^= |= &lt;&lt;= &gt;&gt;= &gt;&gt;&gt;=</code></td> 
</tr> 
</tbody></table>

## Các Quy ước Đặt tên trong Java :

<table class="alt">
<tbody><tr><th>Tên (Name)</th><th>Quy ước (Convention)</th></tr>
<tr><td>tên class (class name)</td><td> nên bắt đầu bằng chữ cái in hoa và là một danh từ 
<br>vd. String, Color, Button, System, Thread, v.v.</td></tr>
<tr><td>tên interface (interface name)</td><td>nên bắt đầu bằng chữ cái in hoa và là một tính từ 
<br>vd. Runnable, Remote, ActionListener, v.v.</td></tr>
<tr><td>tên phương thức (method name)</td><td>nên bắt đầu bằng chữ cái in thường và là một động từ 
<br>vd. actionPerformed(), main(), print(), println(), v.v.
</td></tr>
<tr><td>tên biến (variable name)</td><td>nên bắt đầu bằng chữ cái in thường
<br>vd. firstName, orderNumber, v.v.</td></tr>
<tr><td>tên gói (package name)</td><td>nên viết toàn bộ bằng chữ cái in thường 
<br>vd. java, lang, sql, util, v.v.
</td></tr>
<tr><td>tên hằng số (constants name)</td><td>nên viết toàn bộ bằng chữ cái in hoa.
<br>vd. RED, YELLOW, MAX_PRIORITY, v.v.</td></tr>
</tbody></table>

## Object vs Class

<table class="alt">
<tbody><tr><th>Đối tượng (Object)</th><th>Lớp (Class)</th></tr>
<tr><td>Đối tượng là một <strong>thực thể (instance)</strong> của một lớp.</td><td>Lớp là một <strong>bản thiết kế hoặc khuôn mẫu (blueprint/template)</strong> từ đó các đối tượng được tạo ra.</td></tr>
<tr><td>Đối tượng là một <strong>thực thể trong thế giới thực</strong> như cái bút, laptop, điện thoại, cái giường, bàn phím, con chuột, cái ghế, v.v.</td><td>Lớp là một <strong>nhóm các đối tượng tương tự nhau</strong>.</td></tr>
<tr><td>Đối tượng là một thực thể <strong>vật lý</strong>.</td><td>Lớp là một thực thể <strong>logic</strong>.</td></tr>
<tr><td>Đối tượng được tạo ra thông qua <strong>từ khóa new</strong> là chủ yếu, vd. Student s1=new Student();</td><td>Lớp được khai báo bằng cách sử dụng <strong>từ khóa class</strong>, vd. class Student{}</td></tr>
<tr><td>Đối tượng được tạo ra <strong>nhiều lần</strong> tùy theo yêu cầu.</td><td>Lớp được khai báo <strong>một lần</strong>.</td></tr>
<tr><td>Đối tượng <strong>cấp phát bộ nhớ khi nó được tạo ra</strong>.</td><td>Lớp <strong>không cấp phát bộ nhớ khi nó được tạo ra</strong>.</td></tr>
<tr><td>Có <strong>nhiều cách để tạo đối tượng</strong> như từ khóa new, phương thức newInstance(), phương thức clone(), factory method & deserialization.</td><td>Chỉ có <strong>một cách để định nghĩa lớp</strong> trong Java là sử dụng từ khóa class.</td></tr>
</tbody></table>

## Constructors vs Methods

<table class="alt">
<tbody><tr><th>Hàm tạo (Java Constructor)</th><th>Phương thức (Java Method)</th></tr>
<tr><td>Constructor được dùng để khởi tạo trạng thái của một đối tượng.</td><td>Method được dùng để thể hiện hành vi của một đối tượng.</td></tr>
<tr><td>Constructor không được phép có kiểu trả về (return type).</td><td>Method bắt buộc phải có kiểu trả về.</td></tr>
<tr><td>Constructor được gọi một cách ngầm định (implicitly).</td><td>Method được gọi một cách tường minh (explicitly).</td></tr>
<tr><td>Trình biên dịch (Compiler) cung cấp một constructor mặc định nếu bạn không định nghĩa bất kỳ constructor nào.</td><td>Method không bao giờ được cung cấp bởi trình biên dịch.</td></tr>
<tr><td>Tên constructor phải giống hệt với tên class.</td><td> Tên method có thể giống hoặc khác với tên class.</td></tr>
</tbody></table>

## Các loại Kế thừa (Hỗ trợ thông qua Class)

![single inheritance](https://user-images.githubusercontent.com/2780145/34364364-40b6b646-eaab-11e7-8c92-2c4cd9d0b2ca.png)

## Các loại Kế thừa (Chỉ hỗ trợ thông qua Interface)

![multiple inheritance](https://user-images.githubusercontent.com/2780145/34364363-407486b8-eaab-11e7-94e2-5c1876f414d3.png)

## Association vs Aggregation vs Composition

![association-aggregation-composition](https://user-images.githubusercontent.com/2780145/34364371-5db00694-eaab-11e7-8ef2-bf56d3394f15.png)

## Aggregation vs Composition

<table class="alt">
<tbody><tr><th>Aggregation (Tập hợp)</th><th>Composition (Thành phần)</th></tr>
<tr><td>Aggregation là một Association yếu.</td><td>Composition là một Association mạnh.</td></tr>
<tr><td>Class có thể tồn tại độc lập mà không cần owner (chủ sở hữu).</td><td>Class không thể tồn tại một cách có ý nghĩa nếu không có owner.</td></tr>
<tr><td>Có Life Time (Vòng đời) riêng.</td><td>Life Time phụ thuộc vào Owner.</td></tr>
<tr><td>A sử dụng B (A uses B).</td><td>A sở hữu B (A owns B).</td></tr>
<tr><td>Child không thuộc quyền sở hữu của 1 owner duy nhất.</td><td>Child chỉ có thể có 1 owner.</td></tr>
<tr><td>Mối quan hệ Has-A (Có một). A có B.</td><td>Mối quan hệ Part-Of (Là một phần của). B là một phần của A.</td></tr>
<tr><td>Được ký hiệu bằng một hình thoi rỗng trong UML.</td><td>Được ký hiệu bằng một hình thoi đặc trong UML.</td></tr>
<tr><td>Chúng ta không dùng từ khóa "final" cho Aggregation.</td><td>Từ khóa "final" được sử dụng để đại diện cho Composition.</td></tr>
<tr><td>Ví dụ:<br>- Xe hơi (Car) có Tài xế (Driver).<br>- Con người (Human) sử dụng Quần áo (Clothes).<br>- Công ty (Company) là tập hợp của Con người (People).<br>- Text Editor sử dụng một File.<br>- Mobile có một thẻ SIM.</td><td>Ví dụ:<br>- Động cơ (Engine) là một phần của Xe hơi (Car).<br>- Con người (Human) sở hữu Trái tim (Heart).<br>- Công ty (Company) là thành phần cấu tạo từ các Tài khoản (Accounts).<br>- Text Editor sở hữu một Buffer.<br>- Số IMEI là một phần của Mobile.</td></tr>
</tbody></table>

LƯU Ý : Từ khóa "final" được sử dụng trong Composition để đảm bảo biến con (child variable) được khởi tạo.

## Polymorphism - Method Overloading vs Method Overriding

<table class="alt">
<tbody><tr><th>Nạp chồng phương thức (Method Overloading) </th><th>Ghi đè phương thức (Method Overriding)</th></tr>
<tr><td>Method overloading được sử dụng <em>để tăng tính dễ đọc (readability)</em> của chương trình.</td><td>Method overriding được sử dụng <em>để cung cấp cách triển khai (implementation) cụ thể</em> của phương thức đã được cung cấp sẵn bởi super class của nó.</td></tr>
<tr><td>Method overloading được thực hiện <em>trong cùng một class</em>.</td><td>Method overriding xảy ra <em>giữa hai class</em> có mối quan hệ IS-A (kế thừa).</td></tr>
<tr><td>Trong trường hợp method overloading, <em>tham số (parameter) bắt buộc phải khác nhau</em>.</td><td>Trong trường hợp method overriding, <em>tham số (parameter) bắt buộc phải giống nhau</em>.</td></tr>
<tr><td>Method overloading là ví dụ về <em>compile time polymorphism (đa hình lúc biên dịch)</em>.</td><td>Method overriding là ví dụ về <em>run time polymorphism (đa hình lúc chạy)</em>.</td></tr>
<tr><td>Trong Java, method overloading không thể thực hiện bằng cách chỉ thay đổi kiểu trả về của method. <em>Kiểu trả về có thể giống/khác nhau</em> trong overloading, nhưng bạn bắt buộc phải thay đổi tham số.</td><td><em>Kiểu trả về bắt buộc phải giống nhau hoặc covariant (thay đổi kiểu trả về thành kiểu subclass)</em> trong method overriding.</td></tr>
</tbody></table>

## Abstract Class vs Interface

<table class="alt">
<tbody><tr><th>Lớp trừu tượng (Abstract class)</th><th>Interface</th></tr>
<tr><td>Abstract class có thể <strong>có cả abstract và non-abstract</strong> methods.</td><td>Interface <strong>chỉ có thể có abstract</strong> methods. Kể từ Java 8, nó cũng có thể có thêm các <strong>default & static methods</strong>.</td></tr>
<tr><td>Abstract class <strong>không hỗ trợ đa kế thừa (multiple inheritance)</strong>.</td><td>Interface <strong>có hỗ trợ đa kế thừa</strong>.</td></tr>
<tr><td>Abstract class <strong>có thể chứa biến final, non-final, static và non-static</strong>.</td><td>Interface <strong>chỉ chứa biến static và final</strong>.</td></tr>
<tr><td>Abstract class <strong>có thể cung cấp implementation cho interface</strong>.</td><td>Interface <strong>không thể cung cấp implementation cho abstract class</strong>.</td></tr>
<tr><td>Từ khóa <strong>abstract</strong> được dùng để khai báo abstract class.</td><td>Từ khóa <strong>interface</strong> được dùng để khai báo interface.</td></tr>
<tr><td><strong>Ví dụ:</strong><br> public abstract class Shape{<br>public abstract void draw();}</td><td><strong>Ví dụ:</strong><br> public interface Drawable{<br>void draw();}</td></tr>
</tbody></table>

## Java Access Modifiers (Phạm vi truy cập)

<table class="alt">
<tbody><tr><th>Access Modifier</th><th>trong cùng class (within class)</th><th>trong cùng package (within package)</th><th>ngoài package bởi subclass (outside package by subclass only)</th><th>ngoài package (outside package)</th></tr>
<tr><td><b>Private</b></td><td>Y</td><td>N</td><td>N</td><td>N</td></tr>
<tr><td><b>Default</b></td><td>Y</td><td>Y</td><td>N</td><td>N</td></tr>
<tr><td><b>Protected</b></td><td>Y</td><td>Y</td><td>Y</td><td>N</td></tr>
<tr><td><b>Public</b></td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr>
</tbody></table>

## Abstraction vs Encapsulation

<table class="alt">
<tbody><tr><th>Tính Trừu tượng (Abstraction)</th><th>Tính Đóng gói (Encapsulation)</th></tr>
<tr><td>Abstraction là quá trình che giấu các chi tiết triển khai (implementation details) và chỉ hiển thị chức năng cho người dùng.</td>
<td> Encapsulation là quá trình gói gọn code và dữ liệu vào trong một đơn vị duy nhất (single unit).</td></tr>
<tr><td>Abstraction cho phép bạn tập trung vào những gì đối tượng thực hiện thay vì cách thức nó thực hiện điều đó.</td>
<td>Encapsulation cung cấp cho bạn quyền kiểm soát đối với dữ liệu và giữ cho nó an toàn khỏi việc bị lạm dụng từ bên ngoài.</td></tr>
<tr><td>Abstraction giải quyết vấn đề ở Cấp độ Thiết kế (Design Level).</td>
<td>Encapsulation giải quyết vấn đề ở Cấp độ Triển khai (Implementation Level).</td></tr>
<tr><td>Abstraction được triển khai bằng cách sử dụng các Interfaces và Abstract Classes.</td>
<td>Encapsulation được triển khai bằng cách sử dụng các Access Modifiers (private, default, protected, public).</td></tr>
<tr><td>Abstraction nghĩa là che giấu sự phức tạp của quá trình triển khai bằng cách sử dụng interfaces và abstract class.</td>
<td>Encapsulation nghĩa là che giấu dữ liệu bằng cách sử dụng setters và getters.</td></tr>
</tbody></table>

## Các Phương thức của Object Class
Object class mặc định là class cha (parent class) của tất cả các class trong Java.

<table class="alt">
<tbody><tr><th>Phương thức (Method)</th><th>Mô tả (Description)</th></tr>
<tr><td>public final Class getClass()</td><td>trả về Class class object của đối tượng này. Class class sau đó có thể được sử dụng để lấy siêu dữ liệu (metadata) của class này.</td></tr>
<tr><td>public int hashCode()</td><td> trả về số hashcode cho đối tượng này.</td></tr>
<tr><td>public boolean equals(Object obj)</td><td> so sánh đối tượng được cung cấp với đối tượng hiện tại.</td></tr>
<tr><td>protected Object clone() throws CloneNotSupportedException</td><td> tạo và trả về bản sao chính xác (clone) của đối tượng này.</td></tr>
<tr><td>public String toString()</td><td> trả về chuỗi biểu diễn (string representation) của đối tượng này.</td></tr>
<tr><td>public final void notify()</td><td> đánh thức một thread (luồng) đang chờ trên monitor của đối tượng này.</td></tr>
<tr><td>public final void notifyAll()</td><td> đánh thức tất cả các threads đang chờ trên monitor của đối tượng này.</td></tr>
<tr><td>public final void wait(long timeout)throws InterruptedException</td><td> làm cho luồng hiện tại chờ trong một số mili-giây được chỉ định, cho đến khi một thread khác thông báo (gọi hàm notify() hoặc notifyAll()).</td></tr>
<tr><td>public final void wait(long timeout,int nanos)throws InterruptedException</td><td>làm cho luồng hiện tại chờ trong một số mili-giây và nano-giây được chỉ định, cho đến khi một thread khác thông báo (gọi hàm notify() hoặc notifyAll()).</td></tr>
<tr><td>public final void wait()throws InterruptedException</td><td> làm cho luồng hiện tại chờ, cho đến khi một thread khác thông báo (gọi hàm notify() hoặc notifyAll()).</td></tr>
<tr><td>protected void finalize()throws Throwable</td><td> được gọi bởi bộ thu gom rác (garbage collector) trước khi đối tượng bị dọn dẹp.</td></tr>
</tbody></table>
