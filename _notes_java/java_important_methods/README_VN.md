# Các Phương thức Quan trọng trong Java

Các Phương thức Quan trọng của nhiều Classes khác nhau trong Java kèm theo mô tả. 

LƯU Ý : Các phương thức được đề cập bên dưới chỉ là những phương thức quan trọng nhất, chứ không phải là toàn bộ phương thức.

## Các Phương thức của Class Number :

<table class="alt">
<tbody><tr><th>STT</th><th>Phương thức (Method)</th><th>Mô tả (Description)</th></tr>
<tr>
<td>1</td>
<td>xxxValue()</td><td>
Chuyển đổi giá trị của đối tượng Number <i>này</i> thành kiểu dữ liệu xxx và trả về nó.
</td>
</tr>
<tr>
<td >2</td>
<td>compareTo()</td><td>
So sánh đối tượng Number <i>này</i> với đối số (argument) truyền vào.
</td>
</tr>
<tr>
<td >3</td>
<td>equals()</td><td>
Xác định xem đối tượng Number <i>này</i> có bằng với đối số truyền vào hay không.
</td>
</tr>
<tr>
<td >4</td>
<td>valueOf()</td><td>
Trả về một đối tượng Integer chứa giá trị của primitive được chỉ định.
</td>
</tr>
<tr>
<td >5</td>
<td>toString()</td><td>
Trả về một đối tượng String đại diện cho giá trị của một int hoặc Integer được chỉ định.
</td>
</tr>
<tr>
<td >6</td>
<td>parseInt()</td><td>
Phương thức này được sử dụng để lấy kiểu dữ liệu primitive của một String nhất định.
</td>
</tr>
<tr>
<td >7</td>
<td>abs()</td><td>
Trả về giá trị tuyệt đối (absolute value) của đối số.
</td>
</tr>
<tr>
<td >8</td>
<td>ceil()</td><td>
Trả về số nguyên nhỏ nhất lớn hơn hoặc bằng với đối số. Giá trị trả về dưới dạng double.
</td>
</tr>
<tr>
<td >9</td>
<td>floor()</td><td>
Trả về số nguyên lớn nhất nhỏ hơn hoặc bằng với đối số. Giá trị trả về dưới dạng double.
</td>
</tr>
<tr>
<td >10</td>
<td>rint()</td><td>
Trả về số nguyên có giá trị gần nhất với đối số. Giá trị trả về dưới dạng double.
</td>
</tr>
<tr>
<td >11</td>
<td>round()</td><td>
Trả về giá trị long hoặc int gần nhất đối với đối số, được chỉ định dựa trên kiểu trả về của phương thức.
</td>
</tr>
<tr>
<td >12</td>
<td>min()</td><td>
Trả về số nhỏ hơn trong hai đối số.
</td>
</tr>
<tr>
<td >13</td>
<td>max()</td><td>
Trả về số lớn hơn trong hai đối số.
</td>
</tr>
<tr>
<td >14</td>
<td>exp()</td><td>
Trả về lũy thừa cơ số e (của logarit tự nhiên) với số mũ là giá trị của đối số.
</td>
</tr>
<tr>
<td >15</td>
<td>log()</td><td>
Trả về logarit tự nhiên (natural logarithm) của đối số.
</td>
</tr>
<tr>
<td >16</td>
<td>pow()</td><td>
Trả về giá trị của đối số thứ nhất lũy thừa đối số thứ hai.
</td>
</tr>
<tr>
<td >17</td>
<td>sqrt()</td><td>
Trả về căn bậc hai (square root) của đối số.
</td>
</tr>
<tr>
<td >18</td>
<td>sin()</td><td>
Trả về giá trị sine của một giá trị double được chỉ định.
</td>
</tr>
<tr>
<td >19</td>
<td>cos()</td><td>
Trả về giá trị cosine của một giá trị double được chỉ định.
</td>
</tr>
<tr>
<td >20</td>
<td>tan()</td><td>
Trả về giá trị tangent của một giá trị double được chỉ định.
</td>
</tr>
<tr>
<td >21</td>
<td>asin()</td><td>
Trả về giá trị arcsine của một giá trị double được chỉ định.
</td>
</tr>
<tr>
<td >22</td>
<td>acos()</td><td>
Trả về giá trị arccosine của một giá trị double được chỉ định.
</td>
</tr>
<tr>
<td >23</td>
<td>atan()</td><td>
Trả về giá trị arctangent của một giá trị double được chỉ định.
</td>
</tr>
<tr>
<td >24</td>
<td>atan2()</td><td>
Chuyển đổi tọa độ Đề-các (rectangular coordinates) (x, y) sang tọa độ cực (polar coordinate) (r, theta) và trả về theta.
</td>
</tr>
<tr>
<td >25</td>
<td>toDegrees()</td><td>
Chuyển đổi đối số sang độ (degrees).
</td>
</tr>
<tr>
<td >26</td>
<td>toRadians()</td><td>
Chuyển đổi đối số sang radian.
</td>
</tr>
<tr>
<td >27</td>
<td>random()</td><td>
Trả về một số ngẫu nhiên.
</td>
</tr>
</tbody></table>

LƯU Ý : Hầu hết các phương thức trên thuộc về java.lang.Math và java.lang.Number

## Các Phương thức của Class Character :

<table class="alt">
<tbody><tr><th>STT</th><th>Phương thức (Method)</th><th>Mô tả (Description)</th></tr>
<tr>
<td>1</td>
<td>isLetter()</td><td>
Xác định xem giá trị char được chỉ định có phải là một chữ cái hay không.</td>
</tr>
<tr>
<td>2</td>
<td>isDigit()</td><td>
Xác định xem giá trị char được chỉ định có phải là một chữ số hay không.</td>
</tr>
<tr>
<td>3</td>
<td>isWhitespace()</td><td>
Xác định xem giá trị char được chỉ định có phải là khoảng trắng (white space) hay không.</td>
</tr>
<tr>
<td>4</td>
<td>isUpperCase()</td><td>
Xác định xem giá trị char được chỉ định có phải là chữ hoa hay không.</td>
</tr>
<tr>
<td>5</td>
<td>isLowerCase()</td><td>
Xác định xem giá trị char được chỉ định có phải là chữ thường hay không.</td>
</tr>
<tr>
<td>6</td>
<td>toUpperCase()</td><td>
Trả về dạng chữ hoa của giá trị char được chỉ định.</td>
</tr>
<tr>
<td>7</td>
<td>toLowerCase()</td><td>
Trả về dạng chữ thường của giá trị char được chỉ định.</td>
</tr>
<tr>
<td>8</td>
<td>toString()</td><td>
Trả về một đối tượng String đại diện cho giá trị char được chỉ định, nghĩa là một chuỗi có 1 ký tự.</td>
</tr>
</tbody></table>

LƯU Ý : Tất cả các phương thức trên thuộc về java.lang.Character

## Các Phương thức của Class String :

<table class="alt">
<tbody><tr><th>STT</th><th>Phương thức (Method)</th><th>Mô tả (Description)</th></tr>
<tr><td>1</td><td>char charAt(int index)</td><td>trả về giá trị char tại index (chỉ mục) cụ thể</td></tr>
<tr><td>2</td><td>int length()</td><td>trả về độ dài chuỗi (string length)</td></tr>
<tr><td>3</td><td>static String format(String format, Object... args)</td><td>trả về chuỗi đã được định dạng (formatted string)</td></tr>
<tr><td>4</td><td>static String format(Locale l, String format, Object... args)</td><td>trả về chuỗi đã được định dạng đi kèm locale chỉ định</td></tr>
<tr><td>5</td><td>String substring(int beginIndex)</td><td>trả về chuỗi con (substring) tính từ vị trí begin index</td></tr>
<tr><td>6</td><td>String substring(int beginIndex, int endIndex)</td><td>trả về chuỗi con nằm trong khoảng begin index và end index</td></tr>
<tr><td>7</td><td>boolean contains(CharSeq s)</td><td>trả về true hoặc false sau khi so khớp (matching) với chuỗi char value</td></tr>
<tr><td>8</td><td>static String join(CharSeq delim, CharSeq... elem)</td><td>trả về một chuỗi được nối (joined string)</td></tr>
<tr><td>9</td><td>static String join(CharSeq delim, Iterable&lt;? extends CharSeq&gt; elem)</td><td>trả về một chuỗi được nối</td></tr>
<tr><td>10</td><td>boolean equals(Object another)</td><td>kiểm tra tính bằng nhau của chuỗi với đối tượng khác</td></tr>
<tr><td>11</td><td>boolean isEmpty()</td><td>kiểm tra xem chuỗi có trống hay không</td></tr>
<tr><td>12</td><td>String concat(String str)</td><td>nối liền (concatinates) chuỗi được chỉ định</td></tr>
<tr><td>13</td><td>String replace(char old, char new)</td><td>thay thế toàn bộ các vị trí xuất hiện của char value được chỉ định</td></tr>
<tr><td>14</td><td>String replace(CharSeq old, CharSeq new)</td><td>thay thế toàn bộ các vị trí xuất hiện của CharSeq được chỉ định</td></tr>
<tr><td>15</td><td>static String equalsIgnoreCase(String another)</td><td>so sánh với một chuỗi khác. Nó không phân biệt chữ hoa chữ thường.</td></tr>
<tr><td>16</td><td>String[] split(String regex)</td><td>trả về mảng chuỗi được cắt ra dựa theo regex</td>
</tr><tr><td>17</td><td>String[] split(String regex, int limit)</td><td>trả về mảng chuỗi được cắt ra dựa theo regex và giới hạn limit</td>
</tr><tr><td>18</td><td>String intern()</td><td>trả về một interned string</td>
</tr><tr><td>19</td><td>int indexOf(int ch)</td><td>trả về chỉ mục (index) của giá trị char chỉ định</td></tr>
<tr><td>20</td><td>int indexOf(int ch, int fromIndex)</td><td>trả về chỉ mục của giá trị char chỉ định tính từ vị trí index khởi đầu</td></tr>
<tr><td>21</td><td>int indexOf(String substring)</td><td>trả về chỉ mục của chuỗi con chỉ định</td></tr>
<tr><td>22</td><td>int indexOf(String substring, int fromIndex)</td><td>trả về chỉ mục của chuỗi con chỉ định tính từ vị trí index khởi đầu</td></tr>
<tr><td>23</td><td>String toLowerCase()</td><td>trả về chuỗi ở dạng chữ thường.</td></tr>
<tr><td>24</td><td>String toLowerCase(Locale l)</td><td>trả về chuỗi ở dạng chữ thường dựa trên locale chỉ định.</td></tr>
<tr><td>25</td><td>String toUpperCase()</td><td>trả về chuỗi ở dạng chữ hoa.</td></tr>
<tr><td>26</td><td>String toUpperCase(Locale l)</td><td>trả về chuỗi ở dạng chữ hoa dựa trên locale chỉ định.</td></tr>
<tr><td>27</td><td>String trim()</td><td>cắt bỏ các khoảng trắng ở đầu và cuối của chuỗi này.</td></tr>
<tr><td>28</td><td>static String valueOf(int value)</td><td>chuyển đổi kiểu được đưa vào thành string. Đây là hàm được overloaded (nạp chồng).</td></tr>
</tbody></table>

LƯU Ý : CharSeq - CharSequence, delim - delimeter (dấu phân cách), elem - elements (các phần tử)

## Các Phương thức của Class Array :

<table class="alt">
<tbody><tr><th>STT</th><th align = "left">     Phương thức & Mô tả (Methods & Description)</th></tr>
<tr>
<td>1</td>
<td><b>public static String toString(int[] a)</b><br>
Sự đại diện chuỗi bao gồm danh sách các phần tử của mảng, được bọc trong ngoặc vuông (“[]”). Các phần tử liền kề nhau sẽ được phân tách bởi một dấu phẩy theo sau là một khoảng trắng. Các phần tử sẽ được chuyển thành string thông qua việc gọi hàm String.valueOf(int). Trả về “null” nếu mảng a là null.<br>
</td>
</tr>
<tr>
<td>2</td>
<td><b>public static int[] copyOf(int[] original, int newLength)</b><br>
Sao chép mảng với độ dài được chỉ định. Nó sẽ cắt xén mảng (truncates) nếu độ dài được cấp nhỏ hơn mảng gốc và nếu độ dài được cấp lớn hơn mảng gốc, nó sẽ điền thêm giá trị mặc định của kiểu tương ứng vào các phần tử thừa ra.<br>
</td>
</tr>
<tr>
<td>3</td>
<td><b>public static int[] copyOfRange(int[] original, int from, int to)</b><br>
Sao chép phần phạm vi (range) của mảng được chỉ định sang một mảng mới. Index khởi đầu của mảng (from) phải nằm từ 0 cho đến original.length, kể cả điểm biên.<br>
</td>
</tr>
<tr>
<td>4</td>
<td><b>public static void fill(int[] a, int val)</b><br>
Gán một giá trị int được chỉ định cho mọi phần tử bên trong mảng ints được chỉ định.<br>
</td>
</tr>
<tr>
<td>5</td>
<td><b>public static void fill(int[] a, int fromIndex, int toIndex, int val)</b><br>
Đổ đầy các phần tử của mảng được chỉ định với giá trị truyền vào tính từ phần tử fromIndex, nhưng không tính tới phần tử toIndex.<br>
</td>
</tr>
<tr>
<td>6</td>
<td><b>public static boolean equals(int[] a, int[] a2)</b><br>
Trả về true nếu hai mảng longs được chỉ định là bằng nhau. Hai mảng được coi là bằng nhau nếu cả hai đều có chung số lượng phần tử, và mọi cặp phần tử tương ứng ở trong hai mảng là bằng nhau. Việc này trả về true nếu như hai mảng bằng nhau.<br>
</td>
</tr>
<tr>
<td>7</td>
<td><b>public static void sort(int[] a)</b><br>
Sắp xếp mảng objects được chỉ định theo thứ tự tăng dần (ascending order), tuân theo thứ tự sắp xếp tự nhiên (natural ordering) của các phần tử trong đó.<br>
</td>
</tr>
<tr>
<td>8</td>
<td><b>public static void sort(int[] a, int fromIndex, int toIndex)</b><br>
Nếu chúng ta muốn sắp xếp một phạm vi nhất định của mảng theo thứ tự tăng dần, ta có thể dùng cách này. Phạm vi sắp xếp trải dài từ index fromIndex (tính cả điểm đầu), cho đến phần index toIndex (bỏ qua điểm cuối). Nếu fromIndex == toIndex, vùng sắp xếp được hiểu là một khoảng trống rỗng.<br>
</td>
</tr>
<tr>
<td>9</td>
<td><b>public static int binarySearch(int[] a, int key)</b><br>
Tìm kiếm trong mảng số nguyên một giá trị được chỉ định nhờ thuật toán tìm kiếm nhị phân (binary search). Mảng bắt buộc phải được sắp xếp trước khi đưa vào hàm. Nó sẽ trả về số index của key tìm kiếm, nếu giá trị đó nằm trong list; nếu không, nó sẽ trả về ( – (điểm chèn - insertion point + 1)).<br>
</td>
</tr>
<tr>
<td>10</td>
<td><b>public static List asList(int[] a)</b><br>
Nhận vào một mảng và tạo ra một wrapper (không có dữ liệu nào được copy) để implement List, giúp làm cho mảng nguyên bản khả dụng giống như một list. Các thao tác trên lớp bọc list sẽ được truyền xuống áp dụng vào thẳng mảng gốc. Các thao tác list như thêm/xóa phần tử không được phép thực hiện, bạn chỉ có thể đọc/ghi đè lên các phần tử.<br>
</td>
</tr>
<tr>
<td>11</td>
<td><b>static int hashCode(int[] a)</b><br>
Phương thức này sẽ trả về mã băm (hash code) dựa trên các phần dung lượng có trong mảng được chỉ định.<br>
</td>
</tr>
</tbody></table>

LƯU Ý : Tất cả các phương thức trên thuộc về java.util.Array

Tất cả các phương thức được nhắc tới ở trên thông qua ví dụ với int[] cũng hoàn toàn có thể được dùng cho toàn bộ các primitive, wrapper, và object data types khác (Vd - byte, short, long, Byte, Short, Int, v.v.)
