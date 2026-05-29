# Few Things to Remember

## Definitions, Tips & Rules related to Java OOPS

### Class & Constructor

* *Một class trong Java có thể bao gồm: các thuộc tính (fields), phương thức (methods), hàm khởi tạo (constructors), các khối lệnh (blocks), class lồng nhau (nested class) và interface.*
* *Object (đối tượng) là một thực thể (instance) của một class.*
* *Constructor (hàm khởi tạo) trong Java là một loại phương thức đặc biệt được sử dụng để khởi tạo đối tượng.*
* *Nếu không có constructor nào trong một class, trình biên dịch sẽ tự động tạo một constructor mặc định (default constructor).*
* *Không có copy constructor (hàm khởi tạo sao chép) trong Java. Tuy nhiên, chúng ta có thể sao chép giá trị của một đối tượng sang một đối tượng khác tương tự như copy constructor trong C++.*
* *Một constructor có thể thực hiện các tác vụ khác ngoài việc khởi tạo, ví dụ như tạo đối tượng, khởi chạy một luồng (thread), gọi phương thức, v.v.*
* *Anh có thể thực hiện bất kỳ hoạt động nào trong constructor giống như thực hiện trong một phương thức thông thường.*

### static Keyword

* *Từ khóa static có thể được áp dụng cho: biến (biến class), phương thức (phương thức class), khối lệnh (static block) và class lồng nhau.*
* *Thuộc tính static trong Java được chia sẻ cho tất cả các đối tượng.*
* *Một phương thức static thuộc về class chứ không thuộc về đối tượng của class đó.*
* *Một phương thức static có thể được gọi mà không cần phải tạo thực thể của class.*
* *Một phương thức static có thể truy cập thành viên dữ liệu static và có thể thay đổi giá trị của nó.*
* *Phương thức static không thể sử dụng trực tiếp thành viên dữ liệu non-static hoặc gọi trực tiếp phương thức non-static.*
* *Từ khóa this và super không thể được sử dụng trong ngữ cảnh static (static context).*
* *Phương thức main là static vì JVM không cần đối tượng để gọi phương thức static. Nếu nó là phương thức non-static, JVM sẽ phải tạo đối tượng trước rồi mới gọi phương thức main(), điều này dẫn đến vấn đề cấp phát thêm bộ nhớ không cần thiết.*
* *Một khối lệnh static (static block) được sử dụng để khởi tạo thành viên dữ liệu static. Nó được thực thi trước phương thức main tại thời điểm nạp class (classloading).*

### this Keyword

* *Trong Java, this là một biến tham chiếu trỏ đến đối tượng hiện tại.*
* *Lời gọi đến this() phải là câu lệnh đầu tiên trong constructor.*
* *this có thể được sử dụng để: tham chiếu đến biến thực thể của class hiện tại, gọi phương thức và constructor của class hiện tại.*
* *this có thể được truyền như một đối số trong lời gọi phương thức và constructor.*
* *this có thể được sử dụng để trả về thực thể của class hiện tại từ một phương thức.*
* *Việc sử dụng tên biến có ý nghĩa là một cách tiếp cận tốt hơn. Vì vậy, trong thực tế chúng ta thường đặt tên biến thực thể và tham số giống nhau, và luôn sử dụng từ khóa this để phân biệt.*

### Inheritance

* *Kế thừa (quan hệ IS-A) là một cơ chế mà trong đó một đối tượng có được tất cả các thuộc tính và hành vi của đối tượng cha.*
* *Từ khóa extends chỉ ra rằng anh đang tạo một class mới kế thừa từ một class đã tồn tại.*
* *Đa kế thừa (Multiple inheritance) không được hỗ trợ trong Java thông qua class. Chúng ta có thể sử dụng Interface để thực hiện điều này.*
* *Để giảm bớt sự phức tạp và đơn giản hóa ngôn ngữ, đa kế thừa không được hỗ trợ trong Java.*
* *Nếu một class có chứa một tham chiếu đến một thực thể khác, nó được gọi là Aggregation (quan hệ kết tập - HAS-A).*
* *Kế thừa chỉ nên được sử dụng nếu quan hệ is-a được duy trì trong suốt vòng đời của các đối tượng liên quan; nếu không, kết tập (aggregation) là lựa chọn tốt nhất.*

### Method Overloading

* *Nếu một class có nhiều phương thức trùng tên nhưng khác nhau về tham số, nó được gọi là Method Overloading (Nạp chồng phương thức).*
* *Có hai cách để nạp chồng phương thức trong Java: thay đổi số lượng đối số, hoặc thay đổi kiểu dữ liệu của đối số.*
* *Trong Java, Method Overloading không thể thực hiện được nếu chỉ thay đổi kiểu trả về của phương thức vì sẽ gây ra sự mơ hồ (ambiguity).*
* *Lỗi lúc biên dịch (Compile Time Error) tốt hơn lỗi lúc chạy (Run Time Error). Vì vậy, trình biên dịch Java sẽ báo lỗi biên dịch nếu anh khai báo các phương thức giống nhau có cùng các tham số giống nhau.*
* *Chúng ta cũng có thể nạp chồng phương thức main() của Java, nhưng JVM sẽ chỉ gọi phương thức main() nhận mảng String làm đối số.*
* *Một kiểu dữ liệu sẽ tự động được ép kiểu lên (promoted) một cách ngầm định nếu không tìm thấy kiểu dữ liệu khớp chính xác. Ví dụ: byte có thể được nâng lên short, int, v.v.*
* *Nếu không có phương thức nào có kiểu đối số khớp chính xác, và mỗi phương thức lại ép kiểu lên một số lượng đối số tương đương, sẽ xảy ra sự mơ hồ.*
* *Một kiểu dữ liệu không tự động bị ép kiểu xuống (de-promoted) một cách ngầm định; ví dụ, kiểu double không thể tự động ép kiểu xuống bất kỳ kiểu nào khác một cách ngầm định.*

### Method Overriding

* *Nếu class con (subclass) có cùng một phương thức đã được khai báo trong class cha, nó được gọi là method overriding (Ghi đè phương thức).*
* *Phương thức được ghi đè phải có cùng tên và tham số như trong class cha.*
* *Method overriding được sử dụng để cung cấp cách triển khai cụ thể cho một phương thức đã được cung cấp bởi class siêu (super class) của nó. Nó cũng được sử dụng cho đa hình lúc chạy (runtime polymorphism).*
* *Chúng ta không thể ghi đè phương thức static (bao gồm cả phương thức main) vì phương thức static được gắn với class, trong khi phương thức thực thể (instance method) được gắn với đối tượng. Static thuộc về vùng nhớ class (class area) và instance thuộc về vùng nhớ heap (heap area).*
* *Ghi đè phương thức với Access Modifier (Phạm vi truy cập): nếu anh đang ghi đè một phương thức, phương thức ghi đè (tức là được khai báo ở class con) không được phép có phạm vi truy cập bị hạn chế hơn phương thức ở class cha.*
* *Covariant Return Type (Kiểu trả về đồng biến): Anh hoàn toàn có thể ghi đè phương thức bằng cách thay đổi kiểu trả về nếu class con ghi đè một phương thức có kiểu trả về là kiểu đối tượng (Non-Primitive), nhưng đổi kiểu trả về của nó thành kiểu của class con.*

### super Keyword

* *Từ khóa super là một biến tham chiếu được sử dụng để trỏ trực tiếp đến đối tượng của class cha gần nhất.*
* *super có thể được sử dụng để tham chiếu đến biến thực thể của class cha gần nhất hoặc gọi phương thức và constructor của class cha gần nhất.*
* *super() sẽ tự động được trình biên dịch thêm vào trong mỗi constructor của class nếu trong đó không có lệnh gọi super() hoặc this() nào.*

### Instance initializer block

* *Khối khởi tạo thực thể (Instance Initializer block) được sử dụng để khởi tạo thành viên dữ liệu của thực thể.*
* *Khối này được tạo ra khi thực thể của class được tạo.*
* *Nó chạy mỗi khi một đối tượng của class được tạo.*
* *Nó được gọi sau khi constructor của class cha được gọi (tức là sau lời gọi constructor super()).*
* *Các khối khởi tạo thực thể chạy theo thứ tự xuất hiện của chúng trong code.*

### final Keyword

* *Từ khóa final trong Java được sử dụng để hạn chế người dùng.*
* *Anh không thể thay đổi giá trị của một biến final (nó sẽ đóng vai trò là một hằng số).*
* *Anh không thể ghi đè một phương thức final.*
* *Nếu anh khai báo một class là final, anh không thể kế thừa (extend) class đó.*
* *Phương thức final vẫn được kế thừa nhưng anh không thể ghi đè nó.*
* *Một biến final không được khởi tạo tại thời điểm khai báo được gọi là biến blank final (biến final trống).*
* *Chúng ta chỉ có thể khởi tạo một biến blank final trong constructor.*
* *Một biến static final không được khởi tạo tại thời điểm khai báo được gọi là biến static blank final. Nó chỉ có thể được khởi tạo trong khối static (static block).*
* *Nếu anh khai báo một tham số là final, anh không thể thay đổi giá trị của tham số đó.*
* *A constructor không thể được khai báo là final vì nó không bao giờ được kế thừa.*

### Runtime Polymorphism

* *Đa hình (Polymorphism) là một khái niệm mà qua đó chúng ta có thể thực hiện một hành động duy nhất bằng nhiều cách khác nhau.*
* *Có hai loại đa hình trong Java: đa hình lúc biên dịch (compile time polymorphism) và đa hình lúc chạy (runtime polymorphism).*
* *Chúng ta có thể thực hiện đa hình trong Java bằng cách nạp chồng phương thức (method overloading) và ghi đè phương thức (method overriding).*
* *Nếu anh nạp chồng một phương thức static trong Java, đó là một ví dụ về đa hình lúc biên dịch.*
* *Trong đa hình lúc chạy (Runtime polymorphism / Dynamic Method Dispatch), một phương thức được ghi đè sẽ được định đoạt lúc chạy (runtime) thay vì lúc biên dịch (compile-time).*
* *Một Phương thức ảo (Virtual Method) là một phương thức có thể kế thừa và ghi đè, giúp tạo điều kiện cho việc điều phối động (dynamic dispatch).*
* *Tất cả các phương thức không phải static, không phải final và không phải private đều mặc định là các Phương thức ảo.*
* *Khi biến tham chiếu của class Cha trỏ đến đối tượng của class Con, điều này được gọi là upcasting (ép kiểu lên).*
* *Phương thức được ghi đè chứ thành viên dữ liệu thì không, vì vậy đa hình lúc chạy không thể đạt được thông qua các thành viên dữ liệu (thuộc tính).*
* *Việc kết nối một lời gọi phương thức tới thân phương thức được gọi là binding (liên kết).*
* *Có hai loại liên kết: Liên kết tĩnh - Static binding (early binding) và Liên kết động - Dynamic binding (late binding).*

### instanceof Keyword

* *Toán tử instanceof được sử dụng để kiểm tra xem đối tượng có phải là một thực thể của một kiểu dữ liệu cụ thể (class/subclass/interface) hay không.*
* *Khi kiểu class Con tham chiếu đến đối tượng của class Cha, điều này được gọi là downcasting (ép kiểu xuống).*
* *Nếu chúng ta thực hiện downcasting trực tiếp, sẽ xảy ra lỗi biên dịch.*
* *Nếu chúng ta thực hiện downcasting bằng cách ép kiểu (typecasting), ngoại lệ ClassCastException sẽ bị ném ra lúc chạy.*
* *Nếu chúng ta sử dụng toán tử instanceof, việc downcasting là hoàn toàn khả thi!*

### Abstract Class

* *Một class được khai báo với từ khóa abstract được gọi là abstract class (lớp trừu tượng). Nó có thể có các phương thức trừu tượng (abstract) và phi trừu tượng (non-abstract).*
* *Trừu tượng hóa (Abstraction) là một quá trình ẩn đi các chi tiết triển khai bên trong và chỉ hiển thị tính năng cho người dùng.*
* *Có hai cách để đạt được sự trừu tượng trong Java: Abstract class (từ 0 đến 100%) và Interface (100%).*
* *Một phương thức được khai báo là abstract và không có phần thân triển khai thì gọi là abstract method.*
* *Bất kỳ phương thức nào có phần thân (body) đều là phương thức phi trừu tượng (non-abstract).*
* *Một abstract class có thể có thành viên dữ liệu, phương thức abstract, thân phương thức, constructor và thậm chí cả phương thức main().*
* *Nếu có bất kỳ phương thức abstract nào trong một class, thì class đó bắt buộc phải là abstract class.*
* *Nếu kế thừa một abstract class có phương thức abstract, chúng ta phải cung cấp phần triển khai cho phương thức đó hoặc phải khai báo class con này là abstract class.*
* *Abstract class cũng có thể được sử dụng để triển khai một phần của một interface. Khi đó, người dùng cuối khi kế thừa abstract class này có thể tự do bỏ qua việc triển khai phương thức đó trong khi vẫn ghi đè được tất cả các phương thức khác của interface.*

### Interface

* *Một interface trong Java là một bản thiết kế (blueprint) của một class. Nó chứa các hằng số static (static constants) và các phương thức trừu tượng (abstract methods).*
* *Từ Java 8, chúng ta có thể có phần thân phương thức trong interface. Nhưng chúng ta cần phải khai báo nó là phương thức default hoặc static.*
* *Interface là một cơ chế để đạt được sự trừu tượng. Nó đại diện cho mối quan hệ IS-A.*
* *Bằng cách sử dụng interface, chúng ta có thể hỗ trợ đa kế thừa.*
* *Nó cũng có thể được sử dụng để đạt được loose coupling - liên kết lỏng lẻo (coupling là mức độ hiểu biết trực tiếp mà một thành phần có về một thành phần khác).*
* *Trình biên dịch Java tự động thêm `public & abstract` trước phương thức của interface, và thêm `public, static & final` trước các thành viên dữ liệu.*
* *Một class kế thừa (extends) một class khác, một interface kế thừa (extends) một interface khác, nhưng một class thì triển khai (implements) một interface.*
* *Đa kế thừa không được hỗ trợ bởi class vì sự mơ hồ. Tuy nhiên, nó được hỗ trợ bởi interface vì không có sự mơ hồ nào cả, do phần triển khai thực tế sẽ được cung cấp bởi class triển khai.*
* *Một interface không có thành viên nào bên trong được gọi là marker interface hoặc tagged interface (interface đánh dấu). Ví dụ: Serializable, Cloneable, Remote, v.v.*
* *Marker interface được sử dụng để cung cấp thông tin thiết yếu cho JVM, giúp JVM có thể thực hiện một số hoạt động hữu ích.*
* *Một interface có thể chứa một interface khác bên trong, điều này được gọi là nested interface (interface lồng nhau).*

### Package

* *Một package trong Java là một nhóm các kiểu class, interface và sub-package (package con) tương tự nhau.*
* *Package trong Java được sử dụng để phân loại các class và interface, cung cấp tính năng bảo vệ truy cập và loại bỏ xung đột đặt tên.*
* *Từ khóa package được sử dụng để tạo một package. Package nằm bên trong một package khác được gọi là subpackage.*
* *Nếu anh import một package dạng (package.* ), các subpackage bên trong sẽ không được import theo.*
* *Để import subpackage, hãy sử dụng cấu trúc: import package.classname.*
* *Sử dụng tên đầy đủ (fully qualified name) để chỉ truy cập vào đúng class đã được khai báo của một package.*
* *Thứ tự trong một chương trình phải là: package đầu tiên, sau đó đến import, và cuối cùng là class.*
* *Tiêu chuẩn định danh package là domain.company.package. Ví dụ: com.oracle.database*
* *Chỉ có thể có duy nhất một class public trong một file nguồn Java và file đó phải được lưu bằng chính tên của class public đó.*

### Access Modifiers

* *Có hai loại modifier (bộ bổ nghĩa) trong Java: access modifiers (bộ điều phối truy cập) và non-access modifiers.*
* *Có 4 loại access modifiers trong Java: private, default, protected & public.*
* *Có nhiều non-access modifiers chẳng hạn như static, abstract, synchronized, native, volatile, transient, v.v.*
* *Access modifier private chỉ có thể truy cập được trong nội bộ của chính class đó.*
* *Nếu anh khai báo constructor của một class là private, anh không thể tạo thực thể của class đó từ bên ngoài class.*
* *Nếu chúng ta không sử dụng bất kỳ modifier nào, nó sẽ được coi là default. Default modifier chỉ có thể truy cập được trong cùng một package.*
* *Một Class không thể là private hoặc protected ngoại trừ trường hợp class lồng nhau (nested class).*
* *Access modifier protected có thể truy cập được trong cùng package và ngoài package nhưng chỉ thông qua quan hệ kế thừa.*
* *Access modifier public có thể truy cập được ở mọi nơi. Nó có phạm vi rộng nhất trong số tất cả các modifier.*
* *Nếu anh đang ghi đè bất kỳ phương thức nào, phương thức ghi đè (tức là được khai báo ở class con) không được phép có phạm vi truy cập bị hạn chế hơn phương thức ở class cha.*

### Encapsulation

* *Đóng gói (Encapsulation) là quá trình bọc code và dữ liệu lại với nhau thành một đơn vị duy nhất.*
* *Để tạo ra một class được đóng gói hoàn toàn, hãy khai báo tất cả các thành viên dữ liệu của class là private, và sử dụng các phương thức setter/getter để truy cập dữ liệu.*
* *Bằng cách chỉ cung cấp phương thức setter hoặc getter, anh có thể làm cho class đó trở thành chỉ đọc (read-only) hoặc chỉ ghi (write-only).*

### Miscellaneous

* *Mặc định, class Object là class cha của tất cả các class trong Java.*
* *Interface Cloneable phải được triển khai bởi class nếu chúng ta muốn tạo một bản sao (clone) của một đối tượng.*
* *Wrapper class được sử dụng để chuyển đổi kiểu dữ liệu nguyên thủy (primitive) thành đối tượng (object) và ngược lại.*
* *Tính năng Autoboxing và unboxing tự động chuyển đổi kiểu nguyên thủy thành đối tượng và đối tượng thành kiểu nguyên thủy.*
* *Trong Java chỉ có truyền tham trị (call by value), không có truyền tham chiếu (call by reference).*
* *Một phương thức trong Java tự gọi chính nó được gọi là phương thức đệ quy (recursive method).*
