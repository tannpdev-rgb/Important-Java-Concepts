# Tuần tự hóa (Serialization)

Tuần tự hóa (Serialization) trong java là một cơ chế ghi lại trạng thái của một đối tượng (object) thành một luồng byte (byte stream). Nó được sử dụng chủ yếu trong các công nghệ Hibernate, RMI, JPA, EJB và JMS. Thao tác ngược lại với serialization được gọi là giải tuần tự hóa (deserialization).

![serialization-deserialization](https://user-images.githubusercontent.com/2780145/147404916-d39d7897-6cf6-4451-9985-3c8d5502fc21.png)

**Ưu điểm của Java Serialization :**
Nó được sử dụng chủ yếu để truyền tải (travel) trạng thái của object qua lại trên mạng (còn được gọi là marshaling).

**Interface java.io.Serializable :**
Serializable là một marker interface (interface đánh dấu - không có thành viên dữ liệu hay phương thức nào). Nó được dùng để "đánh dấu" các lớp (classes) java để cho các objects của những lớp này có thể có được khả năng (capability) nhất định nào đó. Interface Cloneable và Remote cũng là các marker interfaces.

Nó bắt buộc phải được implement bởi class mà bạn muốn bảo lưu/lưu trữ (persist) object của class đó.

Class String và toàn bộ các wrapper classes mặc định đều implements interface java.io.Serializable.

## Lớp ObjectOutputStream 
Class ObjectOutputStream được sử dụng để ghi (write) các kiểu dữ liệu nguyên thủy (primitive data types) và các đối tượng Java (Java objects) vào trong một OutputStream. Chỉ những objects nào hỗ trợ interface java.io.Serializable mới có thể được ghi vào các luồng (streams).

**Hàm khởi tạo (Constructor) :**
```java
public ObjectOutputStream(OutputStream out) throws IOException {}
```
Hàm khởi tạo bên trên tạo ra một ObjectOutputStream để ghi vào trong luồng OutputStream đã được chỉ định.

**Các Phương thức Đặc thù (Important Methods) :**
<table class="alt">
<tbody><tr><th>Phương thức (Method)</th><th>Mô tả (Description)</th></tr>
<tr><td>1) public final void writeObject(Object obj) throws IOException {}</td><td>ghi object đã được chỉ định vào trong ObjectOutputStream.</td></tr>
<tr><td>2) public void flush() throws IOException {}</td><td>xả luồng (flushes) output stream hiện tại.</td></tr>
<tr><td>3) public void close() throws IOException {}</td><td>đóng output stream hiện tại.</td></tr>
</tbody></table>

## Ví dụ về Java Serialization
Ví dụ về việc tuần tự hóa (serialize) object của lớp Student.
```java
import java.io.*;  
class Persist{  
 public static void main(String args[])throws Exception{  
  Student s1 =new Student(211,"John");  
  
  FileOutputStream fout=new FileOutputStream("f.txt");  
  ObjectOutputStream out=new ObjectOutputStream(fout);  
  
  out.writeObject(s1);  
  out.flush();  
  System.out.println("success");  
 }  
}  
```

## Deserialization (Giải tuần tự hóa) trong java
Deserialization là quá trình tái cấu trúc lại object từ trạng thái đã được tuần tự hóa (serialized state). Nó là thao tác ngược lại của serialization.

## Lớp ObjectInputStream
ObjectInputStream có nhiệm vụ giải tuần tự hóa (deserializes) các objects và dữ liệu nguyên thủy đã được ghi thông qua ObjectOutputStream.

**Hàm khởi tạo (Constructor) :**
```java
public ObjectInputStream(InputStream in) throws IOException {}
```
Hàm khởi tạo bên trên tạo ra một ObjectInputStream đọc dữ liệu lấy từ luồng InputStream được chỉ định.

**Các Phương thức Đặc thù :**
<table class="alt">
<tbody><tr><th>Phương thức</th><th>Mô tả</th></tr>
<tr><td>1) public final Object readObject() throws IOException, ClassNotFoundException{}</td><td>đọc object lấy từ input stream. </td></tr>
<tr><td>2) public void close() throws IOException {}</td><td>đóng ObjectInputStream.</td></tr>
</tbody></table>

## Ví dụ về Java Deserialization
Ví dụ về việc giải tuần tự hóa (deserialize) object của class Student.
```java
import java.io.*;  
class Depersist{  
 public static void main(String args[])throws Exception{  
    
  ObjectInputStream in=new ObjectInputStream(new FileInputStream("f.txt"));  
  Student s=(Student)in.readObject();  
  System.out.println(s.id+" "+s.name);  
  
  in.close();  
 }  
}  
```

## Các Quy tắc về Tuần tự hóa (Serialization Rules)

**Serialization cùng Tính Kế thừa (Mối quan hệ IS-A) :**
Nếu một class implements serializable thì toàn bộ các lớp con (sub classes) của nó cũng sẽ mang tính chất serializable. Các thuộc tính (properties) của lớp cha được kế thừa truyền sang các sub classes cho nên lớp cha mang tính Serializable thì sub class cũng rứa.

**Serialization cùng Tính Tụ hợp (Mối quan hệ HAS-A) :**
Nếu một class có chứa tham chiếu (reference) tới một class khác, thì tất cả những references đó bắt buộc phải mang tính Serializable nếu không tiến trình serialization sẽ không được thực hiện. Trong trường hợp đó, lỗi NotSerializableException sẽ bị ném ra lúc chạy chương trình (runtime).

Tất cả các objects được đặt nằm bên trong một object bắt buộc phải mang tính Serializable.

**Serialization cùng với thành viên dữ liệu dạng tĩnh (static data member) :**
Giả sử có tồn tại bất kỳ biến dữ liệu tĩnh (static data member) nào nằm ở trong một class, nó sẽ không được đem đi tuần tự hóa (serialized) vì static thuộc về một phần của the class chứ không thuộc về object.

**Serialization đi liền cấu trúc mảng (array) hay danh sách tập hợp (collection) :**
Bên trong mảng hoặc cấu trúc tập hợp (collection), tất cả các objects của mảng hay của collection bắt buộc phải thỏa mãn tính serializable. Chỉ cần một object nằm ở trong bị khuyết thiếu tính năng này, việc tuần tự hóa serialization sẽ thất bại (failed).

## Interface Externalizable trong Java
Interface Externalizable cung cấp khả năng viết trạng thái (state) của một object ra dưới dạng luồng byte (byte stream) theo cấu trúc nén (compress format). Đây không phải marker interface (vì nó chứa method).

Interface Externalizable cung cấp 2 methods sau:
- public void writeExternal(ObjectOutput out) throws IOException
- public void readExternal(ObjectInput in) throws IOException

## Từ khóa Java Transient (Ngoại lệ Tuần tự hóa)
Nếu mà bạn không muốn tuần tự hóa một member (thành viên) lưu giữ data nào đó nằm ở class, cứ gán thẳng mác (mark) transient cho nó là xong.
**Ví dụ :**
```java
transient int age; //Trường này sẽ KHÔNG bao giờ bị serialized  
```
