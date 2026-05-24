# Files và I/O trong Java

Gói java.io chứa gần như mọi class cần thiết để thực thi việc đầu vào và đầu ra (input và output hay I/O) trong Java. Tất cả những stream (luồng) này biểu diễn cho một nguồn input (input source) và một đích đến output (output destination). Stream trong package java.io hỗ trợ cho rất nhiều dạng dữ liệu (data) như kiểu nguyên thủy (primitives), đối tượng (object), các ký tự khu vực (localized characters), v.v. Java mang tới những hỗ trợ mạnh mẽ và rất linh hoạt đối với những loại tác vụ I/O có liên quan tới file và hệ thống mạng (networks).

## Sơ đồ Phân cấp I/O Class trong Java

![java io class hierarchy](https://user-images.githubusercontent.com/2780145/34911563-14813348-f8f3-11e7-87ef-4c8f589bbdf5.png)

## Stream (Luồng)

Stream có thể được hiểu là một chuỗi (sequence) các dữ liệu. Có hai loại Streams chính là:

<ul class="list">
<li><p><b>InputStream</b> − Dùng InputStream để đọc dữ liệu vào từ một nguồn đầu vào (source).</p></li>
<li><p><b>OutputStream</b> − Dùng OutputStream để viết dữ liệu đưa tới một điểm nhận đầu ra (destination).</p></li>
</ul>

### Byte Streams (Luồng Byte)

Java byte streams được sử dụng để tiến hành input và output cho các 8-bit byte. Mặc dù có rất nhiều classes có liên quan tới byte streams thế nhưng các class được sử dụng thường xuyên nhất chính là, **FileInputStream** và **FileOutputStream**.

### Character Streams (Luồng Ký tự)

Java **Byte** streams được sử dụng để tiến hành input và output cho dạng 8-bit byte, trong khi đó Java **Character** streams được sử dụng để tiến hành việc input và output cho dạng 16-bit unicode. Mặc dù có rất nhiều classes có liên quan tới character streams thế nhưng các class được sử dụng thường xuyên nhất là, **FileReader** và **FileWriter**.

Mặc dù trong thực tế nội tại FileReader sử dụng chức năng của FileInputStream và FileWriter sử dụng chức năng của FileOutputStream nhưng ở đây điểm khác biệt mấu chốt là hàm FileReader thực thi đọc 2 bytes mỗi lần chạy và FileWriter thực thi in/viết 2 bytes mỗi lần chạy.

## Vì sao lại cần có Byte và Character Streams

Stream là phương thức cho phép thao tác truy cập file diễn ra tuần tự. Phía byte stream sẽ cho phép truy cập file lần lượt qua mỗi byte. Dạng byte stream cũng rất phù hợp với đủ mọi thể loại tệp, tuy nhiên dạng file văn bản (text file) thì lại không thích hợp sử dụng cấu trúc stream này cho lắm. Lấy ví dụ, nếu file đang lưu sử dụng phương pháp encoding mã unicode và mỗi ký tự lại được đại diện bởi tận hai byte, kiểu byte stream lúc này lại tách hai thành phần riêng biệt này ra và sau cùng bạn vẫn sẽ cần phải tự tay thực thi công tác chuyển đổi.

Kiểu character stream có thể đem sử dụng đọc file tuần tự từng ký tự một. Phía character stream sẽ cần phải được cung cấp sẵn chuẩn mã hóa file (file's encoding) nhằm để có thể vận hành ổn định.

## Standard Streams (Luồng Tiêu chuẩn)

Tất cả các ngôn ngữ lập trình đều cung cấp các cơ chế hỗ trợ ứng với standard I/O, nơi mà program của người dùng có thể nạp input thông qua bàn phím và rồi sinh ra output ở trên màn hình máy vi tính. Java cung cấp sẵn ba mẫu standard streams sau

<ul class="list">
<li><p><b>Standard Input (Đầu vào chuẩn)</b> − Nhánh này dùng để tiếp nạp dữ liệu tới thẳng program của người dùng và thông thường keyboard sẽ dùng làm nguồn input stream tiêu chuẩn cũng như được mô tả thành cấu trúc <b>System.in</b>.</p></li>
<li><p><b>Standard Output (Đầu ra chuẩn)</b> − Nhánh này có tác dụng nạp đầu ra (output) là các dữ liệu do người dùng đưa vào program và theo thường lệ màn hình vi tính sẽ đóng vai trò tiêu chuẩn ứng với luồng output stream này, cấu trúc đại diện sẽ là <b>System.out</b>.</p></li>
<li><p><b>Standard Error (Lỗi tiêu chuẩn)</b> − Nhánh này giữ nhiệm vụ trả kết quả đầu ra là những dòng thông tin lỗi thu được từ chính program của người sử dụng và đại loại màn hình vi tính tiếp tục là công cụ đáp ứng luồng tiêu chuẩn thông tin lỗi (standard error stream) dưới dạng mô phỏng là <b>System.err</b>.</p></li>
</ul>

## Đọc và Ghi Files (Reading and Writing Files)

**InputStream** được sử dụng nhằm mục đích tiến hành đọc chuỗi thông tin tính từ nguồn tạo (source) và nhánh **OutputStream** được dùng cho khâu viết dữ liệu đưa về điểm phát sinh kết quả đích (destination). Hai stream tối quan trọng ứng với việc này là **FileInputStream** và **FileOutputStream**.

## FileInputStream

Stream này giữ nhiệm vụ tiếp nhận quá trình đọc dữ liệu đến từ phía file. Objects hoàn toàn cho phép sinh bằng câu từ khóa có chức năng new bên cạnh sự sẵn có nhờ rất nhiều những dạng constructor khác nhau.

Constructor dưới đây yêu cầu nhận truyền vào thông tin file name ở chuẩn dữ liệu kiểu chuỗi (string) qua đấy sinh một đối tượng input stream nhằm hướng đến quá trình đọc file.
```java
InputStream f = new FileInputStream("C:/java/hello");
```
Dạng constructor tiếp nối theo sau cần phải truyền object ứng với loại file vào với tham vọng khởi tạo một bộ object cấu trúc dạng input stream để tiến hành việc đọc luồng nội dung từ trong file. Mới bước vào đầu tiên ta sẽ phát sinh cấu trúc biến file object qua lời gọi dùng function File().
```java
File f = new File("C:/java/hello");
InputStream f = new FileInputStream(f);
```

Ngay sau lúc đã trong tay đối tượng InputStream, Bạn đã sẵn sàng gọi vô số các dạng thức chức năng methods khác nhau :

<table class="table table-bordered">
<tbody><tr>
<th>STT</th>
<th style="text-align:center;">Phương thức &amp; Mô tả (Method &amp; Description)</th>
</tr>
<tr>
<td class="ts">1</td>
<td><p><b>public void close() throws IOException{}</b></p>
<p>Method đóng đứt chuỗi file output stream hiện thực. Yêu cầu thả lỏng (Releases) các phần dữ kiện làm tốn hao tài nguyên hệ thống (system resources) liên quan. Ném phát một ngoại lệ kiểu IOException.</p>
</td>
</tr>
<tr>
<td class="ts">2</td>
<td><p><b>protected void finalize()throws IOException {}</b></p>
<p>Method xử lý thao tác gọi ngắt toàn diện làm dọn sạch sẽ cầu nối (connection) đưa tới file. Giữ vững niềm tin quá trình method close của dòng file output stream lúc bấy giờ chịu lệnh nảy sinh ở bối cảnh đã dứt điểm sạch không lưu lại mảy may dấu hiệu tham chiếu (references) móc nối luồng stream này. Ném ra thể loại lỗi ngoại lệ chuẩn IOException.</p>
</td>
</tr>
<tr>
<td class="ts">3</td>
<td><p><b>public int read(int r)throws IOException{}</b></p>
<p>Method hỗ trợ đọc các byte chi tiết về mặt số liệu dữ kiện từ trong InputStream. Trả về đối tượng ở chuẩn kiểu int. Trả phần byte nối tiếp mang thông tin về dữ liệu và điểm chốt kết luận sẽ được thu lại là -1 khi nó đã đạt mức đi đến tận chóp mút của chuỗi báo mốc cuối mảng file (end of the file).</p> 
</td>
</tr>
<tr>
<td class="ts">4</td>
<td><p><b>public int read(byte[] r) throws IOException{}</b></p>
<p>Method hoạt động tiến hành thao tác đọc thông lượng giá trị r.length bytes kéo trực diện đầu input stream để tuồn toàn bộ sang mảng arr (array). Quá trình hoàn thiện gửi gắm tổng con số dung lượng ở dạng thức bytes đã xem. Tại thời điểm nó chạm vùng đáy end of the file, biến cố ghi dấu thu lại giá trị trả biểu tượng -1.</p>
</td>
</tr>
<tr>
<td class="ts">5</td>
<td><p><b>public int available() throws IOException{}</b></p>
<p>Phản ánh lại tổng số vạch đếm bytes đủ quyền hạn nhận lệnh bóc tác đọc thẳng nguồn đầu tư nằm bên nhánh luồng file input stream này. Xuất báo kết quả con số qua vỏ bọc hệ sinh thái kiểu int.</p>
</td>
</tr>
</tbody></table>

Những lớp input streams chủ chốt khác :
- ByteArrayInputStream
- DataInputStream

## FileOutputStream

FileOutputStream được dùng với tác vụ sinh khởi file mới (create a file) kết hợp thao tác truyền thông tin (write data) đưa sát vách tường chứa nội dung bên trong file ấy. Luồng cấu trúc sẽ lập nên một khuôn dạng file chuẩn, miễn là trường hợp chưa từng có xuất hiện trước kia trên cõi mạng bộ nhớ, để mà thông dòng khởi động sẵn sàng chào đón dữ liệu đầu ra đổ vào.

Constructor mô phỏng bên dưới lấy truyền đưa thuộc tính tên file name theo chuẩn cấu trúc chuỗi (string) đảm đương khởi dựng khuôn hình đối tượng có gốc dính dáng hệ input stream cho phép việc ghi/vẽ cấu tứ vào file
```java
OutputStream f = new FileOutputStream("C:/java/hello") 
```
Loạt constructor xếp lượt đằng sau nạp dữ liệu truyền tham số với cấu hình lớp file object nhắm vào đích xây dựng object luồng nhánh dòng xuất (output stream) nhằm mục tiêu ghi thông tin tuồn dẫn vô file. Tại khởi trạm chặng đầu, chúng tôi tự khởi cấu lên dòng đối tượng mang cốt file object ứng dụng chức năng ngầm định hàm File().
```java
File f = new File("C:/java/hello");
OutputStream f = new FileOutputStream(f);
```

Khi bạn đã đạt trong tay bộ khuôn object hệ dòng InputStream, Bạn được cung cấp kho tàng vận dụng hàng loại những biến chiêu phương thức methods :

<table class="table table-bordered">
<tbody><tr>
<th>STT</th>
<th style="text-align:center;">Phương thức &amp; Mô tả (Method &amp; Description)</th>
</tr>
<tr>
<td class="ts">1</td>
<td><p><b>public void close() throws IOException{}</b></p>
<p>Phương thức phát tín hiệu khóa kết trói gọn file output stream. Buông xả rỗng tuếch khối tài nguyên phần cứng hệ thống hiện thời còn bám dính cùng cấu tạo file. Xuất bản ngoại lệ kiểu IOException.</p>
</td>
</tr>
<tr>
<td class="ts">2</td>
<td><p><b>protected void finalize()throws IOException {}</b></p>
<p>Phương thức chịu nghĩa vụ rửa quét luồng giao tiếp đưa đường cho kết nối dính dáng file. Làm nhiệm vụ chốt bảo chứng hàm close của tuyến file output stream tự giác chịu gọi báo đánh tiếng khi mọi cầu neo điểm tựa references đi theo cái stream triệt để tiêu tan. Châm ngòi nổ phát sinh IOException.</p>
</td>
</tr>
<tr>
<td class="ts">3</td>
<td><p><b>public void write(int w)throws IOException{}</b></p>
<p>Loại method thi hành nét đục viết khối byte chỉ định thâm nhập hòa nhịp tuyến output stream.</p>
</td>
</tr>
<tr>
<td class="ts">4</td>
<td><p><b>public void write(byte[] w)</b></p>
<p>Tiến trình khắc chữ thông qua mức dung lượng kích cỡ w.length bytes chuyển trích ly ra mảng array hệ quy chiếu mang tính chất byte đưa ngắm tới mục tiêu rổ OutputStream.</p>
</td>
</tr>
</tbody></table>

Các chi phái output streams hệ trọng khác :
- ByteArrayOutputStream
- DataOutputStream

## Toàn tập Ví dụ Hoàn thiện (Complete Example)
Tập hợp mã sau chịu thiên chức khởi tạo file `test.txt` tiếp đến đưa dẫn đường truyền thông số chuỗi number hệ nhị phân (binary format) khép kín ghi thẳng đè vào. Bằng với thành quả y đúc đầu ra sẽ soi bóng hiện chiếu xuất trình diện trên vùng hiển thị của ngõ màn ảnh cổng stdout.
```java
import java.io.*;
public class fileStreamTest {

   public static void main(String args[]) {
   
      try {
         byte bWrite [] = {11,21,3,40,5};
         OutputStream os = new FileOutputStream("test.txt");
         for(int x = 0; x < bWrite.length ; x++) {
            os.write( bWrite[x] );   // tiến hành quá trình viết the bytes
         }
         os.close();
     
         InputStream is = new FileInputStream("test.txt");
         int size = is.available();

         for(int i = 0; i < size; i++) {
            System.out.print((char)is.read() + "  ");
         }
         is.close();
      } catch (IOException e) {
         System.out.print("Exception");
      }	
   }
}
```

## Lớp Java Console (Java Console Class)
Class khung Java Console giữ khả năng chuyên môn kéo gom thông tin thu dập dạng đầu vào nằm vùng ranh giới console. Nó đưa ra đường lối các method làm dịch vụ quét chữ đọc các chuỗi văn bản thuần (texts) cùng dữ liệu bảo mật mật khẩu (passwords). Trong tình huống bạn dò đọc mật khẩu qua cơ cấu bộ phận của Console class, nội dung của nó tuyệt đối miễn phát hình che mờ ánh nhìn xuất hiện bên ngoài thị giác user tiếp cận. Tổ chức thành phần nền tảng java.io.Console class nội tại có sẵn đường dây thắt chặt móc nối với system console.
**Ví dụ :**
```java
import java.io.Console;
class ReadPasswordTest {
    public static void main(String args[]) {
        Console c = System.console();
        System.out.println("Nhập vào mật khẩu: ");
        char[] ch = c.readPassword();
        String pass = String.valueOf(ch); //chuyển đổi chuỗi mảng kiểu char biến về chuỗi string    
        System.out.println("Mật khẩu cung cấp là: " + pass);
    }
}
```


## Điều hướng File và chức năng I/O (File Navigation and I/O)

Các cấu tạo tập hợp dòng class khác dùng cho công đoạn điều phối di chuyển Navigation gắn kèm chức năng I/O.
- File Class
- FileReader Class
- FileWriter Class

## Thư mục chứa trong Java (Directories in Java)

Thư mục chứa (directory) mang đặc trưng bản ngã y hệt một File mà ở ngay giữa lòng trung tâm tự do trữ lại kho danh sách khổng lồ dính đến đủ dạng nhóm tệp (files) kể cả hằng hà sa số các bậc thư mục khác (directories). Bạn có thể khai thác lớp đối tượng **File** sinh ra rổ khay phân loại hệ thống lưu trữ directories, phục vụ công tác trút sổ tung bảng thống kê cho vô số dạng thư mục gốc rễ lọt sẵn ngả lưng gọn chẽ trong cùng một directory nhất định.

## Tạo Thư mục mới (Creating Directories)

<ul class="list">
<li><p>Chiêu bài function <b>mkdir()</b> xuất chinh gọi mầm chồi khai thiên một gốc thư mục directory, kết cục mang tính quả ngọt trả giá trị true nhân ngày đăng quang, thế và đem kết trái false gắn lên bảng lụn bại (failure). Sự thất bại phác họa bóc trần đường truyền (path) nhắm tới trỏ điểm đối tượng File có thật mồn một, bằng không directory nhận lãnh lệnh đứt gánh chưa sinh trào ra đời tại lẽ do hoàn nguyên dải mạch con đường path gốc tính thời điểm hiện nay trống rỗng chẳng hề khai căn hình thành.</p></li>
<li><p>Với hệ sinh thái <b>mkdirs()</b> sinh nảy ra dòng chảy đan xen một directory đồng dạng thâu tóm nhồi nhét mọi nút thắt cha mẹ parents gánh chung directory ấy.</p></li>
</ul>

Chùm khối code mô tả dưới xây đắp sinh hình "/tmp/user/java/bin" directory.
```java
import java.io.File;
public class CreateDir {

   public static void main(String args[]) {
      String dirname = "/tmp/user/java/bin";
      File d = new File(dirname);
      
      // Tạo một thư mục (directory) lúc này.
      d.mkdirs();
   }
}
```

**LƯU Ý :** Java sẽ thực hiện cơ chế âm thầm tự động thay bạn cáng đáng thu dọn cục mớ bùng nhùng đường ranh giới khoảng cách path separators trên hệ điều hành UNIX rẽ nhánh Windows bám theo bộ luật chuẩn conventions. Có đưa chiêu bôi đường viền chéo tới bằng phím forward slash (/) gắn cho Windows bản version đặc hữu Java, đoạn path vẫn vẹn toàn nhận được phương thức phân rã giải quyết sạch sẽ ổn thỏa (resolve correctly).

## Liệt kê các Thư mục (Listing Directories)

Bản thân bạn đủ cơ sở ứng biến linh hoạt triệu hồi dòng chảy list( ) method ban phát từ kho mâm đối tượng File đặng trích phả hệ liệt kê tuôn tuốt mọi mạch ngầm file cùng nhóm thư mục phơi bày rõ nét định vị ngọn nguồn thuộc directory rọi soi y khuôn dòng ví dụ lột tả như vầy.
```java
import java.io.File;
public class ReadDir {

   public static void main(String[] args) {
      File file = null;
      String[] paths;
  
      try {      
         // hình thành khuôn đúc object nạp mới new file
         file = new File("/tmp");

         // danh sách chùm tia mảng nhóm hệ array thâu files ghép directory
         paths = file.list();

         // phục vụ quét ngần ấy tên name nằm chung dải con đường path array
         for(String path:paths) {
            // phác họa phun in filename trộn lẫn cấu thành tên directory name
            System.out.println(path);
         }
      } catch (Exception e) {
         // lỡ như vướng phải hố lỗi error mọc ra
         e.printStackTrace();
      }
   }
}
```
