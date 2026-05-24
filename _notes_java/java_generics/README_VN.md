# Generics trong Java

## Các Lớp Generic (Generic Classes)

Khai báo một generic class trông giống như khai báo một class thông thường (non-generic), ngoại trừ việc tên class được theo sau bởi một phần tham số kiểu (type parameter section).

Phần tham số kiểu của một generic class có thể có một hoặc nhiều tham số kiểu được phân tách bằng dấu phẩy. Các class này được gọi là các lớp tham số hóa (parameterized classes) hoặc kiểu tham số hóa (parameterized types) vì chúng chấp nhận một hoặc nhiều tham số.

**Cú pháp:**
```java
public class Box<T> {
   private T t;
}
```

<ul class="list">
<li><p><b>Box</b> − Box là một generic class.</p></li>
<li><p><b>T</b> − Tham số kiểu generic được truyền vào generic class. Nó có thể nhận bất kỳ Object nào.</p></li>
<li><p><b>t</b> − Thực thể (Instance) của kiểu generic T.</p></li>
</ul>

## Các Quy ước Đặt tên (Naming Conventions)

Theo quy ước, tên tham số kiểu được đặt dưới dạng các chữ cái in hoa, đơn lẻ để tham số kiểu có thể được phân biệt dễ dàng với tên class hoặc interface thông thường. Dưới đây là danh sách các tên tham số kiểu thường dùng −

<ul class="list">
<li><p><b>E</b> − Element (chủ yếu được dùng bởi Java Collections framework)</p></li>
<li><p><b>K</b> − Key (chủ yếu được dùng để biểu diễn key của một map)</p></li>
<li><p><b>V</b> − Value (chủ yếu được dùng để biểu diễn value của một map)</p></li>
<li><p><b>N</b> − Number (biểu diễn các con số)</p></li>
<li><p><b>T</b> − Type (biểu diễn tham số kiểu generic đầu tiên)</p></li>
<li><p><b>S, U, V, v.v.</b> − Các kiểu thứ 2, 3, 4</p></li>
</ul>

## Suy luận Kiểu (Type Inference)

Type inference đại diện cho khả năng của trình biên dịch Java trong việc xem xét một lệnh gọi phương thức và phần khai báo tương ứng của nó để kiểm tra và xác định (các) đối số kiểu (type argument). Thuật toán suy luận kiểm tra các kiểu của đối số và, nếu có, kiểu được gán sẽ được trả về. Các thuật toán suy luận cố gắng tìm ra một kiểu cụ thể có thể đáp ứng được tất cả các tham số kiểu.

Trình biên dịch sẽ tạo ra cảnh báo chuyển đổi không được kiểm tra (unchecked conversion warning) trong trường hợp type inference không được sử dụng.

**Cú pháp:**
```java
Box<Integer> integerBox = new Box<>();
```

<ul class="list">
<li><p><b>Box</b> − Box là một generic class.</p></li>
<li><p><b><></b> − Toán tử kim cương (diamond operator) biểu thị cho type inference.</p></li>
</ul>

Sử dụng toán tử kim cương, trình biên dịch sẽ xác định kiểu của tham số. Toán tử này khả dụng từ phiên bản Java SE 7 trở đi.

## Generic Methods (Phương thức Generic)

Bạn có thể viết một phần khai báo generic method duy nhất nhưng có thể được gọi với các đối số thuộc nhiều kiểu khác nhau. Dựa trên các kiểu của đối số được truyền vào generic method, trình biên dịch sẽ xử lý mỗi lời gọi hàm một cách thích hợp. Dưới đây là các quy tắc để định nghĩa Generic Methods −

<ul class="list">
<li><p>Tất cả các khai báo generic method đều có một phần tham số kiểu được bao quanh bởi các dấu ngoặc nhọn (< và >) nằm trước kiểu trả về của method ( < E > trong ví dụ tiếp theo).</p></li>
<li><p>Mỗi phần tham số kiểu chứa một hoặc nhiều tham số kiểu được phân tách bằng dấu phẩy. Một tham số kiểu, hay còn gọi là biến kiểu (type variable), là một định danh chỉ định tên kiểu generic.</p></li>
<li><p>Các tham số kiểu có thể được sử dụng để khai báo kiểu trả về và đóng vai trò như các trình giữ chỗ (placeholders) cho các kiểu của đối số truyền vào generic method, chúng được gọi là các đối số kiểu thực tế (actual type arguments).</p></li>
<li><p>Phần thân (body) của một generic method được khai báo giống như bất kỳ method nào khác. Lưu ý rằng các tham số kiểu chỉ có thể đại diện cho các kiểu tham chiếu (reference types), không phải là các kiểu nguyên thủy (primitive types như int, double và char).</p></li>
</ul>

```java
public static <E> void printArray( E[] inputArray ) {
      // Hiển thị các phần tử của mảng
      for(E element : inputArray) {
         System.out.printf("%s ", element);
      }
      System.out.println();
   }
```

## Nhiều Tham số Kiểu (Multiple Type Parameters)

Một Generic class có thể có nhiều tham số kiểu. Ví dụ sau đây sẽ minh họa cho khái niệm được đề cập ở trên.

```java
public class Box<S,T> {
   private T t;
   private S s;
}
```

## Các Kiểu Tham số hóa (Parameterized Types)

Một Generic class có thể có các parameterized types, nơi mà một tham số kiểu có thể được thay thế bằng một parameterized type. 
Parameterized Types là những kiểu nhận các kiểu khác làm tham số. Vd - Collection<String>, ArrayList<String>, v.v.
  
```java
public class Box<S,T> {
   ...
}
...
Box<Integer, List<String>> box = new Box<Integer, List<String>>(); //Parameterized Types
...
```

## Raw Types

Một raw type là một đối tượng của một generic class hoặc interface nếu các đối số kiểu của nó không được truyền vào trong quá trình nó được tạo ra.

```java
Box rawBox = new Box();
```

## Bounded Type Parameters (Tham số Kiểu có Giới hạn)

Sẽ có lúc bạn muốn giới hạn các loại kiểu được phép truyền vào một tham số kiểu. Ví dụ, một phương thức hoạt động trên các con số (numbers) có thể chỉ muốn chấp nhận các instances của class Number hoặc các subclasses của nó. Đó là mục đích sử dụng của bounded type parameters.

Để khai báo một bounded type parameter, liệt kê tên của tham số kiểu, tiếp theo là từ khóa extends, và cuối cùng là giới hạn trên (upper bound) của nó.

**Giới hạn Đơn (Single Bound):**
```java
public static <T extends Comparable<T>> T maximum(T x, T y, T z)
```

**Nhiều Giới hạn (Multiple Bounds):**
```java
public static <T extends Number & Comparable<T>> T maximum(T x, T y, T z)
```
<ul class="list">
<li><p><b>maximum</b> − maximum là một generic method.</p></li>
<li><p><b>T</b> − Tham số kiểu generic được truyền vào generic method. Nó có thể nhận bất kỳ Object nào.</p></li>
</ul>

T là một tham số kiểu truyền vào generic class Box và bắt buộc phải là subtype của class Number đồng thời phải implements interface Comparable. Trong trường hợp có cả class được truyền vào dưới dạng bound, nó phải được đặt lên trước interface nếu không sẽ xảy ra lỗi khi biên dịch (compile time error).

**Ví dụ khi gọi:**
```java
maximum( 6.6, 8.8, 7.7 )
```

## Ví dụ về Collections Framework

Java đã cung cấp hỗ trợ generic bên trong các Collections Framework Interfaces như List, Set, Map, v.v.

### List

```java
List<T> list = new ArrayList<T>();
```
<ul class="list">
<li><p><b>list</b> − object của interface List.</p></li>
<li><p><b>T</b> − Tham số kiểu generic truyền vào trong quá trình khai báo List.</p></li>
</ul>
T là tham số kiểu truyền vào cho generic interface List và implementation class của nó là ArrayList.

### Set

```java
Set<T> set = new HashSet<T>();
```
<ul class="list">
<li><p><b>set</b> − object của interface Set.</p></li>
<li><p><b>T</b> − Tham số kiểu generic truyền vào trong quá trình khai báo Set.</p></li>
</ul>
T là tham số kiểu truyền vào cho generic interface Set và implementation class của nó là HashSet.

### Map
```java
Map<T> set = new HashMap<T>();
```
<ul class="list">
<li><p><b>set</b> − object của interface Map.</p></li>
<li><p><b>T</b> − Tham số kiểu generic truyền vào trong quá trình khai báo Map.</p></li>
</ul>
T là tham số kiểu truyền vào cho generic interface Map và implementation class của nó là HashMap.

## Wildcards trong Generics

Dấu chấm hỏi (?), đại diện cho wildcard, mang ý nghĩa là một kiểu chưa xác định (unknown type) trong generics. 

### Upper Bounded Wildcards (Wildcards Giới hạn Trên)

Sẽ có lúc bạn muốn giới hạn các loại kiểu được phép truyền vào một tham số kiểu. Ví dụ, một phương thức hoạt động trên các con số có thể chỉ muốn chấp nhận các instances của class Number hoặc các subclasses của nó.

Để khai báo một tham số Upper Bounded Wildcard, viết ký tự ?, tiếp theo là từ khóa extends, và cuối cùng là upper bound của nó.
```java
public static double sum(List<? extends Number> numberlist) {
      ...
   }
```

### Unbounded Wildcards (Wildcards Không Giới hạn)

Sẽ có những lúc bất kỳ đối tượng nào cũng có thể được sử dụng, đó là khi một phương thức có thể được triển khai bằng chức năng cung cấp sẵn trong class Object hoặc Khi mã code hoạt động độc lập với tham số kiểu.

Để khai báo một tham số Unbounded Wildcard, chỉ cần viết ký tự ?.
```java
public static void printAll(List<?> list) {
    ...
   }
```

### Lower Bounded Wildcards (Wildcards Giới hạn Dưới)

Sẽ có lúc bạn muốn giới hạn các loại kiểu được phép truyền vào một tham số kiểu. Ví dụ, một phương thức hoạt động trên các con số có thể chỉ muốn chấp nhận các instances của class Integer hoặc các superclasses của nó như Number.

Để khai báo một tham số Lower Bounded Wildcard, viết ký tự ?, tiếp theo là từ khóa super, và cuối cùng là giới hạn dưới (lower bound) của nó.
```java
public static void addCat(List<? super Cat> catList) {
      ...
   }
...
//Bạn có thể thêm list của Cat hoặc Animal (super class của class Cat)
addCat(animalList);
addCat(catList);
```

## Xóa Kiểu (Type Erasure)

Generics được sử dụng nhằm mục đích kiểm tra kiểu chặt chẽ hơn tại compile time và cung cấp khả năng lập trình generic. Để triển khai generic behaviour, trình biên dịch Java áp dụng type erasure (xóa kiểu). Type erasure là một quá trình trong đó trình biên dịch thay thế một generic parameter bằng class thực tế hoặc cầu nối phương thức (bridge method). Trong quá trình type erasure, trình biên dịch đảm bảo rằng không có thêm bất kỳ class thừa nào được tạo ra và không có chi phí gia tăng (overhead) khi runtime.

**Các quy tắc của Type Erasure:**
<ul class="list">
<li><p>Thay thế các tham số kiểu trong generic type bằng bound (giới hạn) của chúng nếu bounded type parameters được sử dụng.</p></li>
<li><p>Thay thế các tham số kiểu trong generic type bằng Object nếu unbounded type parameters được sử dụng.</p></li>
<li><p>Chèn các phép ép kiểu (type casts) để duy trì tính an toàn kiểu (type safety).</p></li>
<li><p>Tạo ra các bridge methods để giữ lại tính đa hình (polymorphism) trong các extended generic types.</p></li>
</ul>

## Những Hạn chế đối với Generics

**Không Dùng cho Kiểu Nguyên thủy (No Primitive Types)** - Khi dùng generics, các primitive types không thể được truyền vào như tham số kiểu.
```java
Box<int> intBox = new Box<int>() //Lỗi
```   
LƯU Ý: Hãy sử dụng các Wrappers như Integer thay thế.

**Không Thể Khởi tạo Instance (No Instance)** - Một tham số kiểu không thể được sử dụng để khởi tạo đối tượng của nó bên trong một method.
```java
public static <T> void add(Box<T> box) //Lỗi
```   
LƯU Ý: Để đạt được chức năng này, có thể sử dụng reflection.

**Không Có Trường tĩnh (No Static field)** - Khi sử dụng generics, các tham số kiểu không được phép khai báo là static. Vì biến static được chia sẻ chung giữa các object nên trình biên dịch không thể xác định loại kiểu nào sẽ được sử dụng.
```java
class Box<T> {   
   private static T t; //Lỗi
}
```   

**Không Được Ép kiểu (No Cast)** - Không được phép ép kiểu (casting) sang một parameterized type trừ khi nó được parameterized bởi unbounded wildcards.

```java
Box<Integer> integerBox = new Box<Integer>();
Box<Number> numberBox = new Box<Number>();
integerBox = (Box<Integer>)numberBox; //Lỗi: Cannot cast from Box<Number> to Box<Integer>
```
LƯU Ý: Để đạt được điều tương tự, có thể sử dụng unbounded wildcards.

**Không Được Dùng instanceOf (No instanceOf)** - Bởi vì trình biên dịch sử dụng type erasure, quá trình runtime không tiếp tục theo dõi các tham số kiểu, vì vậy tại thời điểm runtime, sự khác biệt giữa Box<Integer> và Box<String> không thể được kiểm chứng bằng toán tử instanceOf.

```java
... integerBox instanceof Box<Integer> ... 
```

**Không Có Mảng (No Array)** - Các mảng (arrays) của các parameterized types không được cho phép. Bởi vì trình biên dịch sử dụng type erasure, tham số kiểu bị thay thế thành Object và người dùng có thể ném bất kỳ loại object nào vào mảng. Và tại lúc runtime, code sẽ không thể ném ra ArrayStoreException.

```java
Object[] stringBoxes = new Box<String>[]; //Lỗi
```

**Không Có Ngoại lệ (No Exception)** - Một generic class không được phép kế thừa (extend) class Throwable dù là trực tiếp hay gián tiếp. 

```java
//Generic class Box<T> không được làm subclass của java.lang.Throwable
class Box<T> extends Exception {}
class Box1<T> extends Throwable {}
```
Một phương thức không được phép bắt (catch) một instance của tham số kiểu. 
```java
... catch (T e) ...
```

**Không Nạp chồng (No Overload)** - Một class không được phép có hai overloaded methods mà chúng có thể sở hữu cùng một chữ ký (signature) sau quá trình type erasure.
```java
...
public void print(List<String> stringList) { }  // Lỗi
public void print(List<Integer> integerList) { }
```
