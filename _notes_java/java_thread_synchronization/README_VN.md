# Đồng bộ hóa (Synchronization) trong Java
Đồng bộ hóa (Synchronization) trong java là khả năng kiểm soát việc truy cập của nhiều luồng (multiple threads) vào bất kỳ một tài nguyên được chia sẻ (shared resource) nào đó. Java Synchronization là một sự lựa chọn tốt hơn cho những tình huống mà chúng ta chỉ muốn cho phép một luồng duy nhất được quyền thao tác với tài nguyên chia sẻ.

**Việc đồng bộ hóa được dùng cốt lõi nhằm mục đích :**
- Để **ngăn chặn sự Can thiệp vào Luồng (Thread Interference)** (Tình huống can thiệp luồng xảy ra trong điều kiện khi có hơn một luồng cùng lúc truy cập, xử lý cùng chung một vùng dữ liệu song song nhau).
- Để **ngăn ngừa Vấn đề Tính nhất quán (Consistency Problem)** (Các lỗi tính nhất quán bộ nhớ/memory consistency errors nổ ra mỗi khi dăm ba luồng phân mảnh vác theo các góc nhìn không trùng khớp thiếu đồng nhất đổ xô nhắm về một khối dữ kiện mà nhẽ ra chúng chỉ nên chứa mỗi một dạng).

## Các loại Đồng bộ hóa (Types of Synchronization) :
![synchronization-types](https://user-images.githubusercontent.com/2780145/35073887-214be2f0-fc11-11e7-9a84-604feca9bbb4.png)

## Đồng bộ hóa Luồng (Thread Synchronization)
Ở hạng mục đồng bộ hóa luồng (thread synchronization) đẻ ra hai ngách gọi là loại trừ lẫn nhau (mutual exclusive) và giao tiếp liên luồng (inter-thread communication).
1. Loại trừ lẫn nhau (Mutual Exclusive)
2. Hợp tác (Cooperation / Giao tiếp liên luồng trong java)

**Loại trừ lẫn nhau (Mutual Exclusive) :**
Tính chất Loại trừ Lẫn nhau xắn tay hỗ trợ giữ gọng kìm ngáng đường đống threads can thiệp (interfering) xéo nháo vào việc của luồng nọ luồng kia trong khi chia sẻ dữ liệu (sharing data). 
Ở cõi java, việc này có năng lực giải quyết nặn bằng ba the ways (cách) :
1. bằng phương thức đồng bộ hóa (synchronized method)
2. bằng khối đồng bộ hóa (synchronized block)
3. bằng đồng bộ hóa tĩnh (static synchronization)

**Khái niệm về Khóa (Lock) trong Java :**
Sự đồng bộ hóa (Synchronization) được thiết kế xây dựng xoay quanh một thực thể nội bộ (internal entity) mà giang hồ vẫn gọi là lock hay monitor. Mỗi một object đều nắm giữ cho mình một con lock gắn liền với nó. Theo lẽ thường (By convention), một thread nếu có nhu cầu nhào nặn truy cập trường dữ liệu đối tượng (object's fields) một cách nhất quán thì thread ấy bắt buộc phải thâu tóm được chốt khóa của object đó trước (acquire the object's lock), rồi sau khi cơm no rượu say (done), thread ấy phải xả nhả (release) the lock đó ra. Ở java tồn tại khối package java.util.concurrent.locks bọc giữ dăm ba bản ứng dụng lock implementations.

## Phương thức Đồng bộ (Synchronized Method) trong Java :
Nếu mà anh em khai báo bất cứ một method nào là đồng bộ synchronized, nó liền mang danh hàm đồng bộ synchronized method. Chức năng synchronized method xướng gọi công năng khóa (lock) một object rành cho bất cứ cái tài nguyên chia sẻ dùng chung (shared resource) nào. Nhất thời có mảng thread bóp còi gọi lên (invokes) một the synchronized method, nó auto nghiễm nhiên nhận chức thâu được chốt khóa lock khoác trên the object đó và xả khóa (releases) đi lúc mảng the thread xong nhiệm vụ the task.
```java
synchronized void printTable(int n){  //phương thức đồng bộ synchronized method  
   for(int i=1;i<=5;i++){  
     System.out.println(n*i);  
     try{  Thread.sleep(200);  
     }catch(Exception e){System.out.println(e);}  
   } }  
```

## Khối Đồng bộ (Synchronized Block) trong Java
Cụm Synchronized block tha hồ xài nhắm bung tính năng synchronization đè lên vạt bất cứ một dạng specific resource (tài nguyên đặc định) chia mảng bên trong lõi method. Kịch bản bày ra the method cõng tới tận 50 lines (dòng) code lót ổ, mà ông chỉ nằng nặc nhắm synchronize vỏn vẹn 5 dòng code, thì bưng cái synchronized block ra mà xài. Quy mô hoạt động (Scope) của synchronized block vốn eo hẹp bé mỏng the smaller sánh so the method. Trót dại anh khuân bốc toàn bộ đống mớ codes lót the method nhét lấp lọt the synchronized block, nó gánh chạy hệt như phiên bản the synchronized method sờ sờ luôn. Cú pháp (Syntax) - synchronized (biểu thức tham chiếu object / object reference expression) { ... }  
```java
void printTable(int n) {
    synchronized(this) { //khối đồng bộ (synchronized block)  
        for (int i = 1; i <= 5; i++) {
            System.out.println(n * i);
            try {
                Thread.sleep(200);
            } catch (Exception e) {
                System.out.println(e);
            }
        }
    }
}
```

## Đồng bộ hóa Tĩnh (Static Synchronization) trong Java
Bữa nào rảnh ông nhét bóp any static method mác the synchronized đè lên, chiếc thẻ the lock nắn đục móc nằm ngay mảng the class chứ hết cửa sượng object đâu.

**Bê bối Vấn đề ở mảng no static synchronization (không bọc đồng bộ tĩnh) :**

![static synchronization](https://user-images.githubusercontent.com/2780145/35074524-596ce5f0-fc14-11e7-8fd9-e7defb2de0ae.png)

Ví dụ bày ra tảng rẽ mọc hai cái đối tượng (two objects) chọc từ the shared class (lớp xài chung) ví như tên Table với mác object1 chập object2. Nằm cõi vạt the synchronized method cặp the synchronized block, chả bói ra cái interference (xen lấn) vướng vào the t1 cọ the t2 hoặc là t3 cấu the t4 vì đâm ra t1 với t2 cả thảy vướng dính (refers) chung chạ a common object (cùng một trát đối tượng) đội single lock đính. Cơ mà nhỡ đâu cắn nhầm the interference cấu the t1 xén the t3 hoặc mảng t2 xọ trúng t4 vì cớ t1 luồn bứt the lock (khóa này) rồi mà gã t3 ôm tịt the lock (chốt khác). Lòng tao ứ muốn rách chuyện ngáng interference tạt mảng t1 lấn t3, hay the t2 lấn t4 đâu. Kèo the Static synchronization nhảy ra dẹp loạn gánh gãy cái the problem.
```java
synchronized static void printTable(int n) {
    for (int i = 1; i <= 10; i++) {
        System.out.println(n * i);
        try {
            Thread.sleep(200);
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

## Tình trạng Bế tắc (Deadlock) trong Java

![deadlock of threads](https://user-images.githubusercontent.com/2780145/35073886-2122bc2c-fc11-11e7-97a0-a04938a49227.png)

Deadlock rớt mảng xô đụng tình huống một the thread bám chờ chốt ngáng an object lock, mảng bứt the acquired găm vô the another thread vả mảng the second thread nán rụt tay đợi an object lock chọc The acquired luồn first thread vả mảng. Khổ nỗi The both threads ứ buông tha ấp nhau release the lock rụng bứt ra, ranh the condition gán Deadlock bế tắc.
```java
public class TestDeadlockExample1 {
    public static void main(String[] args) {
        final String resource1 = "John";
        final String resource2 = "Tom";

        // t1 cố chiếm lock ở resource1 xong tính rớ resource2  
        Thread t1 = new Thread() {
            public void run() {
                synchronized(resource1) {
                    System.out.println("Luồng 1: đã khóa tài nguyên 1");
                    try {
                        Thread.sleep(100);
                    } catch (Exception e) {}
                    synchronized(resource2) {
                        System.out.println("Luồng 1: đã khóa tài nguyên 2");
                    }
                }
            }
        };

        // t2 hăm he hốt the lock resource2 xong vớt resource1  
        Thread t2 = new Thread() {
            public void run() {
                synchronized(resource2) {
                    System.out.println("Luồng 2: đã khóa tài nguyên 2");
                    try {
                        Thread.sleep(100);
                    } catch (Exception e) {}
                    synchronized(resource1) {
                        System.out.println("Luồng 2: đã khóa tài nguyên 1");
                    }
                }
            }
        };

        t1.start();
        t2.start();
    }
}
```
**Kết quả (Output):** 
```
Luồng 1: đã khóa tài nguyên 1
Luồng 2: đã khóa tài nguyên 2
```

## Giao tiếp Liên luồng (Inter-Thread Communication) trong Java
Nhánh Inter-thread communication hay The Co-operation trổ cớ đắp cầu xúi bầy synchronized threads vả the communicate với nhao. Co-operation (Hợp tác / Giao tiếp luồng in java) phác cái the mechanism đính mác The thread bị the paused (dừng băng luồng chạy) phanh gấp nấc the critical section khía mảng another thread bọc the allowed trượt nấc the enter (khía mảng tóm lock) chui ngách the same critical section tạt nấc the executed.

Được hiện thực hóa the implemented vướng nấc dăm 3 rổ the methods khía **Lớp Object (Object class):**
1. wait()
2. notify()
3. notifyAll()

### Hàm Method wait()
Khéo bứt the current thread (luồng nhấp nhô hiện chạy) tuôn the release (nhả) cái the lock chờ dập the wait tạt lúc mảng the another thread bóp ngòi the invokes tạt the notify() vọt the notifyAll() phanh method mảng The object đính mác, nhấp mảng a specified amount of time mảng the elapsed trượt dập. Ngạch the current thread ôm the must own cái The object's monitor tạt trút the called mảng the synchronized method mác the only hất vẳng rớt cái exception bứt tay.
- public final void wait()throws InterruptedException	
- public final void wait(long timeout)throws InterruptedException

### Hàm Method notify()
Đập dậy hất Wakes up mảng the single thread luồn the waiting nấp nẻo the object's monitor ranh. Hễ khía The any threads cắn the waiting nấp The object mảng the chosen rớt the awakened lót chăn. Khấc The choice dập mác the arbitrary nhấp vạt mảng The discretion tuôn the implementation ranh.
- public final void notify()

### Hàm Method notifyAll()
Vạch mác wakes up mảng trút the all threads dập mảng the waiting nằm The object's monitor hốc nẻo.
- public final void notifyAll()

## Nghiên cứu chu trình the inter-thread communication luồn lách

![inter-thread communication](https://user-images.githubusercontent.com/2780145/35122584-44ef23e8-fcc5-11e7-9caf-581529986ace.png)

**Nội hàm Giải trình cho Mảng Sơ đồ (Explanation of the above diagram) :**
1. Các luồng (Threads) tiến vào chiếm lấy chốt khóa lock.
2. The Lock chộp dính the acquired ngả mảng The one thread.
3. Kế tiếp The thread dạt lặn mảng the waiting state nhỡ The call trút wait() method trỏ the object. Chẳng may nấp cớ releases vạt The lock & tuôn exits lúc trút done.
4. If bứt the notify() ngả the notifyAll() method mọc trút The thread đập mảng the notified state (nảy The runnable state).
5. Now luồng the thread đắp mác the available chộp acquire vạt the lock.
6. Sau lúc the completion dứt the task, luồng The thread ngã releases vạt the lock lướt dập the exits trút the monitor state tạt the object.

**LƯU Ý:** Bọn wait(), the notify() kẹp notifyAll() tuôn nấc methods mọc nắn The defined ranh the Object class thay The Thread class vả cái cớ the related nhấp lock trút the object ôm mác the lock bứt.

## Phân Tách the Difference ranh the wait ngả the sleep
<table class="alt">
<tbody><tr><th>wait()</th><th>sleep()</th></tr>
<tr><td>Hàm wait() method dập thả the releases vạt the lock</td><td>Hàm sleep() method chả the doesn't ngả releases the lock.</td></tr>
<tr><td>mang ngạch a method trút Object class</td><td>mang ngạch a method trút Thread class</td></tr>
<tr><td>khuôn the a non-static method (hàm phi tĩnh)</td><td>khuôn the a static method (hàm tĩnh)</td></tr>
<tr><td>nối nhịp the notified gảy the notify() lọt notifyAll() methods</td><td>sứt the specified amount dập the time, luồng sleep tạt completed.</td></tr>
</tbody></table>

**Ví dụ the Inter Thread Communication tạt luồn :**
```java
class Customer {
 int amount = 10000;

 synchronized void withdraw(int amount) {
  System.out.println("đang tiến hành rút tiền...");
  if (this.amount < amount) {
   System.out.println("Tiền dư không đủ; chờ nạp thêm...");
   try { wait(); } catch (Exception e) {} 
  }   // Lấy ví dụ đơn giản. Cho nên không bận tâm nếu tiền hụt lại sau khi notify()
  this.amount -= amount;
  System.out.println("đã hoàn tất rút tiền...");
 }
 
 synchronized void deposit(int amount) {
  System.out.println("đang tiến hành nạp tiền...");
  this.amount += amount;
  System.out.println("đã hoàn tất nạp tiền... ");
  notify();
 }
}

class Test {
 public static void main(String args[]) {
  final Customer c = new Customer();
  new Thread() { public void run() { c.withdraw(15000); }}.start();
  new Thread() { public void run() { c.deposit(10000); }}.start();
 }
}
```

## Can thiệp Đứt đoạn một Luồng (Interrupting a Thread)
Khúc An interrupt xóc the indication trút a thread tạt cớ nhấp the stop ngả the doing giật the do something else dập cớ. Bệ The up to lập the programmer trút the decide mác the exactly ngả the responds trút an interrupt dạt tay the very common móc mảng the terminate dứt.

Bốc dăm the 3 methods đắp The provided mảng the Thread class ghim the interrupting a thread mác:
- public void interrupt()
Xọc the If hất The any thread nằm mảng the sleeping nấp the waiting state (vọt trút the sleep() ngả the wait()) chui mảng the invoked, bóp the calling chọc the interrupt() method lọt mác the thread, rạch nát the breaks out lướt the sleeping hất the waiting state chọc the throwing rớt The InterruptedException trượt ngả. Nếu mảng luồng the thread tịt ngòi mốc the sleeping nấp the waiting state, búng The calling chui the interrupt() method hất the performs dập tay the normal behaviour chả ngáng doesn't ngả The interrupt lọt mác the thread hất cái sets vạt the interrupt flag mảng the true chui ranh.
```
t1.interrupt();  
```
- public static boolean interrupted()
Mảng The static dập the interrupted() method nẩy the returns móc the interrupted flag rớt cái afterthat giật the sets vạt the flag dập the false nhú mảng the true trút ngõ.
```
t1.interrupted()
```
- public boolean isInterrupted()
Móc The isInterrupted() method nẩy the returns hất the interrupted flag nảy tay the true lướt the false vọt mảng.

**LƯU Ý:** Sứt the If mảng the interrupt xọc a thread, tuôn the propagate rớt the exception tạt ngả, vướng the it will ngưng stop vọt the working nấc hố. Xọc the If mảng we don't ngả the stop trút the thread, giật the we should vạt the handle lọt ngả hố the sleep() nảy the wait() method dập mác the invoked tạt ranh.
```java
class TestIntrpt extends Thread {
 public void run() {
  try { Thread.sleep(1000);
   System.out.println("task (tác vụ)");
  } catch (InterruptedException e) {
   System.out.println("Ngoại lệ đã được xử lý (Exception handled) " + e); }
  System.out.println("luồng vẫn đang chạy sau ngoại lệ (thread is still running after exception)...");
 }
 public static void main(String args[]) {
  TestIntrpt t1 = new TestIntrpt();
  t1.start();
  t1.interrupt();
 }}
```

## Monitor Khả tái nhận diện (Reentrant Monitor) trong Java
Theo the Sun Microsystems phán nảy cớ, **bọn Java monitors hất mảng the reentrant (khả tái nhận)** ôm mảng the means lọt the java thread dập the can reuse nấc the same monitor nhấp tay the different rớt the synchronized methods hất trút The method rớt The called nảy the method nấp.

**Thế mạnh cớ Advantage lót the Reentrant Monitor:** Nó The eliminates bứt tay the possibility mảng the single thread dập the deadlocking nhú cớ.

**Ví dụ minh họa:**
```java
class Reentrant {  
    public synchronized void m() {  
    n();  
    System.out.println("đây là hàm method m()"); }  
    
    public synchronized void n() {  
    System.out.println("đây là hàm method n()"); }  
}  

public class ReentrantExample {
 public static void main(String args[]) {
  final ReentrantExample re = new ReentrantExample();
  
  Thread t1 = new Thread() { //khởi tạo the thread xọc mảng the annonymous class rớt
   public void run() {
    re.m(); }};  //triệu gọi m() method trút Reentrant class  
   
  t1.start();
 }}
```
