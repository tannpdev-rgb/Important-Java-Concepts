# Mạng lưới (Networking)

Java Networking là khái niệm kết nối hai hay nhiều thiết bị tính toán với nhau để chúng ta có thể chia sẻ các tài nguyên.

Khi các thiết bị tính toán như laptop, máy tính để bàn (desktops), máy chủ (servers), điện thoại thông minh (smartphones), và máy tính bảng (tablets) cùng với một mạng lưới các thiết bị IoT đang không ngừng mở rộng như camera, ổ khóa cửa, chuông cửa, tủ lạnh, hệ thống âm thanh/hình ảnh, bộ điều nhiệt, và các loại cảm biến chia sẻ thông tin và dữ liệu với nhau thì được gọi là networking (mạng).

Lập trình Socket trong Java (Java Socket Programming) cung cấp các phương tiện để chia sẻ dữ liệu giữa nhiều thiết bị tính toán khác nhau.

**Ưu điểm của Java Networking :**
- chia sẻ tài nguyên
- quản lý phần mềm tập trung

**Package java.net Hỗ trợ 2 Giao thức (Protocols):**
- **TCP:** Giao thức Điều khiển Truyền vận (Transmission Control Protocol) cung cấp giao tiếp đáng tin cậy giữa người gửi và người nhận. TCP được sử dụng cùng với Giao thức Internet (Internet Protocol) hay còn gọi là TCP/IP.
- **UDP:** Giao thức Gói Dữ liệu Người dùng (User Datagram Protocol) cung cấp một dịch vụ giao thức không kết nối (connection-less) bằng cách cho phép truyền packet (gói) dữ liệu qua lại giữa hai hay nhiều node (nút) mạng

## Thuật ngữ Mạng Java (Java Networking Terminology)

Một số các thuật ngữ java networking được sử dụng rộng rãi như sau:

**1. IP Address (Địa chỉ IP)**
- IP address là một con số duy nhất được gán cho một node của một mạng, ví dụ 192.168.0.1. Nó được cấu thành từ các octet nằm trong khoảng từ 0 đến 255. Nó là một địa chỉ logic (logical address) có thể bị thay đổi.

**2. Protocol (Giao thức)**
- Một protocol về cơ bản là một tập hợp các quy tắc được tuân theo để tiến hành giao tiếp. Ví dụ: TCP, FTP, Telnet, SMTP, POP, v.v.

**3. Port Number (Số cổng)**
- Port number được sử dụng để định danh duy nhất (uniquely identify) nhiều ứng dụng khác nhau. Nó đóng vai trò là một điểm cuối giao tiếp (communication endpoint) giữa các ứng dụng. Port number được gắn liền với IP address để tiến hành giao tiếp giữa hai ứng dụng.

**4. MAC Address (Địa chỉ MAC)**
- MAC (Media Access Control) Address là một định danh duy nhất của NIC (Network Interface Controller - Bộ điều khiển giao tiếp mạng). Một node mạng có thể có nhiều NIC nhưng mỗi NIC đều có một địa chỉ MAC duy nhất. Sự khác biệt chính giữa địa chỉ MAC và địa chỉ IP là, MAC Address được sử dụng để đảm bảo địa chỉ vật lý (physical address) của máy tính. Nó giúp nhận dạng một cách duy nhất các thiết bị trên mạng. Trong khi IP address được sử dụng để nhận dạng duy nhất kết nối mạng của thiết bị đó trên một mạng lưới.

**5. Socket (Ổ cắm mạng)**
- Một socket là một đầu cuối của quá trình kết nối giao tiếp hai chiều giữa hai ứng dụng đang chạy trên mạng. Cơ chế socket thể hiện một phương thức giao tiếp liên tiến trình (IPC - inter-process communication) bằng cách thiết lập các điểm liên hệ được đặt tên (named contact points), nơi mà việc giao tiếp xảy ra giữa chúng. Một socket bị gắn chặt với một port number để cho tầng (layer) TCP có thể nhận ra được ứng dụng mà dữ liệu dự kiến sẽ gửi đến.

**6. Connection-oriented protocol (Giao thức hướng kết nối)**
- Trong connection-oriented protocol, thông điệp xác nhận (acknowledgement) được gửi đi bởi phía người nhận. Do vậy, nó rất đáng tin cậy nhưng lại chậm. Ví dụ về connection-oriented protocol là TCP.

**7. Connection-less protocol (Giao thức không kết nối)**
- Trong connection-less protocol, thông điệp xác nhận không được gửi đi bởi người nhận. Vì vậy, nó tuy không đáng tin cậy nhưng lại vô cùng nhanh. Ví dụ về connection-less protocol là UDP.

## Các Class Java Networking

Package java.net của ngôn ngữ lập trình Java bao gồm nhiều class khác nhau cung cấp một phương tiện dễ sử dụng để truy cập các tài nguyên mạng. Các classes được đề cập trong package java.net được đưa ra như sau – 

| <!-- -->    | <!-- -->    | <!-- -->    | <!-- -->    | <!-- -->    |
|-------------|-------------|-------------|-------------|-------------|
|Authenticator|CacheRequest|CacheResponse|ContentHandler|CookieHandler|
|CookieManager|DatagramPacket|DatagramSocket|DatagramSocketImpl|InterfaceAddress|
|JarURLConnection|MulticastSocket|InetSocketAddress|InetAddress|Inet4Address|
|Inet6Address|IDN|HttpURLConnection|HttpCookie|NetPermission|
|NetworkInterface|PasswordAuthentication|Proxy|ProxySelector|ResponseCache|
|SecureCacheResponse|ServerSocket|Socket|SocketAddress|SocketImpl|
|SocketPermission|StandardSocketOptions|URI|URL|URLClassLoader|
|URLConnection|URLDecoder|URLEncoder|URLStreamHandler|-|
 
**1. CacheRequest**
- Class CacheRequest được sử dụng trong java bất cứ khi nào có yêu cầu phải lưu trữ (store) tài nguyên (resources) trong ResponseCache. Các objects thuộc class này cung cấp một lợi thế để đối tượng OutputStream lưu trữ data tài nguyên vào trong bộ nhớ đệm (cache). 
 
**2. CookieHandler**
- Class CookieHandler được sử dụng trong Java nhằm implement (triển khai) một callback mechanism cho việc bảo mật (securing up) triển khai chính sách quản lý trạng thái HTTP bên trong protocol handler (bộ xử lý giao thức) của HTTP. Cơ chế (mechanism) quản lý trạng thái HTTP quy định cách thức làm thế nào để gửi HTTP requests và responses.
 
**3. CookieManager**
- Class CookieManager được dùng để cung cấp bản triển khai (implementation) chính xác của CookieHandler. Class này phân chia việc lưu trữ của các cookies ra khỏi các chính sách xoay quanh việc từ chối hay chấp thuận cookies. Một CookieManager bao gồm một CookieStore và một CookiePolicy. 
 
**4. DatagramPacket**
- Class DatagramPacket được sử dụng để cung cấp phương tiện cho việc chuyển thông điệp (messages) không kết nối (connectionless transfer) từ hệ thống này sang hệ thống khác. Class này cung cấp bộ công cụ sản xuất các gói dữ liệu (datagram packets) phục vụ việc truyền phát không kết nối bằng cách tận dụng class datagram socket.
 
**5. InetAddress**
- Class InetAddress được sử dụng để cung cấp các phương thức get ra địa chỉ IP của bất kỳ hostname nào. Một IP address được biểu thị bằng một con số không dấu dài 32-bit hoặc 128-bit. InetAddress có khả năng xử lý cả địa chỉ IPv4 và IPv6. 
 
**6. Server Socket**
- Class ServerSocket được sử dụng để triển khai quá trình thực thi hệ thống mang tính độc lập đối với máy chủ của một hệ Socket Connection dạng client/server. Hàm khởi tạo (constructor) đối với class ServerSocket sẽ quăng ra lỗi exception nếu nó không thể nghe thấu (listen) trên một cái port được chỉ định. Ví dụ – nó sẽ ném thẳng lỗi exception ra khi nào cái port đấy đang có một ứng dụng khác xài chung.
 
**7. Socket**
- Lớp Socket được dùng cho vấn đề thiết kế các đối tượng socket mang tác dụng chống lưng cho user trong lúc đang áp dụng tất thảy mọi thao tác socket cơ bản nền tảng nhất. Phía user cũng dễ dàng xài tới nhiều nhóm hành động cấu hình networking chẳng hạn gửi đi (sending), đọc quét dữ kiện (reading data), cùng chặn đứng cắt liên kết (closing connections). Cứ mỗi cái đối tượng Socket định hình được thông qua dòng khuôn java.net.Socket class dính dáng nối dây chính xác dứt khoát chặt chẽ cùng mỗi 1 remote host (máy chủ điều khiển ngầm); nhằm bám nối đi tới mạn sườn một tay host khác, gã user buộc lòng cần tạo nên cái new socket object khác.
 
**8. DatagramSocket**
- DatagramSocket class sắm vai một dạng network socket chuyên tâm cung cấp nhánh điểm không có kết nối cho nỗ lực đẩy nhận gói tin. Mỗi lượt packet đánh bọc đi xuất xứ trên bệ phóng datagram socket bị bẻ gãy đưa riêng biệt rành mạch và đáp thẳng xuống. Rộng cửa hơn nữa thì class này được trọng dụng lặp lại theo thói quen đẩy gửi phân phát quảng bá (broadcast) khối lượng luồng lượng thông tin trôi trên đấy. Khối cơ Datagram Sockets sắm vai đại diện mảng cơ cấu chiêu bài mượn luồng giao tiếp network communication bằng mảng UDP nhường sân mạn hệ thống dạng TCP.
 
**9. Proxy**
- Bộ khuôn a proxy khoác màu sắc bất biến (changeless object) đứng ngang hàng tương tư như phương cách cỗ máy công cụ (tool) hỗ trợ đắc lực chương trình program, hệ thống ngầm, gánh bảo kê bảo trợ nguồn số liệu data của mấy vị user song đôi cả bộ đám computer chìm. Nó dựng ranh giới hành vi tường rào kín giữa các bộ não computer với cư dân mạng (internet users). Gói thể A Proxy Object làm bộ mặt trình phác lại tập The Proxy settings có sứ mạng trút lên chồng dính vào với mối dây connection.
 
**10. URL**
- Lớp Class URL phía bề sâu cấu hình Java gánh vác vai lối đâm vào cổng (entry point) chạm mặt chùm những khu mỏ kho tàng chứa luồng sources trôi dạt khơi trên nẻo chốn internet. Class URL ngụ ý mô phỏng hình khối của Uniform Resource Locator, như vạch đích chỉ lối đâm về hướng “resource” trên hệ thống cỗ máy World Wide Web. Một dạng rễ source đủ khả năng phác họa ra hình tệp file tĩnh đơn xơ rỗng hoặc vùng thư mục directory, chả thế thì nó cũng gánh hình chiếu hắt ra cấu hình dữ liệu phức tạp thâm sâu khó nhằn nhắm tới truy nã the database hay mớ a search engine.
 
**11. URLConnection**
- Khối cấu Class URLConnection cắm chốt của Java đứng dạng màng sương mù trừu tượng (abstract class) nhào nặn lên dạng dây neo gắn nguồn the resource trút vào cấu hình bởi hình dạng cái URL sương sương tợ như thế. Lớp URLConnection túc trực sẵn hỗ trợ nòng cốt nhắm hai phương diện (two distinct yet interrelated purposes). Chiếu một góc nó gán quyền điều phối khống chế nẻo qua lại kết dính hệ server(ưu tiên an HTTP server) đầm đậm hơn vế dòng a URL class. Sang bề thứ hai, bằng mảng a URLConnection, cá thể user thả sức truy kích thanh tra cỗ header tải đẩy theo dải luồng server để dễ lèo lái quăng ra chiêu ứng đối phản xạ. Cá nhân user hoàn toàn quyền hiệu chỉnh sắp hàng các vùng gác header fields dùng đưa đòn đẩy request qua ngõ phía the client dựa dẫm mốc chốt hệ The URLConnection.


## Các Interface trong Java Networking

Gói chứa mâm the java.net package dắt kèm một rổ rải rác lấm tấm dăm the interfaces cung cứng đủ trò đụng chạm vọc vạch chọc ngoáy dễ làm nhắm bám vô hệ the network resources. Chùm Interfaces chen chân núp mảng java.net package rải chiếu bảng dưới đây – 

**1. CookiePolicy**
- Hệ The CookiePolicy interface nằm nép tại khối java.net package trưng xuất cái mâm the classes phụ việc the implementing hằng hà sa số đám mảng mớ the networking applications khác nhau. Hệ thống tự thân phán lệnh chốt sổ xem hội cookies dính dớp loại nào sẽ được nới rào đón vô còn thứ bỏ đi nào bắt lôi tống hất ra xó the rejected. Tại mặt CookiePolicy, tồn đọng 3 bản phác họa triển khai nòng cốt policy theo mặc định pre-defined trôi nổi, với gã gọi đích ACCEPT_ALL, cõi ACCEPT_NONE, và dạng thù hình vóc dáng ACCEPT_ORIGINAL_SERVER.
 
**2. CookieStore**
- Đống lùi A CookieStore đội dạng Interface biểu hình kho đầm địa điểm the storage space (không gian chứa chấp) tống lấp cookies. Khối CookieManager trút nhập chắp và vá cookies vào the CookieStore đáp chả nhịp nảy the HTTP response và móc túi moi The cookies khỏi mâm CookieStore qua từng dịp The HTTP request nhảy cóc gõ cửa.
 
**3. FileNameMap**
- Trục The FileNameMap interface thuần nét giao diện đơn sắc mỏng uncomplicated interface đem trình làng the tool đắp nên đường vạch họa file name chung đôi the MIME type string. Dải FileNameMap xạc điện a filename map (hệ phái được tạc bằng mảng mimetable) rút dây nẩy dội the data file lên.
 
**4. SocketOption**
- Interface SocketOption gieo gánh trợ cánh đính mác user để lèo lái the sockets chạy bám biên lối the behavior. Năng lặp lại trúng lúc, việc vun đắp nặn ra hình thù vóc dáng the necessary features lồng sockets được coi vô vàn the essential. Màng bọc the SocketOptions cấp giấy đi cho the user đơm đặt cấu tứ nhiều nẻo mảng vóc dáng various standard options (chọn lựa thuộc hệ tiêu chuẩn).
 
**5. SocketImplFactory**
- Vỏ The SocketImplFactory interface thiết chuẩn a factory ứng mâm dàn the SocketImpl instances. Nó chuyên giao nhiệm chức bởi socket class cày cấu đúc dựng mớ a socket implementations thực thi vô số nẻo a various policies (tôn chỉ thủ tục).
 
**6. ProtocolFamily**
- Hình thức Interface hiện đại thân diễn một dải gia tộc nếp nhà phả hệ dính dòng a communication protocols. Vỏ The ProtocolFamily interface ôm chầm lấy cái túi a method định nhãn bám mốc ranh giới the name(), nhả trả hồi the name định dạng quy củ phả hệ rễ a protocol family.


## Lập trình Java Socket

Bản chất dòng the Java Socket programming bám dính lấy việc giăng bẫy mồi communication chạy qua nẻo nhịp bước the applications tản nhánh đa hệ the JRE (môi trường). Nhánh Java Socket programming chia cành hoặc the connection-oriented hoặc là the connection-less rành rẽ.

Dòng classes thuộc hệ Socket song đôi với ServerSocket ứng dụng cho ngạch nòng cốt lập trình connection-oriented socket programming còn chùm classes DatagramSocket đi cặp DatagramPacket vinh quy nằm ứng vế mạch đập nòng lập trình connection-less socket programming.

Nguyên thể the client ứng chiến ranh giới socket programming buộc lòng nắm vững hai mốc xích báo (two information):
1. IP Address trực thuộc hệ Server
2. Port number.

### Class Socket :

Bộ a socket thu về nghĩa hẹp gói ghém làm endpoint cho mảng lưới xâu chuỗi luân chuyển (communications) liên máy the machines. Vạch lớp Socket class được chưng dụng lấy nặn khối the a socket.

![socket-programming](https://user-images.githubusercontent.com/2780145/68625991-64f2e400-0500-11ea-9616-3702cb213cdd.png)

**Các phương thức đặc thù (Important methods) :**
|Phương thức (Method)|Mô tả (Description)|
|-|-|
|void connect(SocketAddress host, int timeout)|móc gắn kết (connects) the socket nương theo đúng cái the particularized host|
|int getPort()|trả số the port nằm ranh giới mà the socket vướng mắc kẹt (pinned) lên hệ the remote machine|
|InetAddress getInetAddress()|hồi xuất vị trí (location) dính mốc con computer kia trạm mà the socket neo đậu connected|
|int getLocalPort()|cấp con the port nơi tọa lạc the socket đáp đậu joined thẳng tới bộ the local machine|
|SocketAddress getRemoteSocketAddress()|hiển the location địa điểm của the remote socket|
|InputStream getInputStream()|hoàn cái the input stream lọt từ the socket|
|OutputStream getOutputStream()|bơm trút the output stream nôn ra the socket|
|synchronized void close()|bấm nút đóng kín chốt cửa the socket|

### Class ServerSocket :

Vạch ngang class ServerSocket trưng bày xài vọc mớ a server socket. Chùm đối tượng trên đảm nhận móc dính dây (establish) cầu mây the communication bủa lưới qua the clients.

**Các phương thức đặc thù :**
|Phương thức|Mô tả|
|-|-|
|int getLocalPort()|khai trả port nơi mà cỗ the server socket nằm theo dõi monitoring|
|void setSoTimeout(int timeout)|đắp thời lượng time-out dứt mà cái the server socket chịu đóng băng chờ hố a client trong the accept() method|
|Socket accept()|ngồi trực the incoming client; rớt the socket qua mạn kết nối đan cầu connection đè hệ the server cặp với the client|
|void bind(SocketAddress host, int backlog)|hàn the socket chắp dính a the particularized server chêm dồn port trong lõi object gắn mác the SocketAddress|
|synchronized void close()|niêm phong the server socket đóng|

## Ví dụ về Lập trình Java Socket

### Việc thiết lập Server :
```java
ServerSocket ss = new ServerSocket(6666);  
Socket s = ss.accept(); //cắm chốt connection nằm phục waits cho ông the client   
```

### Việc thiết lập Client :
```java
Socket s = new Socket("localhost",6666);  
```

### Một ví dụ đơn giản dạng Socket mô phỏng client bắn dòng văn bản the text; còn the server đón bắt the nhận và in ấn nó.

#### Phía SERVER
```java
ServerSocket ss = new ServerSocket(6666);  
Socket s=ss.accept(); //thiết lập connection   
DataInputStream dis = new DataInputStream(s.getInputStream());  
String  str = (String)dis.readUTF();  
System.out.println("message= "+str);  
ss.close();  
```

#### Phía CLIENT
```java
Socket s = new Socket("localhost",6666);  
DataOutputStream dout = new DataOutputStream(s.getOutputStream());  
dout.writeUTF("Hello Server");  
dout.flush();  
dout.close();  
s.close();  
```

Bật tung ngỏ nắp hai mảng command prompts (Cửa sổ dòng lệnh) cắm cày (execute) the program
Chờ rãnh tay cái luồng chạy client application, dòng the message trổ nhô phơi the server console.

### Một ví dụ khá phức tạp hệ Socket rành mốc ngấn
- Khúc đầu (First), client tung dòng the write đánh bóng server; the server tóm gọn mảng the receive thả phác the print.
- Về sau (Then), server dập đợt write giội the client; the client ăn cái the receive tung đè the print.

#### Cục SERVER
```java
ServerSocket ss = new ServerSocket(3333);
Socket s = ss.accept();
DataInputStream din = new DataInputStream(s.getInputStream());
DataOutputStream dout = new DataOutputStream(s.getOutputStream());
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

String str = "", str2 = "";
while (!str.equals("stop")) {
    str = din.readUTF();
    System.out.println("client says: " + str);
    str2 = br.readLine();
    dout.writeUTF(str2);
    dout.flush();
}
din.close();
s.close();
ss.close();
```

#### Khúc CLIENT
```java
Socket s = new Socket("localhost", 3333);
DataInputStream din = new DataInputStream(s.getInputStream());
DataOutputStream dout = new DataOutputStream(s.getOutputStream());
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

String str = "", str2 = "";
while (!str.equals("stop")) {
    str = br.readLine();
    dout.writeUTF(str);
    dout.flush();
    str2 = din.readUTF();
    System.out.println("Server says: " + str2);
}

dout.close();
s.close();
```
