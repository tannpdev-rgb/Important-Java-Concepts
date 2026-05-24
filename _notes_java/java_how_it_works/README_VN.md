# Các Tính năng của Java và Quá trình Thực thi Chương trình

Java vừa là một **ngôn ngữ lập trình (programming language)** vừa là một **nền tảng (platform)**. 

**Nền tảng (Platform):** Bất kỳ môi trường phần cứng hay phần mềm nào mà trong đó một chương trình được chạy, được gọi là một nền tảng. Vì Java có môi trường thực thi (runtime environment - JRE) và Giao diện Lập trình Ứng dụng (API) của riêng mình, nên nó được gọi là một nền tảng.

## Các Tính năng của Java :

![java-features](https://user-images.githubusercontent.com/2780145/34343690-2fd47db0-e9ff-11e7-9630-75423dda7eaa.png)

- **Đơn giản (Simple):**
  - Cú pháp thân thiện với người dùng dựa trên C++
  - Có tính năng Thu gom Rác Tự động (Automatic Garbage Collection)
  - Có một bộ API phong phú (Rich set of APIs) 
  - Đã loại bỏ các tính năng gây nhầm lẫn - con trỏ tường minh (explicit pointers), nạp chồng toán tử (operator overloading), đa kế thừa (multiple inheritance), v.v.
  
- **Hướng Đối tượng (Object-Oriented):**
  - Trong Java, chúng ta tổ chức phần mềm như một sự kết hợp của nhiều loại object khác nhau kết hợp cả dữ liệu và hành vi.
  - Dựa trên khái niệm về Objects, Class, Kế thừa, Đa hình, Trừu tượng, Đóng gói.
  
- **Độc lập Nền tảng (Platform Independent):**
  - Java cung cấp một nền tảng dựa trên phần mềm. Nó có hai thành phần:
    - JRE (Runtime Environment - Môi trường Thực thi)
    - API (Application Programming Interface - Giao diện Lập trình Ứng dụng)
  - Mã nguồn Java được biên dịch bởi compiler và chuyển đổi thành bytecode. Bytecode này là nền tảng độc lập. Có thể chạy trên nhiều nền tảng - Windows, Linux, Mac, v.v.
  
- **Bảo mật (Secured):**
  - **Không có con trỏ tường minh (No explicit pointer)**
  - **JVM -** Các chương trình Java chạy bên trong một hộp cát (sandbox) của máy ảo.
  - **Classloader -** gia tăng bảo mật bằng cách tách biệt gói (package) cho các classes thuộc local file system ra khỏi những classes được import từ các nguồn mạng.
  - **Bytecode Verifier -** kiểm tra các đoạn mã (code fragments) xem có mã độc (illegal code) nào có thể vi phạm quyền truy cập vào các objects hay không.
  - **Security Manager -** xác định các tài nguyên mà một class có thể truy cập như thao tác đọc và ghi vào local disk.
  - **Nhiều hơn nữa -** các nhà phát triển có thể bổ sung thêm tính năng bảo mật thông qua SSL, JAAS, Cryptography, v.v.
  
- **Mạnh mẽ (Robust):**
  - **Quản lý bộ nhớ tốt (Good memory management) -** Thu gom rác tự động.
  - **Không có con trỏ -** tăng tính bảo mật. 
  - **Xử lý Ngoại lệ (Exception handling) -** tăng cường sự mạnh mẽ để chống lại các lỗi (errors).
  - **Strongly typed -** mọi biến đều bắt buộc phải được khai báo với một kiểu dữ liệu.
  - **Statically typed -** quá trình kiểm tra kiểu (type checking) của biến được thực hiện tại thời điểm biên dịch (compile time).
  
- **Kiến trúc Trung lập (Architecture-Neutral):**
  - Không có các tính năng bị phụ thuộc vào triển khai thực tế. vd. kích thước của các kiểu nguyên thủy là cố định.
  
- **Khả năng Di động (Portable):**
  - Viết Một lần và Chạy Mọi nơi (Write Once and Run Anywhere).
   
- **Thông dịch (Interpreted):**
  - Java được biên dịch sang bytecodes, sau đó được thông dịch bởi Java run-time environment.
  - Trình thông dịch (interpreter) đọc luồng bytecode rồi sau đó thực thi các lệnh.
  
- **Hiệu suất Cao (High-Performance):**
  - **Sử dụng ByteCode -** Java nhanh hơn các ngôn ngữ thông dịch truyền thống vì byte code rất "gần" với native code. 
  - **Just-In-Time (JIT) -** nó được thiết kế để hỗ trợ các JIT compilers, vốn sẽ biên dịch bytecode thành mã máy (machine code) một cách linh hoạt (dynamically). 
  - **Garbage collector -** thu gom các vùng nhớ không còn sử dụng để cải thiện hiệu suất của ứng dụng.
  - LƯU Ý: Java vẫn chậm hơn ngôn ngữ biên dịch (compiled language) như C/C++.
  
- **Phân tán (Distributed):**
  - Chúng ta có thể tạo các ứng dụng phân tán trong java. RMI và EJB được sử dụng để xây dựng các ứng dụng phân tán.
  - Chúng ta có thể truy cập các files bằng cách gọi các methods từ bất kỳ máy nào trên internet.
  
- **Đa luồng (Multi-threaded):**
  - Một luồng (thread) giống như một chương trình riêng biệt, thực thi đồng thời (concurrently). Chúng ta có thể viết các chương trình Java giải quyết nhiều nhiệm vụ cùng lúc bằng cách định nghĩa ra nhiều luồng.
  - Ưu điểm chính của đa luồng là nó không chiếm dụng từng phần bộ nhớ riêng cho mỗi luồng. Nó chia sẻ chung một vùng bộ nhớ (common memory area).
  - Threads có vai trò quan trọng đối với các ứng dụng đa phương tiện (multi-media), ứng dụng Web, v.v.
  
- **Linh hoạt (Dynamic):**
  - **Dynamic Compilation (JIT) -** Triển khai để gia tăng hiệu suất trong suốt quá trình thực thi chương trình. Mã máy (machine code) xuất ra bởi một dynamic compiler được xây dựng và tối ưu hóa tại thời điểm runtime, việc sử dụng dynamic compilation cho phép tăng cường hiệu suất một cách tối ưu.
  - **Load on Demand (Tải theo Yêu cầu) -** Tải các classes khi chúng được cần tới, thậm chí lấy từ phía bên kia của mạng.
  - **Cấp phát bộ nhớ động (Dynamic memory allocation) -** Tất cả các Java objects đều được cấp phát động. 
  - **Đa hình Động (Dynamic Polymorphism) -** Compiler không biết trước phương thức nào sẽ được gọi. JVM quyết định phương thức nào sẽ được gọi ở lúc run time.

## Quy trình Thực thi Chương trình Java :

![java-execution-process](https://user-images.githubusercontent.com/2780145/34343683-d3aea7e0-e9fe-11e7-866d-26a8857e04c9.png)

## JDK - JRE - JVM - JIT :

![jdk-jre-jvm-jit](https://user-images.githubusercontent.com/2780145/34342877-771d2796-e9e4-11e7-9d18-98ed672a4b53.png)

**Java Development Kit (JDK):** Đây là một bộ các công cụ phát triển phần mềm có bao gồm cả JRE.

**Java Runtime Environment (JRE):** Nó chứa bộ các thư viện và cả JVM.

**Java Virtual Machine (JVM):** Nó là một cỗ máy trừu tượng. Nó là một bộ đặc tả (specification) nhằm cung cấp runtime environment nơi mà java bytecode có thể được thực thi. JVM thực hiện các nhiệm vụ chính sau: Tải mã code (Loads code), Kiểm tra mã code (Verifies code), Thực thi mã code (Executes code) và Cung cấp môi trường thực thi (Provides runtime environment).

**LƯU Ý -** Các JVM khả dụng cho rất nhiều nền tảng phần cứng và phần mềm. JVM, JRE và JDK bị phụ thuộc vào nền tảng (platform dependent) do cấu hình của mỗi OS là khác nhau. Nhưng, bản thân Java là độc lập nền tảng (platform independent).

## Kiến trúc Nội bộ của JVM :

![jvm-architecture](https://user-images.githubusercontent.com/2780145/34343635-f405f2f2-e9fc-11e7-9628-28992defdd0b.png)

JVM (Java Virtual Machine) có nhiều thành phần con (sub components) bên trong. Bạn có thể nhìn thấy những phần quan trọng nhất ở sơ đồ trên.

- **Class loader sub system (Hệ thống tải lớp con):** Hệ thống tải lớp con của JVM thực hiện 3 nhiệm vụ
  - Nó tải .class file vào bộ nhớ.
  - Nó xác minh (verifies) các byte code instructions.
  - Nó phân bổ (allots) bộ nhớ cần thiết cho chương trình.
  
- **Run time data area (Vùng dữ liệu chạy):** Đây là tài nguyên bộ nhớ được JVM sử dụng và nó được chia thành 5 phần
  - **Class (Method) area:** Lưu trữ hằng số (constant pool), dữ liệu của field và method, mã code cho các phương thức.
  - **Heap:** Các objects được cấp phát trên heap.
  - **Java stacks:** Java stacks là những nơi mà các Java methods được thực thi. Một Java stack chứa các frames. Nó lưu giữ các local variables (biến cục bộ) và các partial results (kết quả một phần), và đóng một vai trò trong việc gọi cũng như return của method. Trên mỗi frame, một method riêng biệt được thực thi. Mỗi thread sẽ có một private JVM stack, được tạo ra cùng thời điểm với thread. Một new frame được tạo ra mỗi khi một method được gọi. Một frame sẽ bị hủy (destroyed) khi tiến trình gọi method của nó hoàn tất.
  - **Program counter registers (Thanh ghi bộ đếm chương trình):** PC (program counter) register. Nó chứa địa chỉ của câu lệnh JVM hiện đang được thực thi.
  - **Native method stacks:** Là những nơi mà native methods (ví dụ: các chương trình sử dụng ngôn ngữ C, v.v.) được thực thi.
  
-  **Native method interface:** Native method interface là một chương trình kết nối thư viện của các native methods (ví dụ: các C header files) với JVM để thực thi các native methods.

- **Native method library:** Chứa các thông tin về native libraries.

- **Execution engine (Động cơ thực thi):** 
  - **Just-In-Time(JIT) compiler:** Nó được dùng để cải thiện hiệu suất. Nó dịch byte code thành machine code. JIT cùng lúc sẽ biên dịch các phần của byte code có chức năng tương tự, và do đó giảm thiểu thời gian cần thiết cho việc biên dịch. Ở đây thuật ngữ "compiler" muốn nói đến một trình biên dịch (translator) chuyển từ bộ lệnh của một Java virtual machine (JVM) sang bộ lệnh của một CPU cụ thể.
  - **Interpreter (Trình thông dịch):** Đọc luồng bytecode sau đó thực thi các lệnh.
  - **Virtual processor (Bộ xử lý ảo)** 
  - **LƯU Ý -** JVM sử dụng một kỹ thuật tối ưu hóa để quyết định xem phần nào nên được interpreter dịch và phần nào nên được sử dụng với JIT compiler.
