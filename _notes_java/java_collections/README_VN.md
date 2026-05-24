# Collections Framework trong Java

Gói `java.util` chứa tất cả các class và interface dành cho Collection framework.

**Map :**
Một đối tượng ánh xạ (maps) các key với các value. Một map không có tính thứ tự và không thể chứa các key trùng lặp (nhưng có thể chứa các value trùng lặp). Mỗi key chỉ có thể ánh xạ đến tối đa một value.
    
**Collection :**
Một Collection biểu diễn một nhóm các đối tượng, được gọi là các phần tử (elements) của nó. JDK cung cấp các triển khai của nhiều subinterface cụ thể hơn như Set và List.

**List :**
Một List là một danh sách có thứ tự của các đối tượng, nơi mà cùng một đối tượng có thể xuất hiện nhiều hơn một lần. Ví dụ: [1, 7, 1, 3, 1, 1, 1, 5]. Thật hợp lý khi nói về "phần tử thứ ba" trong một List. Bạn có thể thêm một phần tử vào bất kỳ đâu trong list, thay đổi một phần tử ở bất kỳ đâu trong list, hoặc xóa một phần tử khỏi bất kỳ vị trí nào trong list.

**Queue :**
Một Queue (Hàng đợi) cũng có tính thứ tự, nhưng bạn sẽ chỉ thao tác với các phần tử ở một đầu. Tất cả các phần tử được chèn vào "cuối" (end) và bị xóa khỏi "đầu" (beginning hay head) của queue. Bạn có thể biết được có bao nhiêu phần tử nằm trong queue, nhưng bạn không thể biết chính xác, giả sử, phần tử "thứ ba" là gì. Bạn sẽ chỉ nhìn thấy nó khi bạn lấy đến nó.

**Set :**
Một Set (Tập hợp) không có tính thứ tự và không thể chứa các phần tử trùng lặp. Bất kỳ đối tượng nào đưa ra đều chỉ có thể nằm trong hoặc không nằm trong set. {7, 5, 3, 1} chính xác là cùng một set với {1, 7, 3, 5}. Bạn lại một lần nữa không thể yêu cầu phần tử "thứ ba" hoặc thậm chí phần tử "đầu tiên", vì chúng không tuân theo bất kỳ thứ tự cụ thể nào. Bạn có thể thêm hoặc xóa phần tử, và bạn có thể kiểm tra xem một phần tử nhất định có tồn tại hay không.

<table class="alt">
<tbody>
<tr><th> </th><th>List</th><th>Set</th><th>Queue</th><th>Map</th></tr>
<tr><th>Có thứ tự (Order)</th><th>Có (Yes)</th><th>Không (No)</th><th>Có (Yes)</th><th>Không (No)</th></tr>
<tr><th>Trùng lặp (Duplicates)</th><th>Có (Yes)</th><th>Không (No)</th><th>Có (Yes)</th><th>Không (Cho phép trùng lặp value chứ không phải key)</th></tr>
<tr><th>Giá trị Null (Null Values)</th><th>Có (Yes)</th><th>Single Null</th><th>Có (LinkedList Queue). Không (Priority Queue).</th><th>Single null key và nhiều null values</th></tr>
</tbody></table>

## Sơ đồ phân cấp của Collection Interface :

![collection-hierarchy](https://user-images.githubusercontent.com/2780145/34073817-62945de4-e2c8-11e7-820b-84f9dad32af3.png)

## Các Phương thức của Collection Interface :

<table class="alt">
<tbody><tr><th>STT</th><th>Phương thức (Method)</th><th>Mô tả (Description)</th></tr>
<tr><td>1</td><td>public boolean add(Object element)</td><td>được dùng để chèn một phần tử vào collection này.</td></tr>
<tr><td>2</td><td>public boolean addAll(Collection c)</td><td>được dùng để chèn tất cả các phần tử của collection được chỉ định vào collection đang gọi.</td></tr>
<tr><td>3</td><td>public boolean remove(Object element)</td><td>được dùng để xóa một phần tử khỏi collection này.</td></tr>
<tr><td>4</td><td>public boolean removeAll(Collection c)</td><td>được dùng để xóa tất cả các phần tử của collection được chỉ định khỏi collection đang gọi.</td></tr>
<tr><td>5</td><td>public boolean retainAll(Collection c)</td><td>được dùng để xóa tất cả các phần tử của collection đang gọi ngoại trừ các phần tử có trong collection được chỉ định.</td></tr>
<tr><td>6</td><td>public int size()</td><td>trả về tổng số phần tử trong collection.</td></tr>
<tr><td>7</td><td>public void clear()</td><td>xóa tổng số phần tử khỏi collection.</td></tr>
<tr><td>8</td><td>public boolean contains(Object element)</td><td>được dùng để tìm kiếm một phần tử.</td></tr>
<tr><td>9</td><td>public boolean containsAll(Collection c)</td><td>được dùng để tìm kiếm collection được chỉ định bên trong collection này.</td></tr>
<tr><td>10</td><td>public Iterator iterator()</td><td>trả về một iterator.</td></tr>
<tr><td>11</td><td>public Object[] toArray()</td><td>chuyển đổi collection thành mảng (array).</td></tr>
<tr><td>12</td><td>public boolean isEmpty()</td><td>kiểm tra xem collection có trống hay không.</td></tr>
<tr><td>13</td><td>public boolean equals(Object element)</td><td>so sánh tính bằng nhau của hai collection.</td></tr>
<tr><td>14</td><td>public int hashCode()</td><td>trả về số hashcode của collection.</td></tr>
</tbody></table>

## Các Phương thức của Iterator Interface :

<table class="alt">
<tbody><tr><th>STT</th><th>Phương thức (Method)</th><th>Mô tả (Description)</th></tr>
<tr><td>1</td><td>public boolean hasNext()</td><td>Trả về true nếu iterator còn nhiều phần tử hơn.</td></tr>
<tr><td>2</td><td>public Object next()</td><td>Trả về phần tử tiếp theo và di chuyển con trỏ (cursor) sang phần tử kế tiếp.</td></tr>
<tr><td>3</td><td>public void remove()</td><td>Xóa phần tử cuối cùng được trả về bởi iterator. Phương thức này hiếm khi được sử dụng.</td></tr>
</tbody></table>

## ArrayList vs LinkedList :

<table class="alt">
<tbody><tr><th>ArrayList</th><th>LinkedList</th></tr>
<tr><td>1) ArrayList sử dụng nội bộ <strong>dynamic array (mảng động)</strong> để lưu trữ các phần tử.</td><td>LinkedList sử dụng nội bộ <strong>doubly linked list (danh sách liên kết đôi)</strong> để lưu trữ các phần tử.</td></tr>
<tr><td>2) Quá trình thao tác (Manipulation) với ArrayList <strong>chậm</strong> vì nó sử dụng mảng nội bộ. Nếu có bất kỳ phần tử nào bị xóa khỏi mảng, tất cả các bit phía sau sẽ bị dịch chuyển trong bộ nhớ.</td><td>Quá trình thao tác với LinkedList <strong>nhanh hơn</strong> ArrayList vì nó sử dụng doubly linked list nên không cần dịch chuyển bit trong bộ nhớ.</td></tr>
<tr><td>3) Class ArrayList <strong>chỉ có thể hoạt động như một list</strong> bởi vì nó chỉ implements interface List.</td><td>Class LinkedList <strong>có thể hoạt động như một list và cả queue</strong> bởi vì nó implements cả hai interfaces List và Deque.</td></tr>
<tr><td>4) ArrayList <strong>tốt hơn cho việc lưu trữ và truy cập</strong> dữ liệu.</td><td>LinkedList <strong>tốt hơn cho việc thao tác (thêm/xóa)</strong> dữ liệu.</td></tr>
</tbody></table>

## ArrayList vs Vector :

<table class="alt">
<tbody><tr><th>ArrayList</th><th>Vector</th></tr>
<tr><td>1) ArrayList là <strong>không đồng bộ (non-synchronized)</strong>.</td><td>Vector là <strong>đồng bộ (synchronized)</strong>.</td></tr>
<tr><td>2) ArrayList <strong>tăng thêm 50%</strong> kích thước mảng hiện tại nếu số lượng phần tử vượt quá dung lượng (capacity) của nó.</td><td>Vector <strong>tăng thêm 100%</strong> nghĩa là nhân đôi kích thước mảng nếu tổng số phần tử vượt quá dung lượng của nó.</td></tr>
<tr><td>3) ArrayList <strong>không phải là một class cũ (legacy class)</strong>, nó được giới thiệu từ JDK 1.2.</td><td>Vector là một <strong>legacy class</strong>.</td></tr>
<tr><td>4) ArrayList <strong>nhanh</strong> bởi vì nó non-synchronized.</td><td>Vector <strong>chậm</strong> bởi vì nó được synchronized, có nghĩa là trong môi trường đa luồng (multithreading), nó sẽ giữ các thread khác ở trạng thái runnable hoặc non-runnable cho đến khi thread hiện tại giải phóng khóa (lock) của đối tượng.</td></tr>
<tr><td>5) ArrayList sử dụng interface <strong>Iterator</strong> để duyệt qua các phần tử.</td><td>Vector sử dụng interface <strong>Enumeration</strong> để duyệt qua các phần tử. Nhưng nó cũng có thể sử dụng Iterator.</td></tr>
</tbody></table>

## Sơ đồ phân cấp của Map Interface :

![hierarchy-of-maps-in-java](https://user-images.githubusercontent.com/2780145/34075635-1a5bba52-e2f2-11e7-8962-384b5bc24ae5.png)

## Các Phương thức Hữu ích của Map Interface :

<table class="alt">
<tbody><tr><th>Phương thức (Method)</th><th>Mô tả (Description)</th></tr>
<tr><td> Object put(Object key, Object value)</td><td>Được dùng để chèn một entry vào map này.</td></tr>
<tr><td>void putAll(Map map)</td><td>Được dùng để chèn toàn bộ map được chỉ định vào map này.</td></tr>
<tr><td>Object remove(Object key)</td><td>Được dùng để xóa một entry dựa trên key được chỉ định.</td></tr>
<tr><td>Object get(Object key)</td><td>Được dùng để trả về value của key được chỉ định.</td></tr>
<tr><td>boolean containsKey(Object key)</td><td>Được dùng để tìm kiếm key được chỉ định trong map này.</td></tr>
<tr><td>Set keySet()</td><td>Được dùng để trả về giao diện Set chứa tất cả các keys.</td></tr>
<tr><td>Set entrySet()</td><td>Được dùng để trả về giao diện Set chứa tất cả các keys và values.</td></tr>
</tbody></table>

## Các Phương thức của Map.Entry Interface :
<table class="alt">
<tbody><tr><th>Phương thức (Method)</th><th>Mô tả (Description)</th></tr>
<tr><td> Object getKey()</td><td>Được dùng để lấy ra key.</td></tr>
<tr><td>Object getValue()</td><td>Được dùng để lấy ra value.</td></tr>
</tbody></table>

## HashMap vs HashTable :

<table class="alt">
<tbody><tr><th>HashMap</th><th>Hashtable</th></tr>
<tr><td>1) HashMap là <strong>non-synchronized</strong>. Nó không an toàn luồng (not-thread safe) và không thể được chia sẻ giữa nhiều threads mà không có mã đồng bộ thích hợp.</td><td>Hashtable là <strong>synchronized</strong>. Nó an toàn luồng (thread-safe) và có thể được chia sẻ với nhiều threads.</td></tr>
<tr><td>2) HashMap <strong>cho phép một key null và nhiều values null</strong>.</td><td>Hashtable <strong>không cho phép bất kỳ key hay value nào là null</strong>.</td></tr>
<tr><td>3) HashMap là một <strong>class mới được giới thiệu trong JDK 1.2</strong>.</td><td>Hashtable là một <strong>legacy class</strong>.</td></tr>
<tr><td>4) HashMap <strong>nhanh</strong>.</td><td>Hashtable <strong>chậm</strong>.</td></tr>
<tr><td>5) Chúng ta có thể làm cho HashMap được synchronized bằng cách gọi đoạn code này<br> Map m = Collections.synchronizedMap(hashMap);</td><td>Hashtable được đồng bộ hóa nội bộ (internally synchronized) và không thể unsynchronized được.</td></tr>
<tr><td>6) HashMap được <strong>duyệt bởi Iterator</strong>.</td><td>Hashtable được <strong>duyệt bởi Enumerator và Iterator</strong>.</td></tr>
<tr><td>7) Iterator trong HashMap là <strong>fail-fast</strong>.</td><td>Enumerator trong Hashtable <strong>không phải là fail-fast</strong>.</td></tr>
<tr><td>8) HashMap kế thừa class <strong>AbstractMap</strong>.</td><td>Hashtable kế thừa class <strong>Dictionary</strong>.</td></tr>
</tbody></table>

## Tóm tắt các Implementation Classes của Collections Framework :

![collectionjava](https://user-images.githubusercontent.com/2780145/34075655-a59a8a1c-e2f2-11e7-94d7-a49c03df0fa8.png)

## Interfaces Comparable vs Comparator :

<table class="alt">
<tbody><tr><th>Comparable</th><th>Comparator</th></tr>
<tr><td>1) Comparable cung cấp <strong>single sorting sequence (một trình tự sắp xếp duy nhất)</strong>. Nói cách khác, chúng ta có thể sắp xếp collection dựa trên một phần tử duy nhất như id hoặc name hoặc price, v.v.</td><td> Comparator cung cấp <strong>multiple sorting sequence (nhiều trình tự sắp xếp)</strong>. Nói cách khác, chúng ta có thể sắp xếp collection dựa trên nhiều phần tử như id, name và price, v.v.</td></tr>
<tr><td>2) Comparable <strong>gây ảnh hưởng tới class gốc</strong>, nghĩa là class thực tế sẽ bị sửa đổi.</td><td>Comparator <strong>không gây ảnh hưởng tới class gốc</strong>, nghĩa là class thực tế sẽ không bị sửa đổi.</td></tr>
<tr><td>3) Comparable cung cấp phương thức <strong>compareTo()</strong> để sắp xếp các phần tử.</td><td>Comparator cung cấp phương thức <strong>compare()</strong> để sắp xếp các phần tử.</td></tr>
<tr><td>4) Comparable được tìm thấy trong package <strong>java.lang</strong>.</td><td>Comparator được tìm thấy trong package <strong>java.util</strong>.</td></tr>
<tr><td>5) Chúng ta có thể sắp xếp list các phần tử có kiểu Comparable thông qua phương thức <strong>Collections.sort(List)</strong>.</td><td>Chúng ta có thể sắp xếp list các phần tử có kiểu Comparator thông qua phương thức <strong>Collections.sort(List,Comparator)</strong>.</td></tr>
</tbody></table>

## Legacy Data Structures trong Java

Các legacy classes (lớp cũ) và interfaces là những class và interface đã hình thành nên collections framework trong các phiên bản cũ của Java và hiện nay đã được tái cấu trúc (restructured) hoặc thiết kế lại (re-engineered). Chúng hoàn toàn tương thích với framework hiện tại.

Tất cả các legacy classes đã được re-engineered để hỗ trợ generic trong JDK 5.

Legacy = di sản từ phiên bản java cũ.

Legacy classes và interfaces - Enumeration, Vector, Stack, Dictionary, HashTable, Properties...
