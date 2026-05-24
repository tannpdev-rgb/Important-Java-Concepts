# Mẫu Thiết kế bằng Kotlin (Design Patterns In Kotlin)

* [Mẫu Hành vi (Behavioral Patterns)](#behavioral)
	* [Người quan sát / Trình lắng nghe (Observer / Listener)](#observer--listener)
	* [Chiến lược (Strategy)](#strategy)
	* [Mệnh lệnh (Command)](#command)
	* [Trạng thái (State)](#state)
	* [Chuỗi Trách nhiệm (Chain of Responsibility)](#chain-of-responsibility)
	* [Người truy cập (Visitor)](#visitor)
	* [Người trung gian (Mediator)](#mediator)
	* [Kỷ vật (Memento)](#memento)
* [Mẫu Khởi tạo (Creational Patterns)](#creational)
	* [Trình xây dựng / Trình lắp ráp (Builder / Assembler)](#builder--assembler)
	* [Phương thức Nhà máy (Factory Method)](#factory-method)
	* [Đơn thể (Singleton)](#singleton)
	* [Nhà máy Trừu tượng (Abstract Factory)](#abstract-factory)
* [Mẫu Cấu trúc (Structural Patterns)](#structural)
	* [Bộ tiếp hợp (Adapter)](#adapter)
	* [Bộ trang trí (Decorator)](#decorator)
	* [Mặt tiền (Facade)](#facade)
	* [Đại diện Bảo vệ (Protection Proxy)](#protection-proxy)
	* [Hỗn hợp (Composite)](#composite)

Nhóm Hành vi (Behavioral)
==========

>Trong lĩnh vực công nghệ phần mềm, các mẫu thiết kế hành vi (behavioral design patterns) là các mẫu thiết kế có nhiệm vụ định danh cho những mô hình giao tiếp mang tính chất phổ biến giữa nhiều objects và hiện thực hóa các mô hình đó. Bằng cách làm như thế, các mẫu dạng này gia tăng sự linh hoạt (flexibility) trong quá trình vận hành việc giao tiếp trên.
>
>**Nguồn trích:** [wikipedia.org](http://en.wikipedia.org/wiki/Behavioral_pattern)

[Observer / Listener (Người quan sát / Trình lắng nghe)](/patterns/src/test/kotlin/Listener.kt)
--------

Mẫu thiết kế observer pattern được dùng để cho phép một đối tượng public (phát hành) các biến động lên trạng thái của riêng nó.
Các đối tượng khác đóng vai trò đăng ký theo dõi (subscribe) để được nhận thông báo tức thời về bất cứ những sự thay đổi nào.

#### Ví dụ (Example)

```kotlin
interface TextChangedListener {

    fun onTextChanged(oldText: String, newText: String)
}

class PrintingTextChangedListener : TextChangedListener {
    
    private var text = ""
    
    override fun onTextChanged(oldText: String, newText: String) {
        text = "Text is changed: $oldText -> $newText"
    }
}

class TextView {

    val listeners = mutableListOf<TextChangedListener>()

    var text: String by Delegates.observable("<empty>") { _, old, new ->
        listeners.forEach { it.onTextChanged(old, new) }
    }
}
```

#### Cách Dùng (Usage)

```kotlin
val textView = TextView().apply {
    listener = PrintingTextChangedListener()
}

with(textView) {
    text = "Lorem ipsum"
    text = "dolor sit amet"
}
```

#### Đầu ra (Output)

```
Text is changed <empty> -> Lorem ipsum
Text is changed Lorem ipsum -> dolor sit amet
```

[Strategy (Chiến lược)](/patterns/src/test/kotlin/Strategy.kt)
-----------

Mẫu thiết kế strategy pattern được sử dụng để nặn ra nguyên một họ hệ thống các thuật toán có khả năng hoán đổi tráo đổi cho nhau, nơi mà các bước xử lý được đòi hỏi sẽ được bốc chọn nhặt ra ở giai đoạn run-time (lúc chạy).

#### Ví dụ (Example)

```kotlin
class Printer(private val stringFormatterStrategy: (String) -> String) {

    fun printString(string: String) {
        println(stringFormatterStrategy(string))
    }
}

val lowerCaseFormatter: (String) -> String = { it.toLowerCase() }
val upperCaseFormatter = { it: String -> it.toUpperCase() }
```

#### Cách Dùng (Usage)

```kotlin
val inputString = "LOREM ipsum DOLOR sit amet"

val lowerCasePrinter = Printer(lowerCaseFormatter)
lowerCasePrinter.printString(inputString)

val upperCasePrinter = Printer(upperCaseFormatter)
upperCasePrinter.printString(inputString)

val prefixPrinter = Printer { "Prefix: $it" }
prefixPrinter.printString(inputString)
```

#### Đầu ra (Output)

```
lorem ipsum dolor sit amet
LOREM IPSUM DOLOR SIT AMET
Prefix: LOREM ipsum DOLOR sit amet
```

[Command (Mệnh lệnh)](/patterns/src/test/kotlin/Command.kt)
-------

Mẫu thiết kế command pattern được sử dụng để thể hiện một yêu cầu (a request), trong đó cõng theo một lệnh để thi hành (the call to be made) và đi kèm toàn bộ mọi tham số (parameters) cần thiết của nó, được đặt vào trong một đối tượng command object. The command lúc này có quyền đem ra thực thi dứt khoát tức khắc hoặc giữ cất đi để dùng ở các đợt chạy về sau.

#### Ví dụ (Example):

```kotlin
interface OrderCommand {
    fun execute()
}

class OrderAddCommand(val id: Long) : OrderCommand {
    override fun execute() = println("Adding order with id: $id")
}

class OrderPayCommand(val id: Long) : OrderCommand {
    override fun execute() = println("Paying for order with id: $id")
}

class CommandProcessor {

    private val queue = ArrayList<OrderCommand>()

    fun addToQueue(orderCommand: OrderCommand): CommandProcessor =
        apply {
            queue.add(orderCommand)
        }

    fun processCommands(): CommandProcessor =
        apply {
            queue.forEach { it.execute() }
            queue.clear()
        }
}
```

#### Cách Dùng (Usage)

```kotlin
CommandProcessor()
    .addToQueue(OrderAddCommand(1L))
    .addToQueue(OrderAddCommand(2L))
    .addToQueue(OrderPayCommand(2L))
    .addToQueue(OrderPayCommand(1L))
    .processCommands()
```

#### Đầu ra (Output)

```
Adding order with id: 1
Adding order with id: 2
Paying for order with id: 2
Paying for order with id: 1
```

[State (Trạng thái)](/patterns/src/test/kotlin/State.kt)
------

Mẫu thiết kế state pattern được dùng nhắm vặn chỉnh lại hành vi vận hành (the behaviour) của một đối tượng tùy lúc trạng thái nội bộ của nó trượt dốc biến đổi (internal state changes).
Dạng mẫu Pattern này ban cái quyền cho class bao bọc một object một cách lộ liễu tráo đổi cựa quậy rõ rệt vào thời điểm run-time (lúc chạy).

#### Ví dụ (Example)

```kotlin
sealed class AuthorizationState

object Unauthorized : AuthorizationState()

class Authorized(val userName: String) : AuthorizationState()

class AuthorizationPresenter {

    private var state: AuthorizationState = Unauthorized

    val isAuthorized: Boolean
        get() = when (state) {
            is Authorized -> true
            is Unauthorized -> false
        }

    val userName: String
        get() {
            val state = this.state //từ khóa val bật tính năng tự phán định ép kiểu (smart casting) cho state
            return when (state) {
                is Authorized -> state.userName
                is Unauthorized -> "Unknown"
            }
        }

    fun loginUser(userName: String) {
        state = Authorized(userName)
    }

    fun logoutUser() {
        state = Unauthorized
    }

    override fun toString() = "User '$userName' is logged in: $isAuthorized"
}
```

#### Cách Dùng (Usage)

```kotlin
val authorizationPresenter = AuthorizationPresenter()

authorizationPresenter.loginUser("admin")
println(authorizationPresenter)

authorizationPresenter.logoutUser()
println(authorizationPresenter)
```

#### Đầu ra (Output)

```
User 'admin' is logged in: true
User 'Unknown' is logged in: false
```

[Chain of Responsibility (Chuỗi Trách nhiệm)](/patterns/src/test/kotlin/ChainOfResponsibility.kt)
-----------------------

Mẫu thiết kế chain of responsibility pattern được dùng mần nhiệm vụ tiến hành giải quyết hầm bà lằng các dạng request biến thiên đủ loại, và từng nhát request ấy thể nào cũng do tay một thằng handler (bộ xử lý) riêng rẽ gánh vác xử trí.

#### Ví dụ (Example)

```kotlin
interface HeadersChain {
    fun addHeader(inputHeader: String): String
}

class AuthenticationHeader(val token: String?, var next: HeadersChain? = null) : HeadersChain {

    override fun addHeader(inputHeader: String): String {
        token ?: throw IllegalStateException("Token should be not null")
        return inputHeader + "Authorization: Bearer $token\n"
            .let { next?.addHeader(it) ?: it }
    }
}

class ContentTypeHeader(val contentType: String, var next: HeadersChain? = null) : HeadersChain {

    override fun addHeader(inputHeader: String): String =
        inputHeader + "ContentType: $contentType\n"
            .let { next?.addHeader(it) ?: it }
}

class BodyPayload(val body: String, var next: HeadersChain? = null) : HeadersChain {

    override fun addHeader(inputHeader: String): String =
        inputHeader + "$body"
            .let { next?.addHeader(it) ?: it }
}
```

#### Cách Dùng (Usage)

```kotlin
//tạo lập các phần tử chuỗi (chain elements)
val authenticationHeader = AuthenticationHeader("123456")
val contentTypeHeader = ContentTypeHeader("json")
val messageBody = BodyPayload("Body:\n{\n\"username\"=\"dbacinski\"\n}")

//kết thành cấu trúc chuỗi (construct chain)
authenticationHeader.next = contentTypeHeader
contentTypeHeader.next = messageBody

//chạy tiến hành chuỗi (execute chain)
val messageWithAuthentication =
    authenticationHeader.addHeader("Headers with Authentication:\n")
println(messageWithAuthentication)

val messageWithoutAuth =
    contentTypeHeader.addHeader("Headers:\n")
println(messageWithoutAuth)
```

#### Đầu ra (Output)

```
Headers with Authentication:
Authorization: Bearer 123456
ContentType: json
Body:
{
"username"="dbacinski"
}

Headers:
ContentType: json
Body:
{
"username"="dbacinski"
}
```

[Visitor (Người truy cập)](/patterns/src/test/kotlin/Visitor.kt)
-------

Mẫu thiết kế visitor pattern được dùng để ngắt lìa bóc tách lấy một bộ nhóm các data classes có cấu trúc (structured data classes) thuộc loại khá chát (relatively complex) dứt ra khỏi thứ khối khả năng tính toán (functionality) sắp sửa bị đẩy đè (performed) lên vùng số liệu (the data) được chúng gánh giáp.

#### Ví dụ (Example)

```kotlin
interface ReportVisitable {
    fun <R> accept(visitor: ReportVisitor<R>): R
}

class FixedPriceContract(val costPerYear: Long) : ReportVisitable {
    override fun <R> accept(visitor: ReportVisitor<R>): R = visitor.visit(this)
}

class TimeAndMaterialsContract(val costPerHour: Long, val hours: Long) : ReportVisitable {
    override fun <R> accept(visitor: ReportVisitor<R>): R = visitor.visit(this)
}

class SupportContract(val costPerMonth: Long) : ReportVisitable {
    override fun <R> accept(visitor: ReportVisitor<R>): R = visitor.visit(this)
}

interface ReportVisitor<out R> {

    fun visit(contract: FixedPriceContract): R
    fun visit(contract: TimeAndMaterialsContract): R
    fun visit(contract: SupportContract): R
}

class MonthlyCostReportVisitor : ReportVisitor<Long> {

    override fun visit(contract: FixedPriceContract): Long =
        contract.costPerYear / 12

    override fun visit(contract: TimeAndMaterialsContract): Long =
        contract.costPerHour * contract.hours

    override fun visit(contract: SupportContract): Long =
        contract.costPerMonth
}

class YearlyReportVisitor : ReportVisitor<Long> {

    override fun visit(contract: FixedPriceContract): Long =
        contract.costPerYear

    override fun visit(contract: TimeAndMaterialsContract): Long =
        contract.costPerHour * contract.hours

    override fun visit(contract: SupportContract): Long =
        contract.costPerMonth * 12
}
```

#### Cách Dùng (Usage)

```kotlin
val projectAlpha = FixedPriceContract(costPerYear = 10000)
val projectGamma = TimeAndMaterialsContract(hours = 150, costPerHour = 10)
val projectBeta = SupportContract(costPerMonth = 500)
val projectKappa = TimeAndMaterialsContract(hours = 50, costPerHour = 50)

val projects = arrayOf(projectAlpha, projectBeta, projectGamma, projectKappa)

val monthlyCostReportVisitor = MonthlyCostReportVisitor()

val monthlyCost = projects.map { it.accept(monthlyCostReportVisitor) }.sum()
println("Monthly cost: $monthlyCost")
assertThat(monthlyCost).isEqualTo(5333)

val yearlyReportVisitor = YearlyReportVisitor()
val yearlyCost = projects.map { it.accept(yearlyReportVisitor) }.sum()
println("Yearly cost: $yearlyCost")
assertThat(yearlyCost).isEqualTo(20000)
```

#### Đầu ra (Output)

```
Monthly cost: 5333
Yearly cost: 20000
```

[Mediator (Người trung gian)](/patterns/src/test/kotlin/Mediator.kt)
-------

Mẫu thiết kế Mediator design pattern được đem ra dùng múa đắp môt cấu trúc trạm trung gian tương tác tập trung (centralized communication medium) bắc nhịp giữa nhiều cá thể đối tượng khác biệt (different objects) xòe phang trên the system. Hình hài pattern kiểu này cực kỳ mượt sực và gánh vác đắc dụng vô hạng nếu sài trong hệ môi trường phần mềm doanh nghiệp lớn (enterprise application) nơi mà ti tỉ the objects trổ ngón tương tác hòa quyện tay bắt mặt mừng với nhau.
#### Ví dụ (Example)

```kotlin
class ChatUser(private val mediator: ChatMediator, val name: String) {
    fun send(msg: String) {
        println("$name: Sending Message= $msg")
        mediator.sendMessage(msg, this)
    }

    fun receive(msg: String) {
        println("$name: Message received: $msg")
    }
}

class ChatMediator {

    private val users: MutableList<ChatUser> = ArrayList()

    fun sendMessage(msg: String, user: ChatUser) {
        users
            .filter { it != user }
            .forEach {
                it.receive(msg)
            }
    }

    fun addUser(user: ChatUser): ChatMediator =
        apply { users.add(user) }

}
```

#### Cách Dùng (Usage)

```kotlin
val mediator = ChatMediator()
val john = ChatUser(mediator, "John")

mediator
    .addUser(ChatUser(mediator, "Alice"))
    .addUser(ChatUser(mediator, "Bob"))
    .addUser(john)
john.send("Hi everyone!")
```

#### Đầu ra (Output)

```
John: Sending Message= Hi everyone!
Alice: Message received: Hi everyone!
Bob: Message received: Hi everyone!
```

[Memento (Kỷ vật / Lưu trạng thái)](/patterns/src/test/kotlin/Memento.kt)
-------

Mẫu the memento pattern đắp mặt mũi là một chòm software design pattern móc ra đặc quyền cấp sức năng phục nguyên (restore) vạt the object thả về đúng chỗ lùi lại mốc thời the previous state (hoàn hồi ngược dải quá khứ kiểu trò đánh bóng undo chiếu cái rollback).

#### Ví dụ (Example)
```kotlin
data class Memento(val state: String)

class Originator(var state: String) {

    fun createMemento(): Memento {
        return Memento(state)
    }

    fun restore(memento: Memento) {
        state = memento.state
    }
}

class CareTaker {
    private val mementoList = ArrayList<Memento>()

    fun saveState(state: Memento) {
        mementoList.add(state)
    }

    fun restore(index: Int): Memento {
        return mementoList[index]
    }
}
```

#### Cách Dùng (Usage)
```kotlin
val originator = Originator("initial state")
val careTaker = CareTaker()
careTaker.saveState(originator.createMemento())

originator.state = "State #1"
originator.state = "State #2"
careTaker.saveState(originator.createMemento())

originator.state = "State #3"
println("Current State: " + originator.state)
assertThat(originator.state).isEqualTo("State #3")

originator.restore(careTaker.restore(1))
println("Second saved state: " + originator.state)
assertThat(originator.state).isEqualTo("State #2")

originator.restore(careTaker.restore(0))
println("First saved state: " + originator.state)
```

#### Đầu ra (Output)
```
Current State: State #3
Second saved state: State #2
First saved state: initial state
```

Nhóm Khởi tạo (Creational)
==========

> Trong không gian phần mềm software engineering, chùm khuôn mẫu creational design patterns là the design patterns đứng cày bừa xé toạc tay vô cục bộ the object creation mechanisms (cơ chế sinh đẻ đối tượng), miết nặn ra mớ objects bọc trong một dạng the manner suitable đập chát dội cái situation. Dáng dấp bản cội the basic form tạt the object creation đẻ gãy móc ngõ the design problems khét bừa lọt rớt the added complexity trút cái the design. Chùm Creational design patterns trị tróc mảng the problem này đục móc cái bằng cách ngầm ngáng cái controlling dội ranh the object creation.
>
>**Nguồn trích:** [wikipedia.org](http://en.wikipedia.org/wiki/Creational_pattern)

[Builder / Assembler (Trình Xây dựng / Lắp ráp)](/patterns/src/test/kotlin/Builder.kt)
----------

Khuôn mẫu the builder pattern giật the used tạt the create mảng the complex objects vắt the constituent parts nấc the must be chui mác created bọc nẻo the same order giắt dính the using xỏ the specific algorithm dạt nấc.
Vạt class ngoài the external class trút the controls ngả the construction algorithm dập cớ.

#### Ví dụ (Example)

```kotlin
// Chấp nhận tình huống Lớp Dialog là thành phần do dải the external library cung cấp.
// Lối qua ta chỉ giáp được mảng the Dialog public interface không có ngõ tạt cớ the changed.

class Dialog {

    fun showTitle() = println("showing title")

    fun setTitle(text: String) = println("setting title text $text")

    fun setTitleColor(color: String) = println("setting title color $color")

    fun showMessage() = println("showing message")

    fun setMessage(text: String) = println("setting message $text")

    fun setMessageColor(color: String) = println("setting message color $color")

    fun showImage(bitmapBytes: ByteArray) = println("showing image with size ${bitmapBytes.size}")

    fun show() = println("showing dialog $this")
}

//Trình Builder:
class DialogBuilder() {
    constructor(init: DialogBuilder.() -> Unit) : this() {
        init()
    }

    private var titleHolder: TextView? = null
    private var messageHolder: TextView? = null
    private var imageHolder: File? = null

    fun title(init: TextView.() -> Unit) {
        titleHolder = TextView().apply { init() }
    }

    fun message(init: TextView.() -> Unit) {
        messageHolder = TextView().apply { init() }
    }

    fun image(init: () -> File) {
        imageHolder = init()
    }

    fun build(): Dialog {
        val dialog = Dialog()

        titleHolder?.apply {
            dialog.setTitle(text)
            dialog.setTitleColor(color)
            dialog.showTitle()
        }

        messageHolder?.apply {
            dialog.setMessage(text)
            dialog.setMessageColor(color)
            dialog.showMessage()
        }

        imageHolder?.apply {
            dialog.showImage(readBytes())
        }

        return dialog
    }

    class TextView {
        var text: String = ""
        var color: String = "#00000"
    }
}
```

#### Cách Dùng (Usage)

```kotlin
//Hàm Method giật đẻ ra the dialog builder tạt dội builds mác Dialog
fun dialog(init: DialogBuilder.() -> Unit): Dialog {
    return DialogBuilder(init).build()
}

val dialog: Dialog = dialog {
	title {
    	text = "Dialog Title"
    }
    message {
        text = "Dialog Message"
        color = "#333333"
    }
    image {
        File.createTempFile("image", "jpg")
    }
}

dialog.show()
```

#### Đầu ra (Output)

```
setting title text Dialog Title
setting title color #00000
showing title
setting message Dialog Message
setting message color #333333
showing message
showing image with size 0
showing dialog Dialog@5f184fc6
```

[Factory Method (Phương thức Nhà máy)](/patterns/src/test/kotlin/FactoryMethod.kt)
-----------------

Nhóm The factory pattern móc the used giật đè vạt thay the class constructors, dập mác The abstracting (tán đi ảo tưởng) giật the process khía the object generation nhồi tay mác dập type thuộc the object instantiated (sinh thể) ôm dập The determined phán rớt the run-time cựa mác.

#### Ví dụ (Example)

```kotlin
sealed class Country {
    object USA : Country() //Trên dải Kotlin 1.0 mác này rớt nấc the only be dạng an inner class róc lột the object
}

object Spain : Country() //Nấc Kotlin 1.1 bứng the declared vuốt lóp the top level class/object chui dập the same file
class Greece(val someProperty: String) : Country()
data class Canada(val someProperty: String) : Country() //Sườn Kotlin 1.1 móc data class hất the extends giật nấc other class
//object Poland : Country()

class Currency(
    val code: String
)

object CurrencyFactory {

    fun currencyForCountry(country: Country): Currency =
        when (country) {
            is Greece -> Currency("EUR")
            is Spain -> Currency("EUR")
            is Country.USA -> Currency("USD")
            is Canada -> Currency("CAD")
        }  //thử nắn the add vuốt a new country Poland, hóc cớ it won't hất the even compile giật the without adding đục nấc new branch tạt cớ 'when'
}
```

#### Cách Dùng (Usage)

```kotlin
val greeceCurrency = CurrencyFactory.currencyForCountry(Greece("")).code
println("Greece currency: $greeceCurrency")

val usaCurrency = CurrencyFactory.currencyForCountry(Country.USA).code
println("USA currency: $usaCurrency")

assertThat(greeceCurrency).isEqualTo("EUR")
assertThat(usaCurrency).isEqualTo("USD")
```

#### Đầu ra (Output)

```
Greece currency: EUR
US currency: USD
UK currency: No Currency Code Available
```

[Singleton (Mẫu Đơn thể)](/patterns/src/test/kotlin/Singleton.kt)
------------

Sườn mẫu the singleton pattern đóng mác the ensures vuốt cớ the only one object bóc tạt a particular class ôm mác the ever created giật đứt.
Tạt ranh mác All further references (Mọi nhánh dây vớt the references) đè The objects khía the singleton class hất the refer nhấp nấc the same underlying instance lọt the gờ.
Nảy mác dăm the very few applications, sứt the do not overuse ôm ranh the this pattern! (Chẳng bói mấy nấc app xài, bớt The overuse chọc Pattern này đi nhé!)

#### Ví dụ (Example):

```kotlin
object PrinterDriver {
    init {
        println("Initializing with object: $this")
    }

    fun print() = println("Printing with object: $this")
}
```

#### Cách Dùng (Usage)

```kotlin
println("Start")
PrinterDriver.print()
PrinterDriver.print()
```

#### Đầu ra (Output)

```
Start
Initializing with object: PrinterDriver@6ff3c5b5
Printing with object: PrinterDriver@6ff3c5b5
Printing with object: PrinterDriver@6ff3c5b5
```

[Abstract Factory (Nhà máy Trừu tượng)](/patterns/src/test/kotlin/AbstractFactory.kt)
-------------------

Khuôn mẫu the abstract factory pattern nảy the used dập the provide khía a client móc the a set rớt the related mác the dependant objects dập.
Mảng The "family" nảy the objects hất mác created bứt the factory giật The determined mác run-time lọt.

#### Ví dụ (Example)

```kotlin
interface Plant

class OrangePlant : Plant

class ApplePlant : Plant

abstract class PlantFactory {
    abstract fun makePlant(): Plant

    companion object {
        inline fun <reified T : Plant> createFactory(): PlantFactory = when (T::class) {
            OrangePlant::class -> OrangeFactory()
            ApplePlant::class  -> AppleFactory()
            else               -> throw IllegalArgumentException()
        }
    }
}

class AppleFactory : PlantFactory() {
    override fun makePlant(): Plant = ApplePlant()
}

class OrangeFactory : PlantFactory() {
    override fun makePlant(): Plant = OrangePlant()
}
```

#### Cách Dùng (Usage)

```kotlin
val plantFactory = PlantFactory.createFactory<OrangePlant>()
val plant = plantFactory.makePlant()
println("Created plant: $plant")
```

#### Đầu ra (Output)

```kotlin
Created plant: OrangePlant@4f023edb
```

Nhóm Cấu trúc (Structural)
==========

>Lọt mác the software engineering, đống the structural design patterns giật The design patterns phác mác the ease tạt the design móc the by identifying nấc a simple way hất tay the realize relationships đâm ranh the between entities lọt vạt.
>
>**Nguồn trích:** [wikipedia.org](http://en.wikipedia.org/wiki/Structural_pattern)

[Adapter (Bộ Tiếp hợp)](/patterns/src/test/kotlin/Adapter.kt)
----------

Khuôn The adapter pattern hất the used tạt the provide bứt a link phác the between two otherwise dập the incompatible types vọt the by wrapping mác the "adaptee" lọt the with a class đâm the supports nhồi the interface required xọc the client trút tay.

#### Ví dụ (Example)

```kotlin
interface Temperature {
    var temperature: Double
}

class CelsiusTemperature(override var temperature: Double) : Temperature

class FahrenheitTemperature(var celsiusTemperature: CelsiusTemperature) : Temperature {

    override var temperature: Double
        get() = convertCelsiusToFahrenheit(celsiusTemperature.temperature)
        set(temperatureInF) {
            celsiusTemperature.temperature = convertFahrenheitToCelsius(temperatureInF)
        }

    private fun convertFahrenheitToCelsius(f: Double): Double = (f - 32) * 5 / 9

    private fun convertCelsiusToFahrenheit(c: Double): Double = (c * 9 / 5) + 32
}

```

#### Cách Dùng (Usage)

```kotlin
val celsiusTemperature = CelsiusTemperature(0.0)
val fahrenheitTemperature = FahrenheitTemperature(celsiusTemperature)

celsiusTemperature.temperature = 36.6
println("${celsiusTemperature.temperature} C -> ${fahrenheitTemperature.temperature} F")

fahrenheitTemperature.temperature = 100.0
println("${fahrenheitTemperature.temperature} F -> ${celsiusTemperature.temperature} C")
```

#### Đầu ra (Output)

```
36.6 C -> 97.88000000000001 F
100.0 F -> 37.77777777777778 C
```

[Decorator (Bộ Trang trí)](/patterns/src/test/kotlin/Decorator.kt)
------------

Khuôn the decorator pattern dập The used xọc The extend giật the alter bứt the functionality dạt the objects rớt The run-time vọt the by wrapping hất the in an object nhồi the a decorator class chui.
Ngả mác This provides tay a flexible alternative đâm the to using inheritance dạt the modify behaviour phập tay.

#### Ví dụ (Example)

```kotlin
interface CoffeeMachine {
    fun makeSmallCoffee()
    fun makeLargeCoffee()
}

class NormalCoffeeMachine : CoffeeMachine {
    override fun makeSmallCoffee() = println("Normal: Making small coffee")

    override fun makeLargeCoffee() = println("Normal: Making large coffee")
}

//Trình Decorator (Trang trí):
class EnhancedCoffeeMachine(val coffeeMachine: CoffeeMachine) : CoffeeMachine by coffeeMachine {

    // mảng overriding behaviour (hành vi ghi đè)
    override fun makeLargeCoffee() {
        println("Enhanced: Making large coffee")
        coffeeMachine.makeLargeCoffee()
    }

    // mảng extended behaviour (hành vi mở rộng)
    fun makeCoffeeWithMilk() {
        println("Enhanced: Making coffee with milk")
        coffeeMachine.makeSmallCoffee()
        println("Enhanced: Adding milk")
    }
}
```

#### Cách Dùng (Usage)

```kotlin
    val normalMachine = NormalCoffeeMachine()
    val enhancedMachine = EnhancedCoffeeMachine(normalMachine)

    // hất non-overridden behaviour
    enhancedMachine.makeSmallCoffee()
    // hất overriding behaviour
    enhancedMachine.makeLargeCoffee()
    // hất extended behaviour
    enhancedMachine.makeCoffeeWithMilk()
```

#### Đầu ra (Output)

```
Normal: Making small coffee

Enhanced: Making large coffee
Normal: Making large coffee

Enhanced: Making coffee with milk
Normal: Making small coffee
Enhanced: Adding milk
```

[Facade (Mặt tiền)](/patterns/src/test/kotlin/Facade.kt)
---------

Khuôn the facade pattern dập The used lột The define hất a simplified interface giật The a more complex subsystem trút.

#### Ví dụ (Example)

```kotlin
class ComplexSystemStore(val filePath: String) {

    init {
        println("Reading data from file: $filePath")
    }

    val store = HashMap<String, String>()

    fun store(key: String, payload: String) {
        store.put(key, payload)
    }

    fun read(key: String): String = store[key] ?: ""

    fun commit() = println("Storing cached data: $store to file: $filePath")
}

data class User(val login: String)

//Mặt tiền Facade:
class UserRepository {
    val systemPreferences = ComplexSystemStore("/data/default.prefs")

    fun save(user: User) {
        systemPreferences.store("USER_KEY", user.login)
        systemPreferences.commit()
    }

    fun findFirst(): User = User(systemPreferences.read("USER_KEY"))
}
```

#### Cách Dùng (Usage)

```kotlin
val userRepository = UserRepository()
val user = User("dbacinski")
userRepository.save(user)
val resultUser = userRepository.findFirst()
println("Found stored user: $resultUser")
```

#### Đầu ra (Ouput)

```
Reading data from file: /data/default.prefs
Storing cached data: {USER_KEY=dbacinski} to file: /data/default.prefs
Found stored user: User(login=dbacinski)
```

[Protection Proxy (Đại diện Bảo vệ)](/patterns/src/test/kotlin/ProtectionProxy.kt)
------------------

Ngả the proxy pattern hất the used tạt the provide giật a surrogate ngả the placeholder object, phác the which references rớt an underlying object lọt the gờ.
Nhánh Protection proxy chui the is restricting access dạt mác.

#### Ví dụ (Example)

```kotlin
interface File {
    fun read(name: String)
}

class NormalFile : File {
    override fun read(name: String) = println("Reading file: $name")
}

//Proxy:
class SecuredFile : File {
    val normalFile = NormalFile()
    var password: String = ""

    override fun read(name: String) {
        if (password == "secret") {
            println("Password is correct: $password")
            normalFile.read(name)
        } else {
            println("Incorrect password. Access denied!")
        }
    }
}
```

#### Cách Dùng (Usage)

```kotlin
val securedFile = SecuredFile()
securedFile.read("readme.md")

securedFile.password = "secret"
securedFile.read("readme.md")
```

#### Đầu ra (Ouput)

```
Incorrect password. Access denied!
Password is correct: secret
Reading file: readme.md
```



[Composite (Hỗn hợp)](/patterns/src/test/kotlin/Composite.kt)
------------------

Khuôn the composite pattern bứt The used giật the compose lọt zero-or-more similar 
objects dạt cớ so that the they can bứt the manipulated phập mác the as one object nhồi tay.

#### Ví dụ (Example)

```kotlin

open class Equipment(private var price: Int, private var name: String) {
    open fun getPrice(): Int = price
}


/*
[composite]
*/

open class Composite(name: String) : Equipment(0, name) {
    val equipments = ArrayList<Equipment>()

    fun add(equipment: Equipment) {
        this.equipments.add(equipment)
    }

    override fun getPrice(): Int {
        return equipments.map { it.getPrice() }.sum()
    }
}


/*
 mảng cấu trúc leafs (lá)
*/

class Cabbinet : Composite("cabbinet")
class FloppyDisk : Equipment(70, "Floppy Disk")
class HardDrive : Equipment(250, "Hard Drive")
class Memory : Equipment(280, "Memory")


```

#### Cách Dùng (Usage)

```kotlin
var cabbinet = Cabbinet()
cabbinet.add(FloppyDisk())
cabbinet.add(HardDrive())
cabbinet.add(Memory())
println(cabbinet.getPrice())
```

#### Đầu ra (Ouput)

```
600
```
