# Đa luồng (Multithreading)

Đa luồng (Multithreading) trong Java là một quá trình thực thi nhiều luồng (threads) cùng một lúc. Thread về cơ bản là một tiến trình con hạng nhẹ (lightweight sub-process), một đơn vị xử lý nhỏ nhất. Đa tiến trình (Multiprocessing) và đa luồng (multithreading), cả hai đều được sử dụng để đạt được đa nhiệm (multitasking).

Tuy nhiên, chúng bản sử dụng multithreading nhiều hơn multiprocessing bởi vì các threads chia sẻ một vùng bộ nhớ chung (common memory area). Chúng không cấp phát vùng bộ nhớ riêng biệt nên tiết kiệm bộ nhớ, và quá trình chuyển đổi ngữ cảnh (context-switching) giữa các threads mất ít thời gian hơn so với các tiến trình (process).

Thread được thực thi bên trong tiến trình (process). Có sự chuyển đổi ngữ cảnh giữa các threads. Có thể có nhiều processes bên trong OS (hệ điều hành) và một process có thể có nhiều threads.

![java-cpu-thread](https://user-images.githubusercontent.com/2780145/34954754-a19d1652-fa47-11e7-8d36-4ac3858383b2.png)

**Ưu điểm của Đa luồng :**
- Nó **không chặn (block) người dùng** vì các threads độc lập với nhau và bạn có thể thực hiện nhiều thao tác cùng lúc.
- Bạn **có thể thực hiện nhiều thao tác đồng thời (simultaneously)** nhờ đó tiết kiệm được thời gian.
- Các Threads là **độc lập**, vì vậy nó không ảnh hưởng đến các threads khác nếu có ngoại lệ (exception) xảy ra ở một thread nào đó.

## Đa nhiệm (Multitasking)

Đa nhiệm là quá trình thực thi nhiều tác vụ cùng một lúc. Chúng ta sử dụng đa nhiệm để tận dụng tối đa CPU. Đa nhiệm có thể đạt được bằng hai cách:
- Đa nhiệm dựa trên tiến trình (Multiprocessing)
- Đa nhiệm dựa trên luồng (Multithreading)

| Đa tiến trình (Multiprocessing) | Đa luồng (Multithreading) |
| --- | --- |
| Mỗi process có địa chỉ riêng trong bộ nhớ, tức là mỗi process cấp phát một vùng bộ nhớ riêng biệt. | Các Threads cùng chia sẻ chung một không gian địa chỉ. |
| Process có tính chất nặng (heavyweight). | Thread có tính chất nhẹ (lightweight). |
| Chi phí giao tiếp giữa các tiến trình là rất lớn. | Chi phí giao tiếp giữa các luồng là rất thấp. |
| Việc chuyển đổi ngữ cảnh đòi hỏi thời gian nhất định để lưu và tải thanh ghi, bản đồ bộ nhớ, cập nhật danh sách, v.v. | Việc chuyển đổi ngữ cảnh giữa các threads mất ít thời gian hơn so với process. |

**LƯU Ý :** Context switching (chuyển đổi ngữ cảnh hay chuyển đổi luồng/tiến trình) là quá trình chuyển đổi CPU (bộ vi xử lý trung tâm) từ một process hoặc thread này sang một process hoặc thread khác.

## Vòng đời của một Luồng (Life Cycle of a Thread)

Vòng đời của thread trong java được kiểm soát bởi JVM. Các trạng thái của một luồng trong java như sau:
1. **New (Mới) -** Thread đang ở trạng thái new nếu bạn tạo một instance (thực thể) của class Thread nhưng trước khi gọi (invocation) phương thức start().
2. **Runnable (Có thể chạy) -** Thread chuyển sang trạng thái runnable sau khi gọi phương thức start(), nhưng trình lập lịch cho luồng (thread scheduler) chưa chọn nó làm luồng đang chạy.
3. **Running (Đang chạy) -** Thread ở trạng thái running nếu trình lập lịch cho luồng đã chọn nó.
4. **Non-Runnable (Bị chặn/Blocked) -** Đây là trạng thái khi mà thread vẫn còn sống, nhưng hiện tại không đủ điều kiện để chạy.
5. **Terminated (Kết thúc) -** Một thread nằm ở trạng thái terminated hoặc dead (chết) khi phương thức run() của nó thoát ra.

**LƯU Ý :** Theo Sun, chỉ có 4 trạng thái trong vòng đời của luồng trong java là new, runnable, non-runnable và terminated. Không có trạng thái running.

![Java Thread Life Cycle](https://user-images.githubusercontent.com/2780145/33823420-15edbc42-de81-11e7-9785-79e99b7b3a11.png)

## Tạo một Luồng (Creating a Thread)

**Có hai cách để tạo một thread:**
1. Kế thừa (extends) class Thread
2. Implements interface Runnable.

**Class Thread:** 
Class Thread cung cấp các hàm khởi tạo (constructors) và các phương thức để tạo ra và thực hiện các thao tác lên một thread. Class Thread kế thừa class Object và implements interface Runnable.

**Các Constructors thường được sử dụng của class Thread:**
- Thread()
- Thread(String name)
- Thread(Runnable r)
- Thread(Runnable r,String name)

**Các phương thức thường được sử dụng của class Thread:**
<ol>
<li><strong>public void run():  </strong> được dùng để thực hiện hành động cho một thread.</li>
<li><strong>public void start():  </strong>khởi chạy quá trình thực thi của thread. JVM gọi method run() trên thread.</li>
<li><strong>public void sleep(long miliseconds):  </strong> Khiến thread hiện tại đang chạy phải sleep (tạm ngừng thực thi) trong một khoảng mili giây xác định.</li>
<li><strong>public void join():  </strong>đợi cho một thread chết đi (kết thúc).</li>
<li><strong>public void join(long miliseconds):  </strong>đợi cho một thread chết đi trong một khoảng thời gian mili giây xác định.</li>
<li><strong>public int getPriority():  </strong>trả về độ ưu tiên của thread.</li>
<li><strong>public int setPriority(int priority):  </strong>thay đổi độ ưu tiên của thread.</li>
<li><strong>public String getName():  </strong>trả về tên của thread.</li>
<li><strong>public void setName(String name):  </strong>đổi tên cho thread.</li>
<li><strong>public Thread currentThread():  </strong>trả về reference của thread hiện tại đang chạy.</li>
<li><strong>public int getId():  </strong>trả về id của thread.</li>
<li><strong>public Thread.State getState():  </strong>trả về trạng thái của thread.</li>
<li><strong>public boolean isAlive():  </strong>kiểm tra xem thread có còn sống hay không.</li>
<li><strong>public void yield():  </strong>khiến object thread hiện tại đang thực thi tạm thời dừng lại và cho phép các threads khác thực thi.</li>
<li><strong>public void suspend():  </strong>được sử dụng để đình chỉ thread (đã bị deprecated).</li>
<li><strong>public void resume():  </strong>được sử dụng để tiếp tục một thread đang bị đình chỉ (đã bị deprecated).</li>
<li><strong>public void stop():  </strong>được sử dụng để dừng thread lại (đã bị deprecated).</li>
<li><strong>public boolean isDaemon():  </strong>kiểm tra xem thread có phải là một daemon thread hay không.</li>
<li><strong>public void setDaemon(boolean b):  </strong>đánh dấu thread là daemon hoặc user thread.</li>
<li><strong>public void interrupt():  </strong>gián đoạn (interrupts) thread.</li>
<li><strong>public boolean isInterrupted():  </strong>kiểm tra xem thread đã bị gián đoạn hay chưa.</li>
<li><strong>public static boolean interrupted():  </strong>kiểm tra xem thread hiện tại đã bị gián đoạn hay chưa.</li>
</ol>

**Interface Runnable:**
Interface Runnable nên được implement bởi bất kỳ class nào mà các instances của nó được dự định sẽ được thực thi bởi một thread. Interface Runnable chỉ có duy nhất một phương thức là run(). **public void run():** được dùng để thực hiện hành động cho một thread.

**Khởi chạy một thread:**
Phương thức **start()** của class Thread được sử dụng để bắt đầu một thread vừa mới tạo. Nó thực hiện các nhiệm vụ sau:
- Một luồng mới bắt đầu (với callstack mới).
- Luồng chuyển từ trạng thái New sang trạng thái Runnable.
- Khi luồng có cơ hội thực thi, phương thức mục tiêu run() của nó sẽ được chạy.

## Các Mã lệnh Tạo Thread (Creating Thread Codes) :

1. Ví dụ về Thread qua việc kế thừa class Thread
```java
class Multi extends Thread {
    public void run() {
        System.out.println("thread is running...");
    }
    public static void main(String args[]) {
        Multi t1 = new Multi();
        t1.start();
    }
}
```

2. Ví dụ về Thread qua việc implements interface Runnable
```java
class Multi3 implements Runnable {
    public void run() {
        System.out.println("thread is running...");
    }

    public static void main(String args[]) {
        Multi3 m1 = new Multi3();
        Thread t1 = new Thread(m1);
        t1.start();
    }
}
```

## Trình Lập lịch Thread trong Java (Thread Scheduler in Java)
Trình lập lịch thread trong java là một phần của JVM quyết định luồng nào sẽ chạy. Không có gì đảm bảo luồng runnable nào sẽ được trình lập lịch thread chọn để chạy. Chỉ có duy nhất một luồng tại một thời điểm được chạy trong một tiến trình duy nhất. Trình lập lịch thread chủ yếu sử dụng lập lịch ưu tiên (preemptive) hoặc chia cắt thời gian (time slicing) để lập lịch cho các luồng.

**Sự khác biệt giữa preemptive scheduling (lập lịch ưu tiên) và time slicing (chia cắt thời gian)**

Dưới cơ chế preemptive scheduling, tác vụ có độ ưu tiên cao nhất sẽ thực thi cho đến khi nó chuyển sang các trạng thái waiting hoặc dead hoặc một tác vụ có độ ưu tiên cao hơn xuất hiện. Dưới cơ chế time slicing, một tác vụ sẽ thực thi trong một khoảng thời gian được xác định trước, sau đó đi vào lại pool của các tác vụ đã sẵn sàng (ready tasks). Trình lập lịch sau đó sẽ xác định xem tác vụ nào sẽ được thực thi tiếp theo, dựa vào mức độ ưu tiên và các yếu tố khác.

**LƯU Ý :**
Chúng ta không thể khởi chạy một thread hai lần. Sau khi đã chạy một thread, nó không bao giờ có thể được start một lần nào nữa. Nếu bạn cố làm vậy, một IllegalThreadStateException sẽ bị ném ra vào thời điểm nó được chạy lần thứ hai.

## Phương thức sleep() trong Java
Phương thức sleep() của class Thread được sử dụng để sleep một thread trong một khoảng thời gian được chỉ định.

**Class Thread cung cấp hai phương thức cho sleep :**
1. public static void sleep(long miliseconds)throws InterruptedException
2. public static void sleep(long miliseconds, int nanos)throws InterruptedException
```java
Thread.sleep(500)
```
Tại một thời điểm, chỉ một thread được thực thi. Nếu bạn sleep một thread trong khoảng thời gian đã cho, trình lập lịch thread sẽ chọn một luồng khác và tiếp tục như vậy.

## Phương thức run() trong Java
Trong Java, Mỗi thread được bắt đầu trong một ngăn xếp lời gọi (call stack) tách biệt. Khi gọi phương thức run() từ main thread, phương thức run() sẽ đi vào call stack hiện tại thay vì ở điểm bắt đầu của một call stack mới.

**Vấn đề xảy ra nếu bạn gọi trực tiếp run() thay vì start() "**

Sẽ không có việc chuyển đổi ngữ cảnh (context-switching) trong chương trình bên dưới, bởi vì t1 và t2 lúc này sẽ được coi là object bình thường chứ không phải object của thread.
Đầu ra sẽ là : 1 2 3 4 5 1 2 3 4 5         (Một object sẽ chạy xong trước khi bắt đầu cái tiếp theo)
```java
class TestCallRun extends Thread {
    public void run() {
        for (int i = 1; i < 5; i++) {
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
            System.out.println(i);
        }
    }
    public static void main(String args[]) {
        TestCallRun2 t1 = new TestCallRun2();
        TestCallRun2 t2 = new TestCallRun2();

        t1.run();
        t2.run();
    }
}
```

## Phương thức join() trong Java
Phương thức Java Thread **join()** có thể được dùng để tạm ngưng quá trình thực thi của thread hiện tại, cho đến khi thread được chỉ định kết thúc (dead). 

**Có 3 phương thức join :**
1. public void join()
2. public void join(long millis)
3. public void join(long millis, int nanos)

**Ví dụ :**
```java
t1.join();   \\Thread hiện tại sẽ bị tạm ngưng, cho đến khi t1 dead. (t1 sẽ bắt đầu thực thi)
```
```java
t1.join(1500);  \\Thread hiện tại sẽ bị tạm ngưng, t1 sẽ thực thi trong 1500 mili giây.
```

## Đặt tên cho Thread (Naming Thread)
Class Thread cung cấp các method dùng để đổi và lấy tên của một thread. Mặc định, mỗi thread sẽ có tên là thread-0, thread-1 và cứ thế tiếp tục. Tuy nhiên, chúng ta có thể đổi tên của thread thông qua việc sử dụng phương thức setName().
- **public String getName():** dùng để lấy tên của một thread.
```java
t1.getName()
```
- **public void setName(String name):** dùng để đổi tên của một thread.
```java
t1.setName("My sweet thread"); 
```

Lấy thông tin của Thread hiện tại (Getting the Current Thread)

**public static Thread currentThread():** Phương thức currentThread() trả về một reference của thread hiện tại đang được thực thi.
```java
public void run(){ 
 System.out.println(Thread.currentThread().getName());
}  
```

## Mức độ Ưu tiên của Thread (Priority of a Thread)
Mỗi thread đều có một mức độ ưu tiên. Các mức ưu tiên được biểu diễn bởi một số nguyên từ 1 tới 10. Trong hầu hết các trường hợp, thread schedular sẽ lập lịch trình cho các thread tùy theo mức ưu tiên của chúng (được biết đến như là preemptive scheduling). Thế nhưng điều này cũng không được đảm bảo chắc chắn, bởi nó còn phụ thuộc vào các thông số đặc tả JVM để xác định thuật toán lập lịch nào sẽ được sử dụng.

3 hằng số (constants) được định nghĩa trong class Thread:
- public static int MIN_PRIORITY
- public static int NORM_PRIORITY
- public static int MAX_PRIORITY

Mức ưu tiên mặc định của một thread là 5 (NORM_PRIORITY). Giá trị của MIN_PRIORITY là 1 và của MAX_PRIORITY là 10.
```java
System.out.println("thread priority is:"+t1.getPriority()); 
```
```java
t1.setPriority(Thread.MIN_PRIORITY);  
```

## Luồng ngầm (Daemon Thread)
Daemon thread trong java là một service provider thread (luồng cung cấp dịch vụ) dùng để hỗ trợ các user thread. Nó không có chức năng nào khác ngoài việc phục vụ cho user threads. Sự tồn tại của nó hoàn toàn phụ thuộc vào các user threads, tức là khi toàn bộ user threads kết thúc (dies), JVM tự động cho hủy luôn (terminates) luồng này. Đây là luồng có mức độ ưu tiên rất thấp.

Có một số lượng đáng kể java daemon threads được chạy một cách tự động, ví dụ như gc, finalizer, v.v.

**LƯU Ý :** Bạn hoàn toàn có thể quan sát mọi chi tiết bằng cách nhập "jconsole" vào trong Command Prompt. Bộ công cụ jconsole này cung cấp thông tin về toàn bộ các classes đã load, tình hình bộ nhớ đang sử dụng, và tất nhiên là các luồng đang chạy (running threads), v.v.

**Các Phương thức cho Daemon Thread:**
- **public void setDaemon(boolean status):** dùng để đánh dấu luồng hiện tại đóng vai trò là một daemon thread hay là user thread.
```java
t1.setDaemon(true);   //Giờ đây, t1 đã là daemon thread  
t1.start()
```
- **public boolean isDaemon():** dùng để kiểm tra xem dòng thread ở hiện tại có phải là luồng daemon hay không.
```java
if(t1.isDaemon()) {
 ...
}
```

Trong trường hợp bạn mong muốn điều chỉnh lại một luồng user thread thành dạng Daemon, tiến trình này nên được làm dứt khoát trước khi bắt đầu khởi động luồng nếu không lỗi ngoại lệ IllegalThreadStateException sẽ ngay tức khắc được ném ra.
```java
t1.start();  
t1.setDaemon(true);     //Chỗ này sẽ ném ra lỗi Exception  
```

## Nhóm luồng trong Java (Java Thread Pool)
Java Thread pool tượng trưng cho một tập đoàn nhóm bao gồm nhiều worker threads làm nhiệm vụ nằm chờ trực tiếp nhận giao việc, cùng lúc cho khả năng tài sử dụng tái sinh (reuse) qua nhiều đợt vô cùng dễ dàng.
Nếu ở trong bối cảnh thread pool, một hội nhóm gộp lại với một số lượng cố định thread (fixed size) sẽ được kiến tạo hình thành. Một thread trích xuất từ thread pool sẽ được kéo lên sau đấy tiếp nhận công việc phân định giao phó bằng phía service provider. Khi hoàn tất mỹ mãn khối lượng đồ sộ công việc job, tiến trình của thread đó tiếp tục hồi lại lặn lội quay về túc trực tại kho the thread pool một lần nữa.

**Thế mạnh (Advantage) của Java Thread Pool đem đến là Better performance (Nâng cao khả năng hiệu suất).** Nó chắt chiu tiết kiệm lượng thời giờ khủng bởi khi bấy giờ chẳng hề mang áp lực cần mẫn ngồi tạo new thread (luồng mới) thủ công.

**Trường hợp sử dụng thực tế (Real time usage):** Chức năng này cực kì đắc dụng áp dụng trong Servlet và JSP khu vực nơi mà container sẽ đảm nhận việc xây dựng tạo nên cả dàn thread pool cho mục tiêu xử trí đáp ứng (process the request).

**Cú pháp Ví dụ:**
```java
ExecutorService executor = Executors.newFixedThreadPool(5);  //khởi tạo ra lượng hồ chứa với 5 threads 
```
```java
Runnable worker = new ...
executor.execute(worker);   //gọi lên execute method do kho ExecutorService quản hạt  
```

## Lớp ThreadGroup trong Java
Ngôn ngữ Java trang bị phương tiện thuận lợi gộp nhóm lại rất nhiều những luồng (multiple threads) vào quy tụ nơi cùng một nền tảng đối tượng đơn. Nương theo kiểu cách này, bọn mình dư sức đưa ra quyết định đóng băng đình chỉ (suspend), hoạt động trở lại (resume) hoặc gây ngắt cản trở (interrupt) bao la nhóm (group of threads) đơn giản trải qua vỏn vẹn đúng một nhát kêu gọi method. Java thread group tự hào thể hiện sức mạnh bằng gói tính năng java.lang.ThreadGroup class.

**LƯU Ý :** Bây giờ hàng loạt những phương thức suspend(), resume() đi cùng với stop() đã mang bản án lỗi thời **deprecated**.

**Constructors (Hàm khởi tạo) thuộc ThreadGroup class :**
<table class="alt">
<tbody><tr><th>STT</th><th>Hàm khởi tạo</th><th>Mô tả</th></tr>
<tr><td>1)</td><td>ThreadGroup(String name)</td><td>sinh tạo vùng mảng thread group đính cùng tên chỉ định name.</td></tr>
<tr><td>2)</td><td>ThreadGroup(ThreadGroup parent, String name)</td><td>tạo khuôn một luồng thread group bám vào gốc rễ the parent group đi chung với tên định danh.</td></tr>
</tbody></table>

**Các Phương thức Đặc thù (Important methods) của lớp ThreadGroup class :**
<table class="alt">
<tbody><tr><th>STT</th><th>Phương thức</th><th>Mô tả</th></tr>
<tr><td>1)</td><td>int activeCount()</td><td>báo trả ra lượng đếm (no. of) tổng threads thực thi đang cày cuốc trực thuộc phạm vi current group.</td></tr>
<tr><td>2)</td><td>int activeGroupCount()</td><td>chốt xuất ra số đếm các tổ nhóm đang mở hoạt động phía bên trong nội hàm thread group này.</td></tr>
<tr><td>3)</td><td>void destroy()</td><td>thanh toán hủy diệt bạt trần (destroys) bản thể luồng the thread group kèm tất tật các nhóm phụ thuộc con cháu của nó.</td></tr>
<tr><td>4)</td><td>String getName()</td><td>thông báo truy hồi cái tên the name thuộc the group ở đây.</td></tr>
<tr><td>5)</td><td>ThreadGroup getParent()</td><td>tường trình đưa ra đấng sinh thành the parent đại biểu cho the group.</td></tr>
<tr><td>6)</td><td>void interrupt()</td><td>chặn đứt (interrupts) nhất loạt dăm ba the threads bao trùm vùng nội hàm this group.</td></tr>
<tr><td>7)</td><td>void list()</td><td>xuất phác in (prints) loạt bản tin thông cáo tình huống this group ném dội dạt hướng cái standard console.</td></tr>
</tbody></table>

**Kiến tạo lập nhóm quy nạp threads :**
```java
ThreadGroup tg1 = new ThreadGroup("Group A");   
Thread t1 = new Thread(tg1,new MyRunnable(),"one");     
Thread t2 = new Thread(tg1,new MyRunnable(),"two");     
Thread t3 = new Thread(tg1,new MyRunnable(),"three");    
```
Hiện thực giờ phút này toàn bộ 3 mớ threads tề tựu góp mặt nằm yên bên trong ranh giới one group. Theo cái cớ đó, biến tg1 là định danh the thread group name, class MyRunnable đóng thay vai mượn hình lớp implements interface đính mác Runnable cộng với dòng "one", "two" đi liền chung "three" chính hiệu cho mấy cái tên định dạng the thread names.

Đến đây bọn mình có thể làm khựng dòng chảy toàn bộ mọi the threads qua sự điều phối dứt điểm của duy nhất chỉ một mảng dòng dòng lệnh (single line of code).
```java
Thread.currentThread().getThreadGroup().interrupt();  
```

## Chức năng Shutdown Hook trong Java
Nét công dụng the shutdown hook hữu duyên ứng vận tạo khả năng tiến hành quét dọn mảng tài nguyên (cleanup resource) hoặc là thu thập bảo tồn the state (lưu trạng thái) ngay dịp quá trình chạy dọn chỗ JVM (Java Virtual Machine) đột ngột trút tắt sập nguồn dù thuận tình hay ngang trái (normally or abruptly). Động thái thi hành nhiệm vụ làm sạch tài nguyên đồng nghĩa với việc đóng the log file, đẩy phóng đi tin báo hiệu (alerts) đính với chuyện nào đó linh tinh khác. Để rút gọn, nhằm thực thi khối mã chốt sổ trước cái khi nhịp đập JVM tịt hẳn thì khuyên bạn vận hành hệ the shutdown hook.

**JVM sẽ tắt đi khi:** 
tay người thao tác bập mạnh cụm phím ctrl+c ngay màn cửa command prompt, cấu hình hàm method System.exit(int) chịu lôi lên (invoked), tài khoản dùng rút dây mạng đăng xuất (user logoff), shutdown cúp điện, đại loại vậy.

Quyền năng hàm **addShutdownHook()** mượn tạm class Runtime chịu trọng trách đăng kiểm báo danh mớ luồng rễ the thread với bệ phóng Virtual Machine.
```java
public void addShutdownHook(Thread hook){}  
```
Khuôn the object bọc class Runtime dễ ợt tóm dính được ngay nhờ màn kéo gọi luồng method gốc tĩnh static factory method rành danh mang hiệu getRuntime()
```java
Runtime r = Runtime.getRuntime();
```

**Factory method (Phương thức nhà máy):** Cơ ngơi method xướng trả cái thể the instance của một dòng the class thường hay truyền bá với nhân dạng hàm factory method.

**LƯU Ý:** Nhịp độ shutdown sequence (trình tự tắt luồng) sẽ tạm treo lơ lửng ngưng ngắt bằng tiến trình khơi dậy lời gọi bóp còi method halt(int) từ the Runtime class.

## Multitask (Đa tác vụ)

Từng cái một the thread trải đường thực thi riêng biệt nương nhờ hầm chứa riêng the **callstack**.

![callstack](https://user-images.githubusercontent.com/2780145/35023526-11302878-fb61-11e7-942a-da830e4cd714.JPG)
```java
class TestMultitasking1 extends Thread {
    public void run() {
        System.out.println("task one");
    }
    public static void main(String args[]) {
        TestMultitasking1 t1 = new TestMultitasking1();
        TestMultitasking1 t2 = new TestMultitasking1();
        t1.start();
        t2.start();
    }
}
```

## Cơ chế Thu gom Rác trong Java (Java Garbage Collection)
Với cõi Java, mảng rác (garbage) gán ghép mang danh ý nói tới vùng đối tượng vô thừa nhận (unreferenced objects). Cơ chế Garbage Collection gánh trên lưng là hệ thống lấy lại đòi thu hồi lại nhũng nhiễu mảng không gian bộ nhớ (unused memory) tồn thời điểm runtime một cách hoàn toàn auto (tự động). Đảo ngược định nghĩa, đấy chính là chiêu lối để phá phách giật sập mớ the unused objects (đối tượng rảnh rỗi). Quá khứ nhằm để khai khẩn làm việc đó, đám chúng ta ưa xài gọi the hàm method free() với nền the C language cùng cặp delete() qua C++. Cơ mà qua ngạch java thứ sự kiện kia gánh chạy không tự phát (automatically). Thành thử, mảng sinh quyển java mang trên vai thế đứng dọn nhà quản lý memory vững tay chèo hơn tợn (better memory management).

**Lợi thế điểm cộng đối với Garbage Collection:**
- Giúp khối tài nguyên bộ nhớ java **memory efficient (đạt độ tinh vi hiệu suất cao)** qua chuyện the garbage collector gỡ nhổ tận gốc unreferenced objects tuôn trào lấp đầy trên không gian bãi mìn the heap memory.
- Mang tư thái vận hành **automatically done (tự thực thi dứt khoát trọn vẹn)** qua mảng nhíp vớt thu nhặt the garbage collector (vốn là phần đính thêm dính chặt a part of JVM) do vậy nên tụi mình chẳng phải oằn mình nỗ lực chi phụ thêm (extra efforts).

**Bằng lề thói nào đối tượng khoác bộ áo vô thừa nhận unreferenced:** 
- Qua bước xóa trắng rỗng thành nulling vùng liên đới the reference
```java
Employee e=new Employee();  
e=null;  
```
- Thông qua ngòi ấn tay giao phó assigning a reference tới trỏ ngắm vô đối tượng others (another)
```java
Employee e1=new Employee();  
Employee e2=new Employee();  
e1=e2;    //giờ lúc này, the first object chịu quản dưới trướng bằng e1 coi như ngỏ lời dâng hiến chào mời vào hàng ngũ đợt dọn rác the garbage collection
```
- Sử dụng nặc danh đối tượng (By anonymous object)
```java
new Employee();  
```
- Và v.v (etc).

**Hàm method finalize()**
Tầng function finalize() múa gọi xuất đầu lộ diện lặp hồi đều đặn (each time) sát rạt cận kề trước đợt the object được xúc tống tiễn đi the garbage collected (thu rác dọn dẹp). Thớ method trên đây gánh phần nhiệm kỳ chuyên đóng mác thi hành tác vụ xử lý rác rưởi (perform cleanup processing). Nguyên bản lớp method này được vạch ranh giới nằm thuộc thể loại Object class mô phỏng kiểu: 
```java
protected void finalize(){}  
```
**LƯU Ý :** The Garbage collector đính kèm the JVM khư khư bốc vét sục kiếm the objects cội rễ mọc cấu hình sinh nhờ tay từ khóa new keyword. Đặt giả thiết nếu chăng anh bạn mới sáng nảy ý định tạo mới ngộ nhận khơi dậy bất kỳ the object thiếu thốn sự góp sức nòng cốt cấu the new, anh có toàn quyền mượn cớ method the finalize nhằm triển khai quét dọn nhặt rác dọn trơn the cleanup processing (bức tử cho tan rã destroying thớ the objects thoi thóp thối rữa remaining objects).

**Hàm method gc():**
The gc() method giữ thiên chức bóp còi ấn đánh tiếng gọi cỗ xe vệ sinh quét rác the garbage collector lao đao dấn thân dọn ải the cleanup processing. Khối lệnh The gc() thường hay xuất chúng hiện diện đĩnh đạc bọc sau System đi kèm lấp mình vào cõi Runtime classes. Trọn gói cái method định dạng khoanh gọn vô trong ranh System class chắp nối nôm na sau đây: 
```java
public static void gc(){}  
```
```java
System.gc();    // ấn tay trực diện (explicitely) triệu tập bốc phét khởi binh the garbage collector
```
**LƯU Ý :** Chuỗi quá trình the Garbage collection nắm phần kiểm soát thi hành bởi luồng tuyến tay đua daemon thread bọc cái tên xưng danh gán mác the Garbage Collector(GC). Chiếc luồng thread khua chuông gõ trống bốc cái method the finalize() chạy khét đi qua vội trước cái hồi sự cố the object mang số mệnh rụng lả tả the garbage collected.

**LƯU Ý :**  Lẽ dĩ nhiên chẳng có mảy may chút đảm bảo cam kết chắc nịch (guaranteed) nào dính líu dính dáng cho chung chạ khâu dọn sạch the finalization hay kể cả chặng nhặt rác the garbage collection.

## Lớp Java Runtime Class
**Sản phẩm lớp the Java Runtime class ngắm vào cớ cấu trúc nhịp điệu thao túng tương tác hòa quyện dính lấy khối sinh thái the java runtime environment**. Class Java Runtime mở ra chặng đường các hàm methods chuyên đặc phái nã súng kích động thi hành a process, thúc hông khơi dậy vòng đua GC, tóm thâu số đếm ngạch the total lẫn móc lôi the free memory ra coi, v.v.. Lịch sử duy nhất tồn chỉ có lưu được đúng một thân cội bóng the instance ôm sát danh tính lớp java.lang.Runtime class trình diện thả ra mâm cỗ dọn sẵn đưa đường đón đợt chạy java application. Đám cành ngọn khối **Runtime.getRuntime()** method quăng ném về mặt the singleton instance trích hệ the Runtime class.

**Các Method Máu mặt Phân vai của lớp Java Runtime class :**
<table class="alt">
<tbody><tr><th>STT</th><th>Hàm Phương thức Method</th><th>Trần thuật Mô tả Description</th></tr>
<tr><td>1)</td><td>public static Runtime getRuntime()</td><td>phản hồi the instance chép hệ từ The Runtime class.</td></tr>
<tr><td>2)</td><td>public void exit(int status)</td><td>phá hủy hất cả the virtual machine hiện thời (current).</td></tr>
<tr><td>3)</td><td>public void addShutdownHook(Thread hook)</td><td>tiến cử ghi sổ cho tân dòng the hook thread dọn cửa mới mẻ.</td></tr>
<tr><td>4)</td><td>public Process exec(String command)throws IOException</td><td>cho chạy chuỗi the command truyền lệnh thả nằm ẩn phía trong a separate process ngăn vách.</td></tr>
<tr><td>5)</td><td>public int availableProcessors()</td><td>khai báo lượng con số the available processors rỗi rảnh khả dụng.</td></tr>
<tr><td>6)</td><td>public long freeMemory()</td><td>xuất báo con số độ lớn (amount) khoảng không memory chừa hổng tại ranh the JVM.</td></tr>
<tr><td>7)</td><td>public long totalMemory()</td><td>xuất báo mức the total tổng thể dung tích vùng memory phủ trong luồng JVM.</td></tr>
</tbody></table>

## Hàm method exec() lớp Java Runtime
```java
public class Runtime1{  
 public static void main(String args[])throws Exception{  
  Runtime.getRuntime().exec("notepad");  // Sẽ bật bung bung xòe cuộn ứng dụng mới tảng new notepad  
 }  
}  
```
**Tiến hành Tắt Cúp hệ thống qua mạn lệnh in Java :**
```java
Runtime.getRuntime().exec("shutdown -s -t 0");  // Máy tính sập nguồn Shutdown
```
Anh em tha hồ tùy ý nhấn bưng thả mớ câu chỉ lệnh shutdown -s command thả sức dẹp hệ thống sập nguồn chìm giấc (shutdown system). Ứng ngả sườn dốc windows OS, dân mình chịu mệt xíu cấp full path con đường trỏ mốc ngách shutdown command vd tỉ như c:\\Windows\\System32\\shutdown. Kéo tới đây anh tha hồ giật nút chuyển -s switch đóng chìm tịt mờ shutdown system, kéo công tắc -r switch mở điện khởi tranh lại cỗ máy the restart system còn kề tiếp gắn luôn cái -t switch đắp điểm trỏ báo nhịp lùi the time delay.
```java
Runtime.getRuntime().exec("c:\\Windows\\System32\\shutdown -s -t 0");  // Windows chịu số phận Shutdown
```
```java
Runtime.getRuntime().exec("shutdown -r -t 0");  // Sống lại Restart
```

**Thành phần Runtime gọi hố availableProcessors() method :**
```java
System.out.println(Runtime.getRuntime().availableProcessors());
```

**Khối Runtime điểm danh the freeMemory() sánh đôi totalMemory() method :**
```java
System.out.println("Tổng Bộ nhớ: "+Runtime.totalMemory());  
System.out.println("Bộ nhớ Trống: "+Runtime.freeMemory());  
```
