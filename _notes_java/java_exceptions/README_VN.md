# Exception Handling (Xử lý Ngoại lệ) trong Java

Ngoại lệ (Exception) là một sự kiện làm gián đoạn luồng thực thi bình thường của chương trình. Nó là một đối tượng được ném ra (thrown) tại thời điểm chạy (runtime). Exception handling trong Java là một trong những cơ chế mạnh mẽ nhằm xử lý các lỗi runtime để luồng hoạt động bình thường của ứng dụng có thể được duy trì.
- Một Lỗi (Error) "chỉ ra những vấn đề nghiêm trọng mà một ứng dụng hợp lý không nên cố gắng để catch (bắt) lấy."
- Một Ngoại lệ (Exception) "chỉ ra những điều kiện mà một ứng dụng hợp lý có thể muốn catch lấy."

## Sơ đồ Phân cấp của Class Throwable :

![Throwable Hierarchy](https://user-images.githubusercontent.com/2780145/34899994-64c3ea52-f822-11e7-866e-71d232a40546.png)

## Các loại Exceptions :

**1. Checked Exception -** Checked exception là loại exception xảy ra tại thời điểm biên dịch (compile time), chúng cũng được gọi là các compile time exceptions. Các exceptions này không thể đơn giản bị phớt lờ tại thời điểm biên dịch, lập trình viên nên chú ý (xử lý) những exceptions này. vd. IOException, SQLException, ClassNotFoundException, CloneNotSupported, v.v. Các checked exceptions được kiểm tra tại compile-time.

**2. Unchecked Exception -** Unchecked exception là loại exception xảy ra tại thời điểm thực thi (execution). Chúng còn được gọi là các Runtime Exceptions. Chúng bao gồm các lỗi lập trình (programming bugs), chẳng hạn như lỗi logic hoặc sử dụng sai cách một API. vd. ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException, v.v. Unchecked exceptions không được kiểm tra tại compile-time, thay vào đó chúng được kiểm tra tại runtime.

**3. Error -** Đây hoàn toàn không phải là các exceptions, mà là những sự cố phát sinh ngoài tầm kiểm soát của người dùng hoặc lập trình viên. Các Errors thường bị bỏ qua trong code của bạn bởi vì bạn hiếm khi có thể làm gì để khắc phục một error. Giả sử, nếu xảy ra tình trạng tràn bộ nhớ stack (stack overflow), một error sẽ phát sinh. vd. OutOfMemoryError, VirtualMachineError, AssertionError, v.v.

## Các Tình huống Ví dụ về Exception :

**ArithmeticException**
```java
int a = 50/0; //ArithmeticException
```

**NullPointerException**
```java
String s = null;  
System.out.println(s.length());//NullPointerException
```

**NumberFormatException**
```java
String s = "abc";  
int i = Integer.parseInt(s);//NumberFormatException  
```

**ArrayIndexOutOfBoundsException**
```java
int a[] = new int[5];  
a[10] = 50; //ArrayIndexOutOfBoundsException  
```

## Các Từ khóa cho Exception Handling trong Java :

**1. try -** Khối try (try block) trong Java được sử dụng để bao bọc phần mã có khả năng ném ra một exception. Nó bắt buộc phải được sử dụng bên trong phương thức (method). Khối try phải được theo sau bởi khối catch hoặc khối finally.

**2. catch -** Khối catch trong Java được sử dụng để xử lý Exception. Nó chỉ có thể được sử dụng sau khối try. Bạn có thể sử dụng nhiều khối catch với một khối try duy nhất.

**3. finally -** Khối finally trong Java là khối được sử dụng để thực thi các phần mã quan trọng như đóng kết nối (closing connection), stream, v.v. Khối finally trong Java luôn luôn được thực thi bất kể exception có được xử lý hay không. Khối finally tuân theo sau khối try hoặc catch.

**4. throw -** Từ khóa throw trong Java được sử dụng để ném ra một exception một cách tường minh (explicitly). Chúng ta có thể ném ra checked hoặc uncheked exception bằng từ khóa throw. Từ khóa throw chủ yếu được sử dụng để ném các custom exception (ngoại lệ tùy chỉnh).

**5. throws -** Từ khóa throws trong Java được dùng để khai báo (declare) một exception. Nó cung cấp thông tin cho lập trình viên rằng có thể có một exception xảy ra, vì vậy tốt hơn là lập trình viên nên cung cấp mã xử lý exception.

**LƯU Ý :** Exception Handling chủ yếu được dùng để xử lý các checked exceptions. Nếu có bất kỳ unchecked exception nào xảy ra như NullPointerException, đó là lỗi của lập trình viên vì họ không thực hiện việc kiểm tra trước khi đoạn mã đó được đưa vào sử dụng.

## Trình Xử lý Exception Mặc định của JVM (JVM's Default Exception Handler)

JVM trước tiên kiểm tra xem exception đã được xử lý hay chưa. Nếu exception chưa được xử lý, JVM cung cấp một trình xử lý exception mặc định thực hiện các nhiệm vụ sau:

- In ra phần mô tả exception.
- In ra stack trace (Sơ đồ phân cấp các phương thức nơi exception đó đã xảy ra).
- Gây ra tình trạng kết thúc (terminate) chương trình.

Nhưng nếu exception được xử lý bởi nhà phát triển ứng dụng (application programmer), luồng hoạt động bình thường của ứng dụng sẽ được duy trì, nghĩa là phần mã còn lại sẽ được tiếp tục thực thi.

## Sử dụng Nhiều khối catch (Multiple catch blocks)

- Nếu method của superclass khai báo một exception, method bị ghi đè (overridden) ở subclass có thể khai báo exception tương tự, exception thuộc loại subclass đó hoặc không khai báo exception, nhưng không thể khai báo exception của lớp cha (parent exception).

- Tất cả các khối catch phải được sắp xếp theo thứ tự từ cụ thể nhất (most specific) đến tổng quát nhất (most general), ví dụ: catch cho ArithmeticException phải đặt trước catch cho Exception.

## Sử dụng khối finally

- Nếu bạn không xử lý exception, trước khi kết thúc chương trình, JVM vẫn sẽ thực thi khối finally (nếu có).

- Đối với mỗi khối try có thể có không hoặc nhiều khối catch, nhưng chỉ có thể có duy nhất một khối finally.

- Khối finally sẽ không được thực thi nếu chương trình bị thoát (hoặc do gọi hàm System.exit() hoặc do gây ra lỗi nghiêm trọng fatal error khiến tiến trình bị hủy).

## Sự truyền Exception (Execution Propagation)

Một exception trước tiên được ném từ đỉnh của ngăn xếp (top of the stack) và nếu nó không được caught (bắt), nó sẽ rơi xuống các phương thức gọi nó trước đó trong call stack. Nếu không được caught ở đó, exception lại tiếp tục rơi xuống phương thức trước đó, và cứ thế cho đến khi chúng được caught hoặc cho đến khi chúng chạm đáy của call stack. Quá trình này được gọi là exception propagation.

- Theo mặc định, Unchecked Exceptions được truyền lên (forwarded) trong chuỗi các hàm gọi (propagated).

- Theo mặc định, Checked Exceptions không được truyền lên (forwarded) trong chuỗi các hàm gọi (propagated).

## Sử dụng từ khóa throws

*Chỉ có các **Checked exception** mới nên được khai báo*, bởi vì **Unchecked Exception** là thứ nằm dưới quyền kiểm soát của bạn (vì vậy hãy sửa lại code) Và **Errors** là thứ nằm ngoài tầm kiểm soát của bạn.

**Ưu điểm (Advantage) :** Bằng cách sử dụng từ khóa throws, Checked Exception có thể được propagate (đẩy ngược lên trong call stack). Nó cung cấp thông tin cho nơi gọi hàm (caller) về exception đó.

Nếu bạn đang gọi một hàm có khai báo ném exception, bạn phải tự mình caught (bắt) hoặc declare (khai báo lại) exception đó.

1. Bạn caught exception, tức là xử lý exception bằng try/catch.
- code sẽ được thực thi ổn định bất kể exception có xảy ra trong suốt chương trình hay không.

2. Bạn declare exception, tức là tiếp tục chỉ định throws kèm với method của bạn.
- nếu exception không xảy ra, code sẽ được thực thi bình thường.
- nếu exception xảy ra, một exception sẽ bị ném ra tại runtime bởi vì throws không hề xử lý exception.

Bạn có thể rethrow (ném lại) một exception bằng cách ném chính exception đó bên trong khối catch.

## Từ khóa throw vs throws trong Java

<table class="alt">
<tbody><tr><th>STT</th><th>throw</th><th>throws</th></tr>
<tr><td>1)</td><td>Từ khóa throw trong Java được dùng để ném tường minh một exception.</td><td>Từ khóa throws trong Java được dùng để khai báo một exception.</td></tr>
<tr><td>2)</td><td>Checked exception không thể được propagated nếu chỉ dùng throw.</td><td>Checked exception có thể được propagated bằng throws.</td></tr>
<tr><td>3)</td><td>Throw được theo sau bởi một thực thể (instance).</td><td>Throws được theo sau bởi một lớp (class).</td></tr>
<tr><td>4)</td><td>Throw được dùng ở bên trong method.</td><td>Throws được dùng đi kèm với chữ ký (signature) của method.</td></tr>
<tr><td>5)</td><td>Bạn không thể ném nhiều exceptions.</td><td>Bạn có thể khai báo nhiều exceptions vd.<br> public void method()throws IOException,SQLException.</td></tr>
</tbody></table>

## final vs finally vs finalize trong Java

<table class="alt">
<tbody><tr><th>STT</th><th>final</th><th>finally</th><th>finalize</th></tr>
<tr><td>1)</td><td>Final được dùng để áp đặt các hạn chế lên class, method và biến. Class final không thể bị kế thừa, method final không thể bị ghi đè và giá trị của biến final không thể bị thay đổi.</td><td>Finally được dùng để đặt các đoạn mã quan trọng, nó sẽ được thực thi dù exception có được xử lý hay không.</td><td>Finalize được dùng để thực hiện quá trình dọn dẹp ngay trước khi đối tượng bị thu gom rác (garbage collected). </td></tr>
<tr><td>2)</td><td>Final là một keyword (từ khóa).</td><td>Finally là một block (khối).</td><td>Finalize là một method (phương thức).</td></tr>
</tbody></table>

## Exception Handling kết hợp với Method Overriding :

- Nếu method của superclass không khai báo exception nào, thì method bị ghi đè ở subclass không được phép khai báo checked exception nhưng có thể khai báo unchecked exception.

- Nếu method của superclass có khai báo exception, method bị ghi đè ở subclass có thể khai báo cùng loại, khai báo exception con (subclass exception) hoặc không khai báo exception nào, nhưng không được phép khai báo exception cha (parent exception).

## Custom Exception (Ngoại lệ tùy chỉnh) trong Java :

Nếu bạn tự tạo ra Exception của riêng mình thì đó được gọi là custom exception hoặc user-defined exception. Custom exceptions trong Java được dùng để tùy biến exception theo nhu cầu của người dùng.

Nhờ có custom exception, bạn có thể tạo riêng exception và thông báo (message) của chính mình.
