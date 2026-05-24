# Giới thiệu về Mẫu Thiết kế (Introduction to Design Patterns)

Trong kỹ thuật phần mềm, một mẫu thiết kế (design pattern) là một giải pháp lặp lại tổng quát cho một vấn đề thường gặp trong thiết kế phần mềm. Một design pattern không phải là một thiết kế đã hoàn chỉnh để có thể chuyển đổi trực tiếp thành mã nguồn (code). Nó là một mô tả hoặc khuôn mẫu (template) về cách giải quyết một vấn đề, có thể được áp dụng trong nhiều tình huống khác nhau.

## Công dụng của Mẫu Thiết kế (Uses of Design Patterns) :
Các design pattern có thể tăng tốc quá trình phát triển phần mềm bằng cách cung cấp các mô hình phát triển đã được kiểm chứng và thử nghiệm. Thiết kế phần mềm hiệu quả đòi hỏi phải xem xét các vấn đề mà có thể chưa xuất hiện cho đến khi bắt đầu triển khai chi tiết. Việc tái sử dụng các mẫu thiết kế giúp ngăn chặn các lỗi tiềm ẩn (subtle issues) có thể gây ra những sự cố nghiêm trọng, đồng thời cải thiện khả năng đọc hiểu mã nguồn đối với các lập trình viên và kiến trúc sư hệ thống đã quen thuộc với các mẫu này.

Các mẫu thiết kế cung cấp các giải pháp chung dễ dàng áp dụng cho phạm vi bài toán rộng hơn, được tài liệu hóa dưới dạng không phụ thuộc vào chi tiết cụ thể của một bài toán nào. Ngoài ra, các mẫu này cho phép các nhà phát triển giao tiếp với nhau bằng cách sử dụng các tên gọi phổ biến, dễ hiểu cho các tương tác phần mềm. Các mẫu thiết kế phổ biến có thể được cải tiến theo thời gian, giúp chúng mạnh mẽ và ổn định hơn so với các thiết kế tự phát (ad-hoc).

## 1 Mẫu Thiết kế Khởi tạo (Creational Design Patterns)
Mẫu thiết kế khởi tạo (Creational design patterns) liên quan đến cách thức khởi tạo các đối tượng. Các mẫu thiết kế này được sử dụng khi quyết định khởi tạo một lớp (tức là tạo một đối tượng của một lớp) cần được đưa ra tại thời điểm chạy (runtime). Tuy nhiên, ai cũng biết một đối tượng được tạo bằng cách sử dụng từ khóa `new` trong Java.
Viết code cứng (hard-coded code) không phải là một cách tiếp cận lập trình tốt. Ở đây, chúng ta tạo thực thể bằng cách sử dụng từ khóa `new`. Đôi khi, bản chất của đối tượng phải thay đổi tùy thuộc vào tính chất của chương trình. Trong những trường hợp như vậy, chúng ta phải nhờ đến sự trợ giúp của các creational design pattern để cung cấp cách tiếp cận tổng quát và linh hoạt hơn.

- Factory Method (Phương thức nhà máy)
- Abstract Factory (Nhà máy trừu tượng)
- Singleton (Độc bản)
- Prototype (Nguyên mẫu)
- Builder (Người xây dựng)
- Object Pool (Nhóm đối tượng)

## 2 Mẫu Thiết kế Cấu trúc (Structural Design Patterns)
Mẫu thiết kế cấu trúc (Structural design patterns) liên quan đến cách các lớp và đối tượng có thể được kết hợp với nhau để tạo thành các cấu trúc lớn hơn.
Các mẫu thiết kế cấu trúc đơn giản hóa cấu trúc bằng cách xác định các mối quan hệ.
Các mẫu này tập trung vào cách các lớp kế thừa từ nhau và cách chúng được cấu thành từ các lớp khác.

- Adapter (Bộ tương thích)
- Bridge (Cầu nối)
- Composite (Hỗn hợp)
- Decorator (Trang trí)
- Facade (Mặt tiền)
- Flyweight (Chia sẻ dung lượng)
- Proxy (Ủy nhiệm)

## 3 Mẫu Thiết kế Hành vi (Behavioral Design Patterns)
Mẫu thiết kế hành vi (Behavioral design patterns) liên quan đến sự tương tác và trách nhiệm của các đối tượng.
Trong các mẫu thiết kế này, sự tương tác giữa các đối tượng phải được thiết lập sao cho chúng có thể dễ dàng giao tiếp với nhau nhưng vẫn giữ được tính liên kết lỏng lẻo (loosely coupled).
Điều đó có nghĩa là phần triển khai (implementation) và phía khách khách hàng (client) nên được liên kết lỏng lẻo nhằm tránh viết mã cứng (hard coding) và phụ thuộc lẫn nhau.

- Observer (Người quan sát)
- State (Trạng thái)
- Strategy (Chiến lược)
- Chain of Responsibility (Chuỗi trách nhiệm)
- Command (Lệnh)
- Interpreter (Trình thông dịch)
- Iterator (Trình lặp)
- Mediator (Trung gian)
- Memento (Vật kỷ niệm)
- Template Method (Phương thức khuôn mẫu)
- Visitor (Khách truy cập)
- Null Object (Đối tượng rỗng)

## Một số ví dụ về Mẫu Thiết kế được sử dụng trong JDK

<div class="s-prose js-post-body" itemprop="text">

<h2><a href="http://en.wikipedia.org/wiki/Creational_pattern" rel="noreferrer">Creational patterns (Mẫu khởi tạo)</a></h2>
<h3><a href="http://en.wikipedia.org/wiki/Abstract_factory_pattern" rel="noreferrer">Abstract factory</a> <sup><sub>(nhận biết qua các phương thức khởi tạo trả về chính factory đó, sau đó có thể dùng để tạo ra một kiểu abstract/interface khác)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/javax/xml/parsers/DocumentBuilderFactory.html#newInstance--" rel="noreferrer"><code>javax.xml.parsers.DocumentBuilderFactory#newInstance()</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/javax/xml/transform/TransformerFactory.html#newInstance--" rel="noreferrer"><code>javax.xml.transform.TransformerFactory#newInstance()</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/javax/xml/xpath/XPathFactory.html#newInstance--" rel="noreferrer"><code>javax.xml.xpath.XPathFactory#newInstance()</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Builder_pattern" rel="noreferrer">Builder</a> <sup><sub>(nhận biết qua các phương thức khởi tạo trả về chính thực thể đó - method chaining)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html#append-boolean-" rel="noreferrer"><code>java.lang.StringBuilder#append()</code></a> (không đồng bộ - unsynchronized)</li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/lang/StringBuffer.html#append-boolean-" rel="noreferrer"><code>java.lang.StringBuffer#append()</code></a> (đồng bộ - synchronized)</li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/nio/ByteBuffer.html#put-byte-" rel="noreferrer"><code>java.nio.ByteBuffer#put()</code></a> (cũng có trên <a href="http://docs.oracle.com/javase/8/docs/api/java/nio/CharBuffer.html#put-char-" rel="noreferrer"><code>CharBuffer</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/nio/ShortBuffer.html#put-short-" rel="noreferrer"><code>ShortBuffer</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/nio/IntBuffer.html#put-int-" rel="noreferrer"><code>IntBuffer</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/nio/LongBuffer.html#put-long-" rel="noreferrer"><code>LongBuffer</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/nio/FloatBuffer.html#put-float-" rel="noreferrer"><code>FloatBuffer</code></a> và <a href="http://docs.oracle.com/javase/8/docs/api/java/nio/DoubleBuffer.html#put-double-" rel="noreferrer"><code>DoubleBuffer</code></a>)</li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/javax/swing/GroupLayout.Group.html#addComponent-java.awt.Component-" rel="noreferrer"><code>javax.swing.GroupLayout.Group#addComponent()</code></a></li>
<li>Tất cả các triển khai của <a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Appendable.html" rel="noreferrer"><code>java.lang.Appendable</code></a></li>
<li><a href="https://docs.oracle.com/javase/9/docs/api/java/util/stream/Stream.Builder.html" rel="noreferrer"><code>java.util.stream.Stream.Builder</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Factory_method_pattern" rel="noreferrer">Factory method</a> <sup><sub>(nhận biết qua các phương thức khởi tạo trả về một bản triển khai của kiểu abstract/interface)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#getInstance--" rel="noreferrer"><code>java.util.Calendar#getInstance()</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/ResourceBundle.html#getBundle-java.lang.String-" rel="noreferrer"><code>java.util.ResourceBundle#getBundle()</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/text/NumberFormat.html#getInstance--" rel="noreferrer"><code>java.text.NumberFormat#getInstance()</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/nio/charset/Charset.html#forName-java.lang.String-" rel="noreferrer"><code>java.nio.charset.Charset#forName()</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/net/URLStreamHandlerFactory.html" rel="noreferrer"><code>java.net.URLStreamHandlerFactory#createURLStreamHandler(String)</code></a> (Trả về một đối tượng singleton cho mỗi giao thức)</li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/EnumSet.html#of(E)" rel="noreferrer"><code>java.util.EnumSet#of()</code></a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/javax/xml/bind/JAXBContext.html#createMarshaller--" rel="noreferrer"><code>javax.xml.bind.JAXBContext#createMarshaller()</code></a> và các phương thức tương tự khác</li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Prototype_pattern" rel="noreferrer">Prototype</a> <sup><sub>(nhận biết qua các phương thức khởi tạo trả về một thực thể *khác* của chính nó nhưng có cùng các thuộc tính)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#clone--" rel="noreferrer"><code>java.lang.Object#clone()</code></a> (lớp đó phải implement <a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Cloneable.html" rel="noreferrer"><code>java.lang.Cloneable</code></a>)</li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Singleton_pattern" rel="noreferrer">Singleton</a> <sup><sub>(nhận biết qua các phương thức khởi tạo luôn trả về cùng một thực thể duy nhất - thường là của chính nó)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Runtime.html#getRuntime--" rel="noreferrer"><code>java.lang.Runtime#getRuntime()</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/awt/Desktop.html#getDesktop--" rel="noreferrer"><code>java.awt.Desktop#getDesktop()</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/lang/System.html#getSecurityManager--" rel="noreferrer"><code>java.lang.System#getSecurityManager()</code></a></li>
</ul>
<hr>
<h2><a href="http://en.wikipedia.org/wiki/Structural_pattern" rel="noreferrer">Structural patterns (Mẫu cấu trúc)</a></h2>
<h3><a href="http://en.wikipedia.org/wiki/Adapter_pattern" rel="noreferrer">Adapter</a> <sup><sub>(nhận biết qua các phương thức khởi tạo nhận vào thực thể của kiểu abstract/interface *khác* và trả về một bản triển khai của kiểu abstract/interface của chính nó hoặc một kiểu khác nhằm *trang trí/ghi đè* thực thể được truyền vào)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html#asList-T...-" rel="noreferrer"><code>java.util.Arrays#asList()</code></a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#list-java.util.Enumeration-" rel="noreferrer"><code>java.util.Collections#list()</code></a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#enumeration-java.util.Collection-" rel="noreferrer"><code>java.util.Collections#enumeration()</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/io/InputStreamReader.html#InputStreamReader-java.io.InputStream-" rel="noreferrer"><code>java.io.InputStreamReader(InputStream)</code></a> (trả về một <code>Reader</code>)</li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/io/OutputStreamWriter.html#OutputStreamWriter-java.io.OutputStream-" rel="noreferrer"><code>java.io.OutputStreamWriter(OutputStream)</code></a> (trả về một <code>Writer</code>)</li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/javax/xml/bind/annotation/adapters/XmlAdapter.html#marshal-BoundType-" rel="noreferrer"><code>javax.xml.bind.annotation.adapters.XmlAdapter#marshal()</code></a> và <a href="http://docs.oracle.com/javase/8/docs/api/javax/xml/bind/annotation/adapters/XmlAdapter.html#unmarshal-ValueType-" rel="noreferrer"><code>#unmarshal()</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Bridge_pattern" rel="noreferrer">Bridge</a> <sup><sub>(nhận biết qua các phương thức khởi tạo nhận thực thể của kiểu abstract/interface *khác* và trả về một bản triển khai của kiểu abstract/interface của chính nó nhằm *ủy quyền/sử dụng* thực thể được truyền vào)</sub></sup></h3>
<ul>
<li>Chưa có ví dụ có sẵn nào trực tiếp. Một ví dụ giả định là <code>new LinkedHashMap(LinkedHashSet&lt;K&gt;, List&lt;V&gt;)</code> trả về một map dạng liên kết không thể sửa đổi, không sao chép phần tử mà *sử dụng* trực tiếp chúng. Tuy nhiên, các phương thức <a href="http://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#newSetFromMap-java.util.Map-" rel="noreferrer"><code>java.util.Collections#newSetFromMap()</code></a> và <code>singletonXXX()</code> cũng có cách hoạt động gần giống.</li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Composite_pattern" rel="noreferrer">Composite</a> <sup><sub>(nhận biết qua các phương thức hành vi nhận vào thực thể của *cùng* kiểu abstract/interface vào một cấu trúc cây)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/awt/Container.html#add-java.awt.Component-" rel="noreferrer"><code>java.awt.Container#add(Component)</code></a> (hầu như xuất hiện khắp nơi trong Swing)</li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/faces/component/UIComponent.html#getChildren--" rel="noreferrer"><code>javax.faces.component.UIComponent#getChildren()</code></a> (hầu như xuất hiện khắp nơi trong JSF UI)</li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Decorator_pattern" rel="noreferrer">Decorator</a> <sup><sub>(nhận biết qua các phương thức khởi tạo nhận thực thể của *cùng* kiểu abstract/interface nhằm thêm vào các hành vi bổ sung)</sub></sup></h3>
<ul>
<li>Tất cả các lớp con của <a href="http://docs.oracle.com/javase/8/docs/api/java/io/InputStream.html" rel="noreferrer"><code>java.io.InputStream</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/io/OutputStream.html" rel="noreferrer"><code>OutputStream</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/io/Reader.html" rel="noreferrer"><code>Reader</code></a> và <a href="http://docs.oracle.com/javase/8/docs/api/java/io/Writer.html" rel="noreferrer"><code>Writer</code></a> đều có một constructor nhận tham số là đối tượng cùng kiểu.</li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/Collections.html" rel="noreferrer"><code>java.util.Collections</code></a>, các phương thức <a href="http://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#checkedCollection-java.util.Collection-java.lang.Class-" rel="noreferrer"><code>checkedXXX()</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#synchronizedCollection-java.util.Collection-" rel="noreferrer"><code>synchronizedXXX()</code></a> và <a href="http://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#unmodifiableCollection-java.util.Collection-" rel="noreferrer"><code>unmodifiableXXX()</code></a>.</li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpServletRequestWrapper.html" rel="noreferrer"><code>javax.servlet.http.HttpServletRequestWrapper</code></a> và <a href="http://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpServletResponseWrapper.html" rel="noreferrer"><code>HttpServletResponseWrapper</code></a></li>
<li><a href="https://docs.oracle.com/javase/7/docs/api/javax/swing/JScrollPane.html" rel="noreferrer"><code>javax.swing.JScrollPane</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Facade_pattern" rel="noreferrer">Facade</a> <sup><sub>(nhận biết qua các phương thức hành vi sử dụng bên trong các thực thể thuộc các kiểu abstract/interface độc lập và *khác nhau*)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/faces/context/FacesContext.html" rel="noreferrer"><code>javax.faces.context.FacesContext</code></a>, bên trong nó sử dụng các kiểu abstract/interface như <a href="http://docs.oracle.com/javaee/7/api/javax/faces/lifecycle/Lifecycle.html" rel="noreferrer"><code>LifeCycle</code></a>, <a href="http://docs.oracle.com/javaee/7/api/javax/faces/application/ViewHandler.html" rel="noreferrer"><code>ViewHandler</code></a>, <a href="http://docs.oracle.com/javaee/7/api/javax/faces/application/NavigationHandler.html" rel="noreferrer"><code>NavigationHandler</code></a> và nhiều lớp khác mà người dùng cuối không cần bận tâm (tuy nhiên có thể ghi đè chúng qua dependency injection).</li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/faces/context/ExternalContext.html" rel="noreferrer"><code>javax.faces.context.ExternalContext</code></a>, bên trong sử dụng <a href="http://docs.oracle.com/javaee/7/api/javax/servlet/ServletContext.html" rel="noreferrer"><code>ServletContext</code></a>, <a href="http://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpSession.html" rel="noreferrer"><code>HttpSession</code></a>, <a href="http://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpServletRequest.html" rel="noreferrer"><code>HttpServletRequest</code></a>, <a href="http://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpServletResponse.html" rel="noreferrer"><code>HttpServletResponse</code></a>, v.v.</li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Flyweight_pattern" rel="noreferrer">Flyweight</a> <sup><sub>(nhận biết qua các phương thức khởi tạo trả về một thực thể được lưu trong cache, có phần giống ý tưởng "multiton")</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html#valueOf-int-" rel="noreferrer"><code>java.lang.Integer#valueOf(int)</code></a> (cũng áp dụng cho <a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html#valueOf-boolean-" rel="noreferrer"><code>Boolean</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Byte.html#valueOf-byte-" rel="noreferrer"><code>Byte</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Character.html#valueOf-char-" rel="noreferrer"><code>Character</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Short.html#valueOf-short-" rel="noreferrer"><code>Short</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Long.html#valueOf-long-" rel="noreferrer"><code>Long</code></a> và <a href="https://docs.oracle.com/javase/8/docs/api/java/math/BigDecimal.html#valueOf-long-int-" rel="noreferrer"><code>BigDecimal</code></a>)</li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Proxy_pattern" rel="noreferrer">Proxy</a> <sup><sub>(nhận biết qua các phương thức khởi tạo trả về một bản triển khai của kiểu abstract/interface được chỉ định, bản triển khai này sẽ *ủy quyền/sử dụng* một bản triển khai *khác* của kiểu abstract/interface đó)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Proxy.html" rel="noreferrer"><code>java.lang.reflect.Proxy</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/rmi/package-summary.html" rel="noreferrer"><code>java.rmi.*</code></a></li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/ejb/EJB.html" rel="noreferrer"><code>javax.ejb.EJB</code></a></li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/inject/Inject.html" rel="noreferrer"><code>javax.inject.Inject</code></a></li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/persistence/PersistenceContext.html" rel="noreferrer"><code>javax.persistence.PersistenceContext</code></a></li>
</ul>
<hr>
<h2><a href="http://en.wikipedia.org/wiki/Behavioral_pattern" rel="noreferrer">Behavioral patterns (Mẫu hành vi)</a></h2>
<h3><a href="http://en.wikipedia.org/wiki/Chain_of_responsibility_pattern" rel="noreferrer">Chain of responsibility</a> <sup><sub>(nhận biết qua các phương thức hành vi gián tiếp gọi cùng phương thức đó trong một bản triển khai *khác* của *cùng* kiểu abstract/interface trong một hàng đợi)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/logging/Logger.html#log-java.util.logging.Level-java.lang.String-" rel="noreferrer"><code>java.util.logging.Logger#log()</code></a></li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/servlet/Filter.html#doFilter-javax.servlet.ServletRequest-javax.servlet.ServletResponse-javax.servlet.FilterChain-" rel="noreferrer"><code>javax.servlet.Filter#doFilter()</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Command_pattern" rel="noreferrer">Command</a> <sup><sub>(nhận biết qua các phương thức hành vi trong một kiểu abstract/interface gọi một phương thức trong một bản triển khai của một kiểu abstract/interface *khác* vốn đã được *đóng gói* bởi bản triển khai command trong lúc khởi tạo)</sub></sup></h3>
<ul>
<li>Tất cả các triển khai của <a href="http://docs.oracle.com/javase/8/docs/api/java/lang/Runnable.html" rel="noreferrer"><code>java.lang.Runnable</code></a></li>
<li>Tất cả các triển khai của <a href="http://docs.oracle.com/javase/8/docs/api/javax/swing/Action.html" rel="noreferrer"><code>javax.swing.Action</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Interpreter_pattern" rel="noreferrer">Interpreter</a> <sup><sub>(nhận biết qua các phương thức hành vi trả về một thực thể/kiểu có cấu trúc *khác* so với thực thể/kiểu được truyền vào; lưu ý rằng việc phân tích/định dạng không thuộc mẫu này, mà việc xác định mẫu và cách áp dụng nó mới đúng)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html" rel="noreferrer"><code>java.util.Pattern</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/text/Normalizer.html" rel="noreferrer"><code>java.text.Normalizer</code></a></li>
<li>Tất cả các lớp con của <a href="http://docs.oracle.com/javase/8/docs/api/java/text/Format.html" rel="noreferrer"><code>java.text.Format</code></a></li>
<li>Tất cả các lớp con của <a href="http://docs.oracle.com/javaee/7/api/javax/el/ELResolver.html" rel="noreferrer"><code>javax.el.ELResolver</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Iterator_pattern" rel="noreferrer">Iterator</a> <sup><sub>(nhận biết qua các phương thức hành vi lần lượt trả về các thực thể thuộc một kiểu *khác* từ một hàng đợi)</sub></sup></h3>
<ul>
<li>Tất cả các triển khai của <a href="http://docs.oracle.com/javase/8/docs/api/java/util/Iterator.html" rel="noreferrer"><code>java.util.Iterator</code></a> (do đó bao gồm cả <a href="http://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html" rel="noreferrer"><code>java.util.Scanner</code></a>!).</li>
<li>Tất cả các triển khai của <a href="http://docs.oracle.com/javase/8/docs/api/java/util/Enumeration.html" rel="noreferrer"><code>java.util.Enumeration</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Mediator_pattern" rel="noreferrer">Mediator</a> <sup><sub>(nhận biết qua các phương thức hành vi nhận thực thể của kiểu abstract/interface khác (thường sử dụng mẫu command) để ủy quyền/sử dụng thực thể đó)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/Timer.html" rel="noreferrer"><code>java.util.Timer</code></a> (tất cả các phương thức <code>scheduleXXX()</code>)</li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Executor.html#execute-java.lang.Runnable-" rel="noreferrer"><code>java.util.concurrent.Executor#execute()</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ExecutorService.html" rel="noreferrer"><code>java.util.concurrent.ExecutorService</code></a> (các phương thức <code>invokeXXX()</code> và <code>submit()</code>)</li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ScheduledExecutorService.html" rel="noreferrer"><code>java.util.concurrent.ScheduledExecutorService</code></a> (tất cả các phương thức <code>scheduleXXX()</code>)</li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#invoke-java.lang.Object-java.lang.Object...-" rel="noreferrer"><code>java.lang.reflect.Method#invoke()</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Memento_pattern" rel="noreferrer">Memento</a> <sup><sub>(nhận biết qua các phương thức hành vi thay đổi trạng thái nội bộ của *toàn bộ* thực thể)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/Date.html" rel="noreferrer"><code>java.util.Date</code></a> (các phương thức setter thực hiện điều này, <code>Date</code> được biểu diễn nội bộ bằng một giá trị kiểu <code>long</code>)</li>
<li>Tất cả các triển khai của <a href="http://docs.oracle.com/javase/8/docs/api/java/io/Serializable.html" rel="noreferrer"><code>java.io.Serializable</code></a></li>
<li>Tất cả các triển khai của <a href="http://docs.oracle.com/javaee/7/api/javax/faces/component/StateHolder.html" rel="noreferrer"><code>javax.faces.component.StateHolder</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Observer_pattern" rel="noreferrer">Observer (hoặc Publish/Subscribe)</a> <sup><sub>(nhận biết qua các phương thức hành vi gọi một phương thức trên thực thể của một kiểu abstract/interface *khác*, tùy thuộc vào trạng thái của chính nó)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/Observer.html" rel="noreferrer"><code>java.util.Observer</code></a>/<a href="http://docs.oracle.com/javase/8/docs/api/java/util/Observable.html" rel="noreferrer"><code>java.util.Observable</code></a> (ít khi được dùng trong thực tế)</li>
<li>Tất cả các triển khai của <a href="http://docs.oracle.com/javase/8/docs/api/java/util/EventListener.html" rel="noreferrer"><code>java.util.EventListener</code></a> (hầu như xuất hiện khắp Swing)</li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpSessionBindingListener.html" rel="noreferrer"><code>javax.servlet.http.HttpSessionBindingListener</code></a></li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpSessionAttributeListener.html" rel="noreferrer"><code>javax.servlet.http.HttpSessionAttributeListener</code></a></li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/faces/event/PhaseListener.html" rel="noreferrer"><code>javax.faces.event.PhaseListener</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/State_pattern" rel="noreferrer">State</a> <sup><sub>(nhận biết qua các phương thức hành vi thay đổi cách hoạt động của nó tùy thuộc vào trạng thái của thực thể vốn có thể kiểm soát được từ bên ngoài)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/faces/lifecycle/Lifecycle.html#execute-javax.faces.context.FacesContext-" rel="noreferrer"><code>javax.faces.lifecycle.LifeCycle#execute()</code></a> (được điều khiển bởi <a href="http://docs.oracle.com/javaee/7/api/javax/faces/webapp/FacesServlet.html" rel="noreferrer"><code>FacesServlet</code></a>, hành vi phụ thuộc vào phase (trạng thái) hiện tại của vòng đời JSF)</li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Strategy_pattern" rel="noreferrer">Strategy</a> <sup><sub>(nhận biết qua các phương thức hành vi trong một kiểu abstract/interface gọi một phương thức trong bản triển khai của một kiểu abstract/interface *khác* vốn được *truyền vào* dưới dạng đối số của phương thức)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/util/Comparator.html#compare-T-T-" rel="noreferrer"><code>java.util.Comparator#compare()</code></a>, được thực thi bởi <code>Collections#sort()</code>.</li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpServlet.html" rel="noreferrer"><code>javax.servlet.http.HttpServlet</code></a>, phương thức <code>service()</code> và tất cả các phương thức <code>doXXX()</code> đều nhận <code>HttpServletRequest</code> và <code>HttpServletResponse</code> và bộ triển khai phải xử lý chúng (không được lưu chúng dưới dạng biến thực thể!).</li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/servlet/Filter.html#doFilter-javax.servlet.ServletRequest-javax.servlet.ServletResponse-javax.servlet.FilterChain-" rel="noreferrer"><code>javax.servlet.Filter#doFilter()</code></a></li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Template_method_pattern" rel="noreferrer">Template method</a> <sup><sub>(nhận biết qua các phương thức hành vi vốn đã được định nghĩa một hành vi "mặc định" bởi một kiểu abstract)</sub></sup></h3>
<ul>
<li>Tất cả các phương thức không trừu tượng (non-abstract methods) của <a href="http://docs.oracle.com/javase/8/docs/api/java/io/InputStream.html" rel="noreferrer"><code>java.io.InputStream</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/io/OutputStream.html" rel="noreferrer"><code>java.io.OutputStream</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/io/Reader.html" rel="noreferrer"><code>java.io.Reader</code></a> và <a href="http://docs.oracle.com/javase/8/docs/api/java/io/Writer.html" rel="noreferrer"><code>java.io.Writer</code></a>.</li>
<li>Tất cả các phương thức non-abstract của <a href="http://docs.oracle.com/javase/8/docs/api/java/util/AbstractList.html" rel="noreferrer"><code>java.util.AbstractList</code></a>, <a href="http://docs.oracle.com/javase/8/docs/api/java/util/AbstractSet.html" rel="noreferrer"><code>java.util.AbstractSet</code></a> và <a href="http://docs.oracle.com/javase/8/docs/api/java/util/AbstractMap.html" rel="noreferrer"><code>java.util.AbstractMap</code></a>.</li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpServlet.html" rel="noreferrer"><code>javax.servlet.http.HttpServlet</code></a>, tất cả các phương thức <code>doXXX()</code> theo mặc định gửi một lỗi HTTP 405 "Method Not Allowed" về cho response. Bạn có thể tự do triển khai hoặc không triển khai bất kỳ phương thức nào trong số chúng.</li>
</ul>
<h3><a href="http://en.wikipedia.org/wiki/Visitor_pattern" rel="noreferrer">Visitor</a> <sup><sub>(nhận biết qua hai kiểu abstract/interface *khác nhau* có các phương thức định nghĩa nhận kiểu abstract/interface *còn lại*; kiểu này thực sự gọi phương thức của kiểu kia và kiểu kia thực thi chiến lược mong muốn trên nó)</sub></sup></h3>
<ul>
<li><a href="http://docs.oracle.com/javase/8/docs/api/javax/lang/model/element/AnnotationValue.html" rel="noreferrer"><code>javax.lang.model.element.AnnotationValue</code></a> và <a href="http://docs.oracle.com/javase/8/docs/api/javax/lang/model/element/AnnotationValueVisitor.html" rel="noreferrer"><code>AnnotationValueVisitor</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/javax/lang/model/element/Element.html" rel="noreferrer"><code>javax.lang.model.element.Element</code></a> và <a href="http://docs.oracle.com/javase/8/docs/api/javax/lang/model/element/ElementVisitor.html" rel="noreferrer"><code>ElementVisitor</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/javax/lang/model/type/TypeMirror.html" rel="noreferrer"><code>javax.lang.model.type.TypeMirror</code></a> và <a href="http://docs.oracle.com/javase/8/docs/api/javax/lang/model/type/TypeVisitor.html" rel="noreferrer"><code>TypeVisitor</code></a></li>
<li><a href="http://docs.oracle.com/javase/8/docs/api/java/nio/file/FileVisitor.html" rel="noreferrer"><code>java.nio.file.FileVisitor</code></a> và <a href="http://docs.oracle.com/javase/8/docs/api/java/nio/file/SimpleFileVisitor.html" rel="noreferrer"><code>SimpleFileVisitor</code></a></li>
<li><a href="http://docs.oracle.com/javaee/7/api/javax/faces/component/visit/VisitContext.html" rel="noreferrer"><code>javax.faces.component.visit.VisitContext</code></a> và <a href="http://docs.oracle.com/javaee/7/api/javax/faces/component/visit/VisitCallback.html" rel="noreferrer"><code>VisitCallback</code></a></li>
</ul>
</div>
