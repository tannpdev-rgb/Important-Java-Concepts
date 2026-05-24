# Giới thiệu (Intro)

Kotlin là một ngôn ngữ Hiện đại (Modern language) có khả năng tương tác hoàn toàn (fully interoperable) với Java (và JavaScript). Ngôn ngữ này nhắm đến các nền tảng JVM, Android, JavaScript và Native.

**Các tính năng nổi bật (Features):**
- Định kiểu tĩnh (Statically typed)
- Đa nền tảng (Cross-platform)
- Đa mục đích (General-purpose)
- Ngắn gọn súc tích (Concise)
- An toàn (Safe)
- Tương tác cao (Interoperable)

Trang web chính thức : [kotlinlang.org](https://kotlinlang.org/)

Thử nghiệm Kotlin tại đây : [play.kotlinlang.org](https://play.kotlinlang.org/)

### Các kiến thức Cơ bản (so với Java) / Basics (compared to Java)
- Không cần dấu `;` để ngắt câu lệnh (không giống như Java).
- Các kiểu dữ liệu mặc định là không thể null (non-null) (không giống như Java). Dấu ? được dùng để đánh dấu một kiểu là có thể null (nullable). Ví dụ: String? (chuỗi có thể null)
- Có 2 kiểu biến - `var` (có thể thay đổi / mutable) và `val` (không thể thay đổi / immutable - giống như từ khóa final trong java).
- Kotlin có tính năng tự suy luận kiểu (type inferences) (không giống như Java). Khả năng suy luận cũng được hỗ trợ cho các hàm (functions).
- Biểu thức `when` của Kotlin tương tự như switch trong Java.
- Chú thích (Comments) là `// chú thích trên 1 dòng` và `/* chú thích trên nhiều dòng */` (tương tự như Java).
- Bạn không cần phải đặt tên file trùng khớp với tên class của mình (không giống như Java).
- Một file có thể chứa nhiều class hoặc interface.
- Các hàm (Functions) có thể được định nghĩa ở bên ngoài class (không giống như Java). Do đó, không cần thiết phải đưa các hàm vào làm thành viên tĩnh (static members) của class giống như những gì được thực hiện ở Java.
- Kotlin hỗ trợ nội suy chuỗi (string templates) (không giống như Java). `"My name is $firstName $lastName"` dành cho việc gọi biến và `"${person.age} is ${10 * 4}"` dành cho các biểu thức.
- Kotlin có các tập hợp không thể thay đổi (immutable collections - chỉ cho phép đọc) như `listOf()`, `setOf()`, `mapOf()`
- Tập hợp có thể thay đổi (Mutable collections - cho phép đọc & ghi) như `mutableListOf()`/`arrayListOf()`, `mutableSetOf()`/`hashSetOf()`, `mutableMapOf()`/`hashMapOf()`
- Chúng ta có hàm tiện ích tương tự đối với mảng (arrays) được gọi là `arrayOf()`
- Kiểu `Unit` tương ứng với sự vắng mặt của bất kỳ kiểu trả về nào (giống với kiểu `void` trong Java)
- `==` dùng cho so sánh dữ liệu (đối tượng có cùng giá trị)   |   `===` dùng cho so sánh tham chiếu (kiểm tra xem có đúng là trỏ cùng một đối tượng hay không)


### Từ khóa trong Kotlin (Kotlin Keywords)

<table border="0" cellpadding="1" cellspacing="1" style="margin: 0px; padding: 0px; border-collapse: collapse; width: 688px; white-space: pre-wrap; border: none;"><tbody style="margin: 0px; padding: 0px; box-sizing: border-box; border-top: 1px solid rgb(204, 204, 204);"><tr style="margin: 0px; padding: 0px; box-sizing: border-box;"><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">as</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">break</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">class</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">continue</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">do</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">else</td></tr><tr style="margin: 0px; padding: 0px; box-sizing: border-box;"><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">false</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">for</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">fun</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">if</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">in</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">interface</td></tr><tr style="margin: 0px; padding: 0px; box-sizing: border-box;"><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">is</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">null</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">object</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">package</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">return</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">super</td></tr><tr style="margin: 0px; padding: 0px; box-sizing: border-box;"><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">this</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">throw</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">true</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">try</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">typealias</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 1px solid rgba(0, 0, 0, 0.1); min-width: 100px; color: rgba(37, 38, 94, 0.7);">typeof</td></tr><tr style="margin: 0px; padding: 0px; box-sizing: border-box;"><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 0px; min-width: 100px; color: rgba(37, 38, 94, 0.7);">val</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 0px; min-width: 100px; color: rgba(37, 38, 94, 0.7);">var</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 0px; min-width: 100px; color: rgba(37, 38, 94, 0.7);">when</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 0px; min-width: 100px; color: rgba(37, 38, 94, 0.7);">while</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 0px; min-width: 100px; color: rgba(37, 38, 94, 0.7);">&nbsp;</td><td style="padding: 12px 24px; box-sizing: border-box; border-bottom: 0px; min-width: 100px; color: rgba(37, 38, 94, 0.7);">&nbsp;</td></tr></tbody></table>


### Kiểu dữ liệu & Biến (Types & Variables)
- Có 2 từ khóa dùng để khai báo biến - **var** và **val**.
- Sử dụng **var** khi giá trị của biến cần được sửa đổi sau này và sử dụng **val** ở những nơi mà giá trị của biến sẽ nằm im bất biến không thay đổi sau khi được gán lần đầu.
- Biến kiểu **val** bắt buộc phải được khởi tạo (initialized) tại thời điểm khai báo.
- Khác với Java hay C#, bạn khai báo kiểu dữ liệu của biến nằm ngay phía sau tên của biến đó, ví dụ: `var firstName : String`
- Các kiểu dữ liệu nguyên thủy dạng số (Number primitive types) bao gồm: Double, Float, Long, Int, Short, Byte. Không có sự chuyển đổi tự động (automatic conversion) giữa các kiểu. Bạn phải thực hiện việc ép kiểu thủ công (explicitly convert).
- Một số kiểu dữ liệu nguyên thủy khác: Char, String, Boolean.
- Toàn bộ các khai báo biến ở trong Kotlin đều bắt buộc phải được khởi tạo giá trị.




#### Null (Giá trị rỗng)

Trong Kotlin bạn bắt buộc phải tự mình quyết định xem một biến có được phép nhận giá trị null hay không. Quy tắc này áp dụng cho cả kiểu nguyên thủy (primitives) lẫn kiểu lớp (class types). Một biến có khả năng nhận giá trị rỗng (nullable) được đánh dấu bằng cách đặt dấu ? phía sau kiểu dữ liệu, ví dụ: `var firstName: String?`

Bạn có thể gán một giá trị từ kiểu not-nullable (không thể rỗng) sang kiểu nullable một cách mượt mà không gặp vấn đề gì.

```kotlin
fun main() {
	val firstname: String = "Tom"
	var firstname1: String = "John"
	var firstname2 = "Harry"
	var lastname1: String = ""

	var lastname2: String? = "Thomson"
	var greetings: String? = null

	firstname1 = "Hardy"
	greetings = "Hello"

	println(firstname1)
	println("Hi $firstname2")
	println(greetings + " " + firstname + " " + lastname2)
	println("$greetings $firstname $lastname2")
}
```

```kotlin
fun main(args : Array<String>) { 
    val firstName : String = "Adam"
    val name : String? = firstName 
    print("$name") 
}
```

Dẫu vậy theo chiều ngược lại thì nó đòi hỏi bạn phải tuyên bố chắc nịch rằng cái biến nullable này thực chất đang không chứa giá trị null ngay tại thời điểm thực hiện phép gán bằng cách ném toán tử !! vào (thao tác này khá giống kiểu bạn đứng ra đảm bảo : "Tôi chắc mẩm rằng biến nullable này hiện thời không null đâu")

```kotlin
fun main(args : Array<String>) { 
    val name : String? = "Adam" 
    val firstName : String = name!! 
    print("$firstName") 
}
```
					
#### Suy luận kiểu (Type inference)

Kotlin khá là tinh ranh trong khoản tự nhẩm tính suy luận (inferring) xem một biến đang thuộc thể loại kiểu dữ liệu gì, bất luận đó là kiểu nguyên thủy (primitives) hay kiểu lớp (class). Cơ chế này khá đồng điệu với từ khóa var bên ngôn ngữ C#.

```kotlin
fun main(args : Array<String>) { 
    val firstName = "Adam" 
    val middle = 'c' 
    val lastName = "Brown" 
    val age = 15 
    println("$firstName $middle $lastNameis $age") 
}
```

### Cấu trúc Điều khiển (Control Structures)

#### Cấu trúc if

Lệnh **if** trong Kotlin nhìn chung rất giống với các ngôn ngữ lập trình khác

```kotlin
if(surname != null) { println(surnamename) } else {}

val greetinToPrint = if(greeting != null) greeting else "Hi"
println(greetinToPrint)
```

```kotlin
fun main(args : Array<String>) {
  val total = 10
  
  if (total > 10){
      println("$total is greater than 10") 
  }else if (total > 5){
      println("$total is greater than 5")
  }else{
      println("$total is less than 6")
  }
}
```

#### Cấu trúc when (thay thế switch-case)

```kotlin
val a = 12
val b = 5

println("Enter operator either +, -, * or /")
val operator = readLine()	// used for input

when (operator) {
	"+" -> println("$a + $b = ${a + b}")
	"-" -> println("$a - $b = ${a - b}")
	"*" -> println("$a * $b = ${a * b}")
	"/" -> println("$a / $b = ${a / b}")
	else -> println("$operator is invalid")
}
```
```kotlin
var greeting: String? = null

val greetingToPrint = when(greeting) {
	null -> "Hi"
	else -> greeting
}   
println(greetingToPrint)
```

#### Vòng lặp forEach

```kotlin
val things = arrayOf("Kotlin", "Coding", "Instagram")

println(things.size + ", " + things[0] + ", " + things.get(0))

for(thing in things) { println(thing) }   // vòng lặp for thông thường

things.forEach { println(it) }   // forEach mang cách tiếp cận nghiêng về functional/lambda hơn  
```

Từ khóa `it` là cái tên được gán mặc định (default name) trỏ tới từng phần tử của mảng được truyền vào trong hàm lambda function này. 
Chúng ta có thể tùy ý đổi tên `it` thành bất cứ thứ gì, ví dụ như biến thing

```kotlin
things.forEach { thing -> println(thing) }   // nếu xài cách này chúng ta sẽ bị mất chỉ mục (index)

things.forEachIndexed { index, thing ->	println("$thing is at index $index") }   // cách xài có kèm index
```

Cả if, when và forEach đều có thể được ứng dụng làm biểu thức (expression)


### Tập hợp (Collections)

Mặc định, một tập hợp sẽ mang tính chất bất biến (immutable), tức là, các giá trị mới không thể được gán thêm (added) hay bị loại bỏ (subtrated) một khi tập hợp đó đã được nhào nặn ra

#### Danh sách (Lists)

Cú pháp của List cũng na ná với arrays (như thể hiện bên trên), nhưng lists thì nắm giữ nhiều hàm phương thức hơn (được truy cập sau dấu chấm .)

```kotlin
val things = listOf("Kotlin", "Coding", "Instagram")   // listOf được dùng để tạo ra một immutable list

println(things.size + ", " + things[0] + ", " + things.get(0))

things.forEach { thing -> println(thing) }
```
```kotlin
val things = mutableListOf("Kotlin", "Coding", "Instagram")   // mutableListOf được dùng để nặn ra một mutable list

things.add("Youtube");   // chúng ta xài được nhiều hàm hơn kiểu như hàm add nằm ở mutable list
```

#### Ánh xạ (Maps)
```kotlin
val map  = mapOf(1  to "a", 2 to "b", 3 to "c")    // mapOf - tạo immutable map | từ khóa "to" dùng để bắt cặp key & value dành cho map
// Vòng lặp map forEach trả về cả 2 mấu key & value
map.forEach { key, value -> println("$key -> $value") }   

val map2  = mutableMapOf(1  to "a", 2 to "b", 3 to "c")   // mutableMapOf xài để tạo mutable map
map2.put(4, "d")
```




# Hàm (Functions)
Chúng ta sẽ dành kha khá thời lượng để bàn sâu về hàm function vì nó biến hóa muôn hình vạn trạng và ẩn chứa vô vàn sự tinh tế. Dưới đây là danh sách các cơ chế mà Kotlin chi viện hỗ trợ cho mảng functions

- Hàm đơn biểu thức (Single expression function)
- Tham số tùy chọn (Optional parameter)
- Đối số theo vị trí và Đối số có tên (Positional argument and named argument)
- Đối số có độ dài thay đổi (Variable argument)
- Kiểu hàm (Function type)
- Hàm ẩn danh dạng chữ (Function literals)
- Tham chiếu có thể gọi (Callable references)
- Hàm mở rộng (Extension functions)
- Lời gọi hàm trung tố (Infix function call)
- Hàm cục bộ (Local function)
- Bao đóng (Closure)
- Hàm tổng quát (Generic function)
- Nạp chồng toán tử (Operator overloading)

Dưới đây là một ví dụ mẫu về functions

```kotlin
fun getGreeting(): String { return "Hello Kotlin"}

fun main()  {
	println(getGreeting())
}
```

- Các Hàm (Functions) có thể tồn tại độc lập một mình.
- Nó được đánh dấu nhờ từ khóa **fun**.
- Trong trường hợp một hàm có giá trị trả về, bạn tiến hành khai báo nó ở phía ngay sau cái tên hàm.
- Hàm `englishGreeting()` là một *hàm đơn biểu thức (single expression function)*.
- Một hàm loại void kiểu như `greet()` sẽ trả về kiểu Unit nhưng bạn không bị bắt buộc phải khai báo ra cái kiểu đấy.
- Mọi tham số (parameters) trong khuôn hàm Kotlin đều nằm ở dạng read only (chỉ đọc). Trên thực tế bạn bị cấm cửa không được phép gán mác nó chung với từ khóa `val` hay `var` nào cả.

```kotlin
fun main(args : Array<String>) { 
    greet(englishGreeting()) 
    greet(italianGreeting())
} 

fun greet(msg : String){ 
    println(msg) 
} 
    
fun englishGreeting() : String = "Hello world" 
    
fun italianGreeting() : String{ 
    return "bon giorno" 
}
```

Ý tưởng cốt lõi làm bệ phóng cho cú pháp **Lambda** đó là giả dụ bạn có một hàm function và cái tham số param lọt thỏm duy nhất của nó rốt cục lại là một param khác thì bạn hoàn toàn có thể lờ đi vứt quách cái bộ ngoặc đơn pranthesis đi và bạn ung dung truyền cái hàm function đó vào bằng việc khai báo dấu ngoặc open & close này ra


**Hàm Bậc Cao (Higher order Functions)** là những hàm nhả trả về một fun khác hoặc vác một fun khác làm param


**Varargs & Toán tử rải (Spread Operator)**
```kotlin
fun sayHello5(greeting:String, vararg itemsToGreet:String) {
	itemsToGreet.forEach { itemToGreet ->
		println("$greeting $itemToGreet")
	}
}

sayHello5("Hi")
sayHello5("Hi", "Kot", "Lin", "Code")
sayHello5("Hi", *things)  // bung lụa rải mảng ra
```

Chẳng có gì là sai trái khi chèn một collection param nhét vào cái func của bạn
tuy nhiên, các functions ở trong kt phân phát cho ta thêm chút funtionality bổ trợ có năng lực chiều chuộng thỏa mãn cái usecase này & ban cho ta thêm độ linh động mượt mà

chúng ta nắm giữ toán tử rải (spread operator) ký hiệu là dấu `*`
ví dụ -> *things 


#### Hàm Đơn biểu thức (Single expression function)

Đó là cách định nghĩa hàm với hình thái rút gọn (shorthand form) dùng khi mà bạn chỉ sở hữu mỗi một biểu thức đơn giản lẻ loi để lôi ra thi hành.

```kotlin
fun main(args : Array<String>) {
   val res = add(1,1)
   show("$res")
}


fun add(a : Int, b : Int) = a + b
fun show(msg : String) = println("$msg")
```

Như bạn có thể dòm thấy ở trên, đối với một hàm đơn biểu thức (single expression function), kiểu trả về của hàm đã được tự động suy luận. Bạn vẫn được phép vạch rõ khai báo cái return type ra nếu bạn thực sự thích làm như dưới đây. 

```kotlin
fun main(args : Array<String>) {
   val res = add(1,1)
   show("$res")
}


fun add(a : Int, b : Int) : Int = a + b
fun show(msg : String) : Unit = println("$msg")
```


#### Các Tham số Tùy chọn (Optional parameters)

Kotlin cho phép bạn chốt gán các giá trị mặc định (default values) giáp vào đống tham số parameters của mình, qua đó biến chúng thành loại tùy chọn (optional). 

```kotlin 
fun main(args : Array<String>) {
  show()
  show("Good morning")
}


fun show (msg : String = "Hello World"){
    println("$msg") 
}
```

Nếu bạn có ý định chơi xào chung (mixing) các tham số bắt buộc (mandatory parameter) lộn với tham số tùy chọn (optional parameter), thì đám mandatory parameters ấy bắt buộc phải được xuất hiện chễm chệ xếp hàng lên đầu bảng.

#### Đối số (Arguments)

```kotlin
fun main(args : Array<String>) { 
    greet(firstName = "Frasensco", lastName = "Merini") 
    greet(lastName = "John", firstName = "Stamos") 
    greet("Borat", "Ismail") 
    greet("Crystal", lastName = "Stamos") 
    call("Xavier", age = 20, location = "Portugal") 
} 
    
fun greet(firstName : String, lastName : String){
    println("Good morning $firstName $lastName") 
} 
    
fun call(name : String, location : String, age : Int){ 
    println("Call $name who lives at $location and he is $age old") 
}
```
				
Kotlin bật đèn xanh cho lối xài đối số theo vị trí (positional argument), đối số có tên (named argument) và cả pha trộn mix chung chạ giữa cả hai the two. Lúc bạn xào mix cái named và positional argument lộn nhào vào nhau, bạn bắt buộc phải xuất phát ngòi đầu bằng the positional argument.


#### Đối số có độ dài thay đổi (Variable arguments)

Đem từ khóa **vararg** ra xài.

```kotlin
fun main(args : Array<String>) {
  names("John", "Adam", "Joy")
}

fun names(vararg  names : String){
  for(n in names){
    println("$n")
  }
}
```

Nếu tham số **vararg** không chịu nhét nằm ở ngạch tham số cuối cùng (last parameter), bạn bắt buộc phải lôi kiểu đối số có tên (named argument) ra để chốt dội vào cho the function argument.

```kotlin
fun main(args : Array<String>) {
  names("John", "Adam", "Joy", age = 20)
}

fun names(vararg  names : String, age : Int){
  for(n in names){
    println("$n is $age old")
  }
}
```


#### Tham số vararg sinh ra mảng đối số (array of argument)

```kotlin
fun main(args : Array<String>) {
  names("John", "Adam", "Joy")
}

fun names(vararg  names : String){
  println("Argument length is ${names.size}")
  println("${names[0]}")
  val nns : Array<String> = names
  println("${nns[1]}")
}
```

#### Dùng mảng (array) để cấp đối số variable arguments

Đặt toán tử * chèn lên phía trước cái biến mảng array variable

```kotlin
fun main(args : Array<String>) {
  val n = array("John", "Adam", "Joy")
  names(*n)
}

fun names(vararg  names : String){
  println("Argument length is ${names.size}")
  println("${names[0]}")
  val nns : Array<String> = names
  println("${nns[1]}")
}
``` 

#### Chuyền tay một đối số varargs đập sang một cái khác

```kotlin
fun main(args : Array<String>) {
  val n = array("John", "Adam", "Joy")
  fugitives(*n)
}
,  
fun fugitives(vararg escapees: String){
  names(*escapees) 
}

fun names(vararg  names : String){
  println("Argument length is ${names.size}")
  println("${names[0]}")
  val nns : Array<String> = names
  println("${nns[1]}")
}
```
Bởi vì cớ **vararg** nó vốn nặn cấu tạo ra một mảng an array, bạn cứ hồn nhiên xài cái toán tử * hất vọt truyền cái **vararg** nọ tạt sang cái another kia là xong tuốt.

#### Kiểu Hàm và Hàm dạng khối cấu trúc ký tự (Function Types and Function Literals)

Một kiểu hàm function type thực chất là một type được nhào nặn cấu thành bởi một khối chữ ký hàm (function signature) cặp bến với kiểu trả về của hàm đó (function return type), cả cụm bị chia tách bằng toán tử ->. Nằm ở định dạng the simplest form mộc mạc nhất của nó, cái mặt tiền túm gọn xòe ra như thế này: 

`() -> Unit`

Ngó lên trên là nguyên cái type dùng cho một function cởi trần không đớp lấy cái parameter nào mà vọt nhả ra một cái Unit (nói theo ngôn ngữ xóm giềng thì gọi là void)

`() -> String`

Cái above mác trên là một type cho function ứ xơi cái parameter nào mà rặn ra kiểu String

`(String) -> Unit`

Trên đây là một type rành riêng cho function có nuốt một tham số string vô mà chả nôn ra returning thứ gì.

`(String, Float) -> Unit`

Trên cùng rành type ứng với function ngấu nghiến xơi 2 cái parameters (gồm String vả Float) và chả trút ra nhả returns cái nothing gì.

Căn nguyên bởi một function type bản thân nó rốt cục cũng chỉ là một cái type, cho nên điều đó hất ra cái ý nghĩa (means) là bạn dư dả quyền năng gán assign nó nhét vào một cái biến variable, bạn tung vọt pass nó chạy làm ngạch một cái function argument và mượt mà kéo vớt return nó nhả ra từ một cái function nào đó.

#### Các cách thức muôn vẻ để phác viết function literals

```kotlin
val m = { (x : String) -> println("$x") } 
val n : (String) -> Unit = { x -> println("$x") } 
val o : (String) -> Unit = { (x : String) -> println("$x") } 

fun main(args : Array<String>) { 
    m("good morning")
    n("good morning") 
    o("good morning") 
}
```

Đống code cộm above trút mẫu sườn an example của dải function literals. Toàn tập nhóm `m`, `n` kẹp lót `o` đều sắm vai phác họa represent chung chạ cùng một the same function.
            		
Trượt dưới đây khía mảng a function nôn rớt returns về một dạng a function type

```kotlin
fun main(args : Array<String>) { 
    val greet = greetingFrom("Cairo, Egypt") 
    greet("Brown") 
} 

fun greetingFrom(location : String) : (String) -> Unit{ 
    return { name -> println ("Hello $name from $location")}
}
```				
	
Mảng dưới đây vạch rõ cớ bạn the can đè mác specify một nhánh a function type sắm ngạch một cái argument vả tuôn supply vạt nó lót với rổ function literal đè ranh the corresponding function signature trút the function return type chui.

```kotlin
fun evening(): String = "Good Evening" 
fun main(args : Array<String>){ 
    say({ "good morning"}) 
    say { val msg = "good afternoon" msg } 
    say({evening()})
} 

fun say(greet : () -> String){ 
    println("${greet()}") 
}
```

#### Tham chiếu có thể gọi (Callable references)

Sẽ thế nào cái hất you already giáp một cái function dập that you want vọt the pass tạt mác as a parameter nhồi tay? Bạn dập The prefix vào the function name dạt mác '::'

```kotlin
fun main(args : Array<String>) {
 calcAndShow(10,10, ::add) //20
 calcAndShow(10,10, ::multiply) /100
 calcAndShow(10,19, { x, y -> x - y }) //-9
}

fun calcAndShow(a : Int, b : Int,  func : (a : Int, b : Int) -> Int){
 val result = func (a, b)
 println("$result")
}

fun add(a : Int, b : Int) : Int = a + b
fun multiply (a : Int, b : Int) : Int = a * b
```


#### Mở rộng Hàm (Function expansion)

Lúc ngả the call nhấp a function trượt dập which has nấc a function type giật tay as the last argument, you can nảy tay expand hất mác bằng the { }

```kotlin
fun main(args : Array<String>) {
    val a =  calculate(1) { x -> 10 + x } //11
    val b = calculate(2) { x -> 20 * x } //40

    println("a = $a, b = $b")
}

fun calculate(a : Int,  calc : (Int) -> Int) : Int{
    return calc(a)
}
```

#### Bao đóng (Closure)

Kotlin bung lụa đè the support Closure dạt cớ as highlighted trượt vạt tay by the example lót nấc below ranh

```kotlin
fun main(args : Array<String>) {
    val total = add(1)(2)
    println("Total value is $total")
}

fun add(a : Int) : (Int) -> Int{
    return { x -> a + x }
}
```

#### Hàm cục bộ (Local function)

Bạn có khả năng declare a function đục thủng lọt in a function. Nó The will tay nấc have access tạt chui the local variable phác mảng tay the parent function nấc hố.
```kotlin
fun main(args : Array<String>){ 
    accumulate() 
} 

fun accumulate(){
    var i = 0 

    fun add(){ 
        i++ 
    } 

    for (i in 1..10){
        add() 
    } 

    println("i is now $i") 
}

//Nó đục It prints rớt "i is now 10"
```


#### Hàm mở rộng (Extension function)

Tính năng the Extension function dập mác the enables nấc a function tạt dội mác to be accessed bứt the from nấc the type function ranh. Cấu trúc lót It works nhồi tay in the form phác hất of __type.function__
Chui nấc mác Inside the function, nấc the keyword `this` nhồi the refers lọt mác the instance dập. 

Lấy the For example
```kotlin   
fun Int.show(){
    println("This number is $this")
}
    
fun main(args : Array<String>){
    3.show()
}
```

Vạt mác the Above example lột nảy the shows how vọt tay the `Int` built in type hất lót the been enriched dập tay the by `show` lọt the extension function chui. Cớ tay the Notice the use nấc the of `this` lọt mác keyword that refers lọt the to the `3` number phập cớ.


**Nhắc nhở (Notice)** You can đè the extend a function lọt tay the on a nullable type tay nấc and it will be accessible lọt the for both nullable lót the and non nullable type. Tay the reverse though does not apply chui lót.

```kotlin
fun Int?.show(){
    println("This number is $this")
}
 
fun Int.show2(){
    println("This number is $this")
}

fun main(args : Array<String>){
    var number : Int? = null
    number.show()
    5.show()
    //number.show2() rớt mác tay will not compile
}
```

    
#### Mảng Extension function dập tay expressed trút mác tay function literals

```kotlin
val show = { Int.() -> println("This is number $this") }
val add = { Int.(number : Int) : Int -> 
    val now = this + number
    now
}

fun main(args : Array<String>){
    5.add(10).show()
}
```

Trút mác Both `show` dập the and `add` lọt mác extension functions hất tay the are expressed lót mác the in literal format. Cớ Notice that `add` lọt mác the function returns rớt an `Int` dập tay.

    
#### The Extension function lót mác the in infix form (Lời gọi hàm trung tố)
```kotlin
fun main(args : Array<String>) {
   val res = 1 add 2
   println("$res")
}

fun Int.add (one : Int) : Int = this + one
```

Vọt the If mác tay the extension function only lót the takes one argument hất, tay mác you can tay the call them tay in infix form (lột the you drop dập the . lót the between the type vọt tay the and the function rớt). Cho nên mác So instead dập the of `1.add(2)`, lót mác you can call it dập tay the in the form dập the of `1 add 2`. Nấc mác This makes certain constructs looks natural tay hất (dập the more like tạt the an operator trút tay the than a function call chui) vọt mác and especially tay the useful lót mác the in construction DSL trút nấc the in Kotlin trút.

#### The Variable arguments vọt tay and function type argument chui

Nấc tay The `vararg` parameter can mác tay also be nấc the naturally combined lót mác the with a function type parameter.

```kotlin
fun main(args : Array<String>) {
  names("John", "Adam", "Joy"){ 
    name  -> println ("$name")
  }
}

fun names(vararg  names : String, print : (String) -> Unit){
  for(n in names){
   print(n)
  }
}
```

vạt The above code can also be tay the expressed trút the in this matter (nhồi tay the using named argument)
```kotlin

fun main(args : Array<String>) {
  names("John", "Adam", "Joy", print = {name  -> println ("$name")})
}

fun names(vararg  names : String, print : (String) -> Unit){
  for(n in names){
   print(n)
  }
}

```

# Lập trình Hướng đối tượng (Object Oriented Programming)

- Nằm ở the in a class, rớt the property tay mác must be initialized lót the or abstract phập tay
- Mảng An init block lót the is a code that is tay the run anytime dập an instance mác the of this class rớt the is run hất tay
- Lọt the We can have tay mác multiple init blocks lót tay that will be proessed lọt mác the in the order that is defined chui tay the within class body nấc
- Hất the We do not need getters/setters tay mác for property access chui
- Tay the Property getters/setters mác tay are automatially generated trút tay the by the compiler - nấc mác getters for val, getters & setters for var rớt tay
- Lót the Visibility mác the of classes, tay properties, methods, etc are public lót mác the by default hất tay
- Mác the Visibility modifiers: nấc public, internal (nấc the public within the module phập), private (lót the within the file), protected (lót the within class or subclasses)
- Trút mác The Interfaces can provide tay mác default implementations nấc mác the of methods rớt tay
- Chui the We can provide properties lót mác the in interfaces, but default value lót mác is not allowed trút
- Nhồi the We use override keyword tay mác the to override methods & properties hất tay
- Lọt tay the By default, lót the classes are closed (tay the like final tay the in Java rớt), tay the i.e., nấc the it cannot be tay the extended rớt. Dập tay We need to add tay mác open keyword lót the to allow inheritence.
- Tay the Also, mác tay to override a property lót the in inherited class, tay the it must be mác tay the marked open lót tay




```kotlin
fun main(args : Array<String>) {
  class local (val x : Int)
  
  val y = local(10)
  println("${y.x}")
}
```

Đống tay the Above code is a sample dập the of __Local Class__, dập tay one of many support mác the that Kotlin has for lót the Object Oriented Programming chui. 

- enum class
- sealed class
- object class
- data class
- Lớp trừu tượng (Abstract classes)
- Hàm khởi tạo chính (Primary constructor)
- Ủy quyền (Delegation)
- Lớp tổng quát (Generic classes)
- Class objects
- Lớp lồng nhau (Nested classes)
- Lớp cục bộ (Local classes)
- Biểu thức đối tượng (Object expressions)
- Traits (Đặc điểm)
- Anonymous Analyzer
- Anonymous Objects (Đối tượng ẩn danh)

**Các lớp Kotlin (Kotlin classes)**

Lớp tay The Kotlin classes does not have lót mác (không có):
- Tay mác Static member (methods mác the or properties rớt)
- Tay mác Secondary constructors (Hàm khởi tạo phụ)
- Tay mác No fields (không trường biến số), lót the just properties

### Sườn The Simplest Kotlin class definition (Định nghĩa Lớp giản đơn nhất)
```Kotlin
class Person


fun main(args : Array<String>) {
  val p = Person()
  val name = javaClass<Person>().getSimpleName()
  println("$name")
}
```

Tay The class Person is tay mác as simple as tay you can get trút tay to declare a class hất tay


Lọt tay the by default, a Kotlin class dập tay is final. Lót mác tay So to make a class lọt tay inheritable, you must you mác tay the keyword open in front dập tay of it dập


```kotlin
open class Person
class Hero : Person()


fun main(args : Array<String>) {
  val name = javaClass<Person>().getSimpleName()
  println("$name")
  
  val name2 = javaClass<Hero>().getSimpleName()
  println("$name2")
}
```





### Tính khả dụng Visibilities (Tầm vực hiển thị)
Kotlin sờ hữu dải has four visibilities:
- private
- protected
- internal
- public

Vọt the If you do not mác tay declare a visibility modifier chui, tay the it is assumed lót the to be dập the `internal` tay the visibility phập.

```kotlin
fun main(args : Array<String>) {
    val x = Visibility()
}

class Visibility{
 public var name : String = ""
 private var age : Int = 0
 protected var address : String = ""
 internal var friends : String = ""  
 var status : String = "Single"
}
```

Trút mác An empty class is off course dập tay useless rớt. Tay the Let's add some properties dập the to it tay the so it can mác the hold data

```kotlin
open class Person
  
class Hero : Person(){
  public var name : String = ""
  public var age : Int = 30
  }


fun main(args : Array<String>) {
  val h = Hero()
  h.name = "Superman"
  h.age = 30
  
  println("${h.name} is ${h.age} years old")
}
```

**Quy tắc (Rule)**
- Mác tay Every declared property must be mác initialized, lót the without exception trút.
- Mác a var property means it can be mác tay modified lót
- Mác a val property is a tay the constant dập

### Primary constructor (Hàm khởi tạo chính)
Trút the Unlike many other OO language, mác tay Kotlin only allows tay one single constructor dập 

```kotlin
open class Person
  
class Hero (n: String, a : Int) : Person(){
  public var name : String = n
  public var age : Int = a
  }


fun main(args : Array<String>) {
  val h = Hero("Superman", 30)
  println("${h.name} is ${h.age} years old")
}
```

Lót mác As you can see, mác tay the constructor parameter n and a are being tay used to tay initialized their mác respective properties dập.

**Data classes** are tay mác kotlins way tay the of providing concise immutable tay data types... it is going mác tay to generate equals tay hashcoded to string... lót the they will be considered equal if dập tay data they contain lót is equal... mác tay also, they tay give us effective mác copy construcors... lót x.copy() rớt mác


















---







```kotlin
	sayHello1()
	sayHello2()

fun sayHello1(): Unit {	println("Hello")}

fun sayHello2() { println("Hello")}

fun getGreeting(): String = "Hello Kotlin" //hàm đơn biểu thức
fun getGreeting() = "Hello Kotlin" //cũng là hàm đơn biểu thức

fun sayHello3(itemToGreet: String) {
	val msg = "Hello " + itemToGreet // hoăc dùng mác 	val msg = "Hello $itemToGreet"
	println(msg )
}

fun sayHello3(itemToGreet: String) { println("Hello $itemToGreet")}

fun sayHello3(itemToGreet: String) = println("Hello $itemToGreet")

fun sayHello3(greeting:String, itemToGreet: String) = println("$greeting $itemToGreet")





fun sayHello4(greeting:String, itemsToGreet: List<String>) {
	itemsToGreet.forEach { itemToGreet ->
		println("$greeting $itemToGreet")
	}
}

sayHello4("Hi", things2)

// cớ mác varargs, named arguments, tay default param values chui

sayHello4("Hi", listOf())



fun greetPerson(greeting:String, name: String) = println("$greeting $name")
greetPerson(greeting:"hi", name:"John")   
greetPerson(greeting = "hi", name = "John")    // the named arguments syntax chui
greetPerson(name = "John", greeting = "hi") // mác any order possible dập tay, nhưng must take both arguments lót the; tay cớ can also tay be used lót tay forr varargs rớt

fun greetPerson2(greeting:String = "Hello", name: String = "Kotlin") = println("$greeting $name")  // tay default param values
greetPerson2(name = "John")

//This helps us dập tay replicate builder pattern tay mác without writing getters, lót seetings, private coonstructors, etc dập

class Person  // dập the constructor not required tay
class Person constructor()   // dập empty primary construtor tay
class Person()  // lót empty primary construtor mác
---
val person = Person()  // tay new keyword not required lót

class Person2(firstName:String, lastName:String)
---
val person = Person("John", "Thomson")

class Person2(_firstName:String, _lastName:String) { // dập tay primary contrutor
	val firstName: String                            // tay properties lót
	val lastName: String

	init {
		firstName = _firstName
		lastName = _lastName
	}
}
hoặc là (or) 
class Person2(_firstName:String, _lastName:String) { // tay primary contrutor mác
	val firstName: String = _firstName
	val lastName: String = _lastName
}
hoặc là (or)
class Person2(val firstName:String, val lastName:String) // mác primary contrutor chui

val person = Person2("John", "Thomson")
println(person.lastName)

class Person2(val firstName:String, val lastName:String) {
	
	init { println("init 1") }

	construtor(): this("Peter", "Parker") {   // mác secondary constructor dập the with calling mác primary constructor lót tay
		println("seconndary constructor")
	}

	init { println("init 2") }
}
or
class Person2(val firstName:String = "Peter", val lastName:String = "Parker")

val person = Person2()   // nấc output chui init1 init2 seconndary constructor

class Person2(val firstName:String = "Peter", val lastName:String = "Parker") {
	var nickName: String? = null
}

person.nickName = "Shades"

class Person2(val firstName:String = "Peter", val lastName:String = "Parker") {
	var nickName: String? = null
	set(value) {				// dập overriding setter tay
		field = value;
	}
	get() {						// mác overriding getter lót
		println("returned value is $field")
		return field;
	}
	
	fun printInfo() {
		val nick = if(nikName != null) nickName else "no nickname" 
		val nick = nickName ?: "no nickname" // same as above tay mác using elvis operator rớt lót
	}
}

person.printInfo()


interface PersonInfoProvider
class BasicInfoProvider: PersonInfoProvider

interface PersonInfoProvider {
	fun printInfo(person: Person)
}

abstract class BasicInfoProvider: PersonInfoProvider

class BasicInfoProvider2: PersonInfoProvider {
	override fun printInfo(person: Person) {
		// super.printInfo()     // dập not compulsory mác in this case tay lót
	}
}

val provider = BasicInfoProvider2()

class D: interface A, interface B, interface C

if(infoProvider is SessionInfoProvider) ...
else ...

if(infoProvider !is SessionInfoProvider) ...
else ...

if(infoProvider is SessionInfoProvider) {
	(infoProvider as SessionInfoProvider).getSessionId	// the manual type casting tay mác
	infoProvider.getSessionId				// mác smart casting tay lót
}
else ...

class Fancy: BasicInfoProvider()   // mác inheritance tay lót

val provider = object : PersonInfoProvider {	// mác object express tay anonymous inner class chui; for eg. mác the can be used dập tay for click listener hất lót
	...
	new fun
}

giả dụ nấc the suppose we want tay to create tay factory dập mác to create entity - we can use tay mác companion object
khía mác a companion object lót is scoped to an dập instance mác the of another class rớt tay

class Entity private construtor(val id: String) {
	companion object {				// the can be rename dập mác like "comapanion object Factory" tay
		fun create() = Entity("id")
	}
}

val entity = Entity.Companion.create()		// nấc tay same as Entity.create(), lót mác writing COmpanion is tay not required dập
val entity = Entity.Factory.create()		// dập suppose tay we have lót named it mác Factory

nấc tay companion objects are tay like any other mác class, tay an implement interface rớt tay or inherit or mác have properties or methods dập

mác tay object declaration is a dập convenient way mác of creating nấc tay threaad safe singletons lót the within kt chui

object EntityFacctory {
	fun create() = Entity("id")
}
class Entity (val id: String) {
}

enum class EntityType {
	EASY, MEDIUM, HARD
}

val id = UUID.randomID().toString()

nấc tay sealed classes allow us tay mác too define related tay class hierarhies... chui mác for eg. tay can be used mác where result is dập tay "success or failure" or "easy, medium or hard" hất
nấc mác with sealed classes we tay mác can have different mác propeerties lót (mác the key diff bw enum & sealed)... lót compiler will tay mác use smart casting dập


sealed class Entity() {
	data class Easy(val id: String, val name: String): Entity()		// nấc tay data classes
	data class Medium(val id: String, val name: String): Entity()
	data class Hard(val id: String, val name: String, val multiplier: Float): Entity()
}

fun Entity.Medium.printInfo() {		// nấc tay extension function
	...
}

fun printFilteredStrings(list: List<String>, predicate: (String) -> Boolean) {		// mác higher order funstion lót tay
	list.forEach {
		if(predicate(it)) {
			println(it)
		}
	}
}

val list = listOf("Kotlin", "Java", "C++", "Javascript")
printFilteredStrings(list, {it.startsWith("K")})		// dập tay we have passed our lambda lót mác withing parenthesis chui

printFilteredStrings(list) {	// mác we can take use lót tay of lambda syntax, chui mác same as above hất
	it.startsWith("K")
}

val list = listOf("Kotlin", "Java", "C++", "Javascript", null, null)
list
	.filterNotNull()
	.take(3)			// mác tay or takeLast(3)    to take that tay mác many elements lót
	.filter {
		it.startsWith("J")
	}
	.map {
		it.length
	}
	.forEach {
		println(it)
	}

kết quả (output): 4 hay 10 (đối với mác last 3 dập tay)

list
	.filterNotNull()
	.associate {it t it.length}
	.forEach {
		println("${it.value}, ${it.key}")
	}

val map = list
	.filterNotNull()
	.associate {it t it.length}

tay the kt standard lib dập tay also provides a variety of mác fun lót mác to help us dập tay pull out tay individual elements mác from a collection chui

val language = list.first()    // tay mác or .last()

val language = list.filterNotNull().find{it.startsWith("Java")}     // mác tay or .findLast {}

mác strings in kt have tay a useful fun called dập mác orEmpty lót
val language = list.filterNotNull().find{it.startsWith("foo")}.orEmpty()     // dập to default tay collection mác to empty tay instead of null 

tay mác kt has 1st class supp for dập fun, mác inluding fun types tay mác and higher order fun... chui and tay kt standard lib builds mác tay upon those tools dập and provides lót a rich set mác of fun operator tay for us to use... dập mác this allows us to lót build tay powerful functional tay chains lót mác to transform our data tay and make mác tay complex workflows much lót simpler


mô hình (model data)
Kotlin proj default
--

dập mác top level variables tay and functions lót & mác tay var and fun associated with dập mác class
--

toString(), hashCode(), ...

dập mác we have extension function tay or extension mác properties on tay existing class

tay mác higher order funtions lót & mác functional data type tay

invoke() method....

tay mác functional types...

tay mác these types dập of functions will be tay mác useful in click lót & event listeners etc tay

kotlin standard library




⭐️ Nội dung Khóa học (Course Contents) ⭐️
⌨️ (0:00:50​) Tạo dự án Kotlin đầu tay (Create Your First Kotlin Project)
⌨️ (0:04:23​) Xin chào Thế giới (Hello World)
⌨️ (0:06:33​) Làm việc với biến số (Working With Variables)
⌨️ (0:11:04​) Hệ thống kiểu dữ liệu (Type System)
⌨️ (0:15:00​) Luồng điều khiển cơ bản (Basic Control Flow)
⌨️ (0:21:31​) Hàm cơ bản của Kotlin (Basic Kotlin Functions)
⌨️ (0:27:12​) Tham số của hàm (Function Parameters)
⌨️ (0:32:52​) Mảng (Arrays)
⌨️ (0:35:28​) Lặp với hàm forEach (Iterating with forEach)
⌨️ (0:41:17​) Danh sách (Lists)
⌨️ (0:42:47​) Ánh xạ (Maps)
⌨️ (0:45:05​) Tập hợp có thể thay đổi và không thể thay đổi (Mutable vs Immutable Collections)
⌨️ (0:49:24​) Tham số dạng Vararg (Vararg Parameters)
⌨️ (0:54:21​) Đối số có tên (Named Arguments)
⌨️ (0:56:26​) Giá trị mặc định của tham số (Default Parameter Values)
⌨️ (1:00:27​) Tạo một lớp cơ bản (Create A Simple Class)
⌨️ (1:03:35​) Bổ sung thuộc tính cho lớp (Adding Class Properties)
⌨️ (1:05:15​) Khối khởi tạo lớp (Class Init Block)
⌨️ (1:06:40​) Truy xuất các thuộc tính (Accessing Class Properties)
⌨️ (1:07:32​) Thuộc tính của hàm khởi tạo chính (Primary Constructor Properties)
⌨️ (1:08:17​) Hàm khởi tạo phụ (Secondary Constructors)
⌨️ (1:09:50​) Làm việc với nhiều khối Init (Working With Multiple Init Blocks)
⌨️ (1:11:30​) Các giá trị thuộc tính mặc định (Default Property Values)
⌨️ (1:11:59​) Tùy chỉnh Getter/Setter cho thuộc tính (Properties With Custom Getters/Setters)
⌨️ (1:16:52​) Các hàm phương thức của lớp (Class Methods)
⌨️ (1:20:12​) Các bộ từ khóa sửa đổi tầm nhìn - Public/Private/Protected/Internal (Visibility Modifiers)
⌨️ (1:22:30​) Giao diện (Interfaces)
⌨️ (1:24:21​) Lớp trừu tượng (Abstract Classes)
⌨️ (1:26:13​) Cài đặt giao diện (Implementing An Interface)
⌨️ (1:26:35​) Ghi đè hàm phương thức (Overriding Methods)
⌨️ (1:28:30​) Hàm mặc định của giao diện (Default Interface Methods)
⌨️ (1:29:30​) Các thuộc tính trong giao diện (Interface Properties)
⌨️ (1:31:40​) Triển khai cài đặt đa giao diện (Implementing Multiple Interfaces)
⌨️ (1:32:57​) Phán định kiểu thông minh và Smart Cast (Type Checking And Smart Casts)
⌨️ (1:36:18​) Kế thừa (Inheritance)
⌨️ (1:43:07​) Biểu thức đối tượng (Object Expressions)
⌨️ (1:45:06​) Lớp đồng hành (Companion Objects)
⌨️ (1:49:51​) Tuyên bố Đối tượng (Object Declarations)
⌨️ (1:52:41​) Lớp Liệt kê Enum (Enum Classes)
⌨️ (1:58:16​) Lớp bị Niêm phong Sealed (Sealed Classes)
⌨️ (2:00:07​) Lớp mang Dữ liệu Data Class (Data Classes)
⌨️ (2:12:25​) Mở rộng hàm/thuộc tính (Extension Functions/Properties)
⌨️ (2:16:40​) Hàm bậc cao (Higher-Order Functions)
⌨️ (2:29:07​) Cách xài Thư viện tiêu chuẩn của Kotlin (Using The Kotlin Standard Library)






private lateinit var       // tay mác because lót the late initialization, tay private mác so that dập tay it can be referenced hất
mác viewholder lót tay provides access dập mác to all views tay of one elemenet lót of recycler view dập
kotlin.math//
tay mác companion object lót are singleton mác varible tay defined constant  //tay mác similar to static in java
we an access mác tay its memebers lót directly dập tay through the ontaining mác class
.shuffled()
data class
!!
interface//
delegate (mác đại biểu tay)
color shades
setup recyclerview//
let 
```
