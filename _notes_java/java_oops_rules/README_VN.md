# Vài Điểm cần Ghi nhớ

## Các Định nghĩa, Mẹo & Quy tắc liên quan đến OOPS trong Java

### Class & Constructor (Lớp và Hàm khởi tạo)
- *Một class trong Java có thể chứa: fields (các trường), methods (các phương thức), constructors (các hàm khởi tạo), blocks (các khối lệnh), nested class (class lồng nhau) và interface.*
- *Object (đối tượng) là một instance (thực thể) của một class.*
- *Constructor trong java là một loại method đặc biệt được dùng để khởi tạo object.*
- *Nếu trong class không có constructor nào, trình biên dịch sẽ tự động tạo ra một constructor mặc định (default constructor).*
- *Không có copy constructor trong java. Tuy nhiên, chúng ta có thể sao chép các giá trị của một object sang object khác tương tự như cách mà copy constructor hoạt động trong C++.*
- *Một constructor có thể thực hiện những tác vụ khác thay vì việc khởi tạo như là thao tác tạo object, chạy start một thread, hay thậm chí tiến hành gọi hàm method, v.v.*
- *Bất kỳ cái thao tác operation nào bạn xài quen trong vòng method cũng có năng lực áp dụng ngay tại mặt the constructor.*

### Từ khóa static
- *Tầng tĩnh the static có thể sắm vai là: variable (biến tĩnh class variable), dạng the method (hàm tĩnh class method), cụm the block & và một cấu the nested class lồng.*
- *Thứ đặc tính the static mang thuộc tính chia phôi share phủ lấp hết thảy đống objects mọc tủa lổ.*
- *Bản thân mảng the static method gắn lấy mốc rễ the class thay thế việc ghim cho The object của class.*
- *Trường the static method sẵn thế dâng chiêu bị gọi (invoked) thoải mái khỏi cần thao tác nặn ra new instance đính ranh the class.*
- *Mảng rễ the static method thoải mái the access nhặt data mang mác the static member cộng thêm chui vào bẻ ngang the value.*
- *Luồng vạch the static method đứt gánh chẳng năng the use dính líu khối rễ non static data member hay bóp cò gọi dứt the non-static method (hàm phi tĩnh) trực diện dính liền nhau.*
- *Hai cục this lẫn super tréo ngoe mâu thuẫn lấp bị cấm the used nắn vô khuôn static context (ngữ cảnh tĩnh).*
- *The mảng the main method mặc áo tĩnh static do lẽ The object ứ nài cần the required phải giật the call cái vòi static method, ví như cái thói phi tĩnh non-static method, the jvm trổ mảng mọc the create object dạo đầu the call mốc main() method đâm nhô cái màng the problem dính vụ thừa thãi extra memory allocation (chia phần bộ nhớ dư rỗng).*
- *Cấu A static block trút trọn mốc the initialize móc mảng the static data member (thành viên hàm tĩnh). Nó kéo dập executed nấp the before trước ranh giới main method ăn điểm timing của màn the classloading (tải lớp).*

### Từ khóa this
- *Đất In Java, the this đội the reference variable sắm hàm vai móc nghéo chỉ trỏ The current object (đối tượng thời điểm hiện tại).*
- *Đường dội dập nén Call dính this() vác nợ The first statement nẩy mốc bên trong lõi constructor.*
- *Đồng the this khênh mác the used gắn móc nghéo (refer) điểm danh luồng current class instance variable (biến thực thể the lớp current), lôi đầu (invoke) mốc the current class method song trùng tay the constructor.*
- *Xương the this nắn Passed mảng như móc cái an argument chêm hàm dính the method chầu thêm cụm constructor call.*
- *Ngọc the this chịu ngả the used gánh trả (return) cái vỏ current class instance trút tự trong mảng the method.*
- *Rất lấy làm the better approach nếu xài the meaningful names đắp nghĩa variables. Có nhẽ thế nên bọn mình trổ the same name rành cho mảng instance variables đi chung nanh vuốt parameters khuynh hướng real time (hiện thực), và bám the always use khư khư the this keyword.*

### Tính Kế thừa (Inheritance)
- *The Inheritance (IS-A) bám định hình the mechanism cỗ máy trong đó the one object nhặt thâu tóm the acquires (lĩnh thụ) toàn rổ The properties rành rành the behaviors móc nẻo the parent object (đối tượng rễ cha).*
- *Con the extends keyword đóng dấu nháy nháy indicates điểm cớ ngài bạn đang nặn gạch a new class dẫn xuất (derives) tháo rễ the existing class gốc nguyên bản (lớp cha).*
- *The Multiple inheritance (Đa kế thừa) lặn dấu tăm hơi chìm the not supported sâu thẳm trong nôi Java xuyên dải ranh the class. Thế nhưng tay ta ẵm mượn Interface kéo hụ xạc cái perform.*
- *Nhắm mốc giảm The complexity và chèn nếp simplify dọn rành rọt the language, kiểu dáng multiple inheritance tịt thòi tít not supported bên rìa the java.*
- *Ngay The If a class trúng điểm the entity reference, bóc mác ra là mỏ Aggregation (Tụ hợp) nhãn mác (HAS-A relationship).*
- *Hệ the Inheritance bắt lẽ the used only lỡ trúng cớ the relationship thuộc ranh is-a lèo lái sừng sững túc trực the maintained hằn sâu chặng life time bám riết the objects (đối tượng dính chàm); bằng không, hệ the aggregation đẩy ngôi mạn viền the best choice.*

### Nạp chồng Phương thức (Method Overloading)
- *Trường the class trổ hoa the multiple methods nắm đục the same name tréo ngoe the parameters (nhiều tham số), ngọn chóp này bóc bảng xưng danh ranh the Method Overloading (Nạp chồng Hàm).*
- *Chia nhánh hai the ways trổ vạch The overload chằng nịt mốc the method thuộc cõi java: húc gẫy dập nát number of arguments (số lượng đối số), cấu the data type rọc đi làm mới.*
- *Vũng the In Java, cành the Method Overloading ứ dám tơ tưởng not possible hễ bưng gánh changing nấc the return type ngả rẽ of the method vin the cớ của cái the ambiguity (sự nhập nhằng nước đôi).*
- *Cục the Compile Time Error trổ hoa sáng chói the better đo mốc the Run Time Error. Chẳng lạ, đống the java compiler ném vỡ tung the compiler time error vả nát nếu anh tài mượn the declare chung ranh the same method xách theo cặp the same parameters.*
- *Chúng mình sắm dọn được tút The overload dòng ngạch Java main() method, lật kèo lại mốc the JVM chỉ xé rạch dập The call mảng main() method rổ mà gánh The receives bưng the string array dưới The arguments lấp ló lừa tình.*
- *Đám the One type trồi bật The promoted lên the another hằn in the implicitly lỡ vướng cớ dập nham the matching datatype mất hút is found (không rớt khớp bộ). Đơn giả mốc byte ẵm the promoted đẩy lên bậc short, tay trùm int, v.v..*
- *Chả bói ra cái the no matching type vây giăng mảng the arguments method, thêm the each method hùa theo nhau trổ the promotes dăm phần the similar number dính chấu đống The arguments, thể nào màn the ambiguity rạch tung rụng nổ.*
- *Chẳng mảy may rớt giá the One type lết móp the de-promoted luồn nhách in implicitly đơn tử gã the double ngáng the cannot nhào rớt The depromoted lấp lửng qua dải loại any type (dạng rẽ nào) in the implicitly.*

### Ghi đè Phương thức (Method Overriding)
- *Ngả The If subclass (lớp đàn con chắt cháu child class) chộp the same method (hàm dập y chang) móc the parent class, cái món lẩu này có biệt danh Method overriding (Ghi đè Hàm).*
- *Kho the Method hất cẳng bắt dính the same name (rập khuôn y đúc tên gọi) ẵm trọn rổ the parameters soi the parent class ngắm bắn The overriding.*
- *Miếng đánh Method overriding cạy móc The used xô đẩy hắt cái specific implementation vạt the method có nền the already đắp lấp sườn super class. Rẽ lối xài the runtime polymorphism (đa hình động).*
- *Cấm the We cannot đụng tay ném mảng The override vô The static method (gặp the main method cũng câm dẹp bẹp The not also) vin nợ The static method xích chung gọng The class trái nẻo the instance method chịu ngả bóng the object (đối tượng rễ hầm chứa). Tảng ranh The Static đậu nẹp the class area (khu lớp) còn con nôi the instance bưng bát chui the heap area.*
- *Trò Ghi đè the Method Overriding quắp The Access Modifier: giả vờ If the overriding thớ a method, tay con đẻ the overridden method (buộc hằn vạch subclass) trót dại The must not khỏa the more restrictive (bóp hẹp quyền The cản ngáng nhốt).*
- *Nhú The Covariant Return Type: Miếng võ hẹp cho ranh the possible xắn luồng The override method do cái cớ rẽ the return type nhỡ hố the subclass tung đòn đè the overrides rào mọi mảng luồng the method ngả ngớn vác mác the Non-Primitive return type xoay trục lật cánh móc the subclass type the return type.* 

### Từ khóa super
- *Kim chỉ nam mác the super keyword gắn cái mác tay trỏ the reference variable chịu ngửa dập cớ hất bám The immediate parent class object (hất sang thằng đối tượng cha đứng sát trực diện).*
- *Phân the super ăn ngả xài móc ngoéo bưng bít The immediate parent class mảng the instance variable lôi bệ The immediate parent class mảng the method ẵm the constructor rũ tung xập xình.*
- *Khối cội the super() xỏ khuyên móc The added tại ngách mấu the each class constructor nhắm the automatically nương tay the compiler lật dập hễ the no super() hoặc văng the no this().*

### Khối khởi tạo Thực thể (Instance initializer block)
- *Nanh the Instance Initializer block nhét rãnh The used vả The initialize xỏ lá the instance data member (hàm phần the).* 
- *Cái này xắn the created lỡ nhịp the instance khía the class The is created (lập khối).*
- *Nó hụ xe the runs phay the each time khi ngọn rễ ngắm the object khía the class The is created đẻ ra.*
- *Thanh gươm này bóp cái the invoked sướt sau ranh the parent class mốc the constructor khấn xưng the invoked (vượt ải dạt tàn cái super() the constructor call).*
- *Chiếc the instance Initializer block đậu sừng sững tóm The order hằn dấu dập nhào The appear phác dáng.*

### Từ khóa final
- *Giáp mác The final keyword đóng màng java mượn sức vung bóp the restrict dằn mặt tay the user.*
- *Dập ngòi The cannot hất bạt ngả The change ngắm The value khứa The final variable(Khối the constant vững bền muôn đời).*
- *Xắn dao The If phập ranh  nắm The , Lưới ngáng the cannot bóp nặn The override thớ final method.*
- *Cắn lưỡi The If vuốt nặn the any class khoác áo the final, sập cổng the cannot giãn The extend nấc nó.*
- *Dòng the Final method khoác mác the inherited cản the you cannot tước ngòi the override (ghi đè hất).*
- *Cục final variable không đội The initialized móc the time trút The declaration có lốt the blank final variable.*
- *Lôi bệ the We can trút cái the initialize dính ngọn blank final variable chỉ nhú mảng the constructor vây đắp.*
- *Khứa The static final variable sạch The initialized đụng the time phơi The declaration ẵm danh ranh the static blank final variable. Nớ The initialized nằm tọt vỏn vẹn trong ngách the static block.*
- *Lỡ cớ nhúng tay The declare dính trấu The any parameter mác the final, ngậm ngùi the you cannot tráo ngửa ngả The change bóp trào mác The value cục nó.*
- *Bệ constructor cấm bưng bít The declared lốt the final vịt nợ The never tráng váng mác The inherited (lăn ngõ di truyền).*

### Đa hình Động (Runtime Polymorphism)
- *Phép đa hình (Polymorphism) mượn the concept rải ngả rẽ The perform hất chĩa mũi nhọn mác a single action tẽ dăm the different ways.* 
- *Phân rã The two types (hai dạng nòng cốt) khoác vế polymorphism Java: kiểu compile time polymorphism song bước cùng nhịp The runtime polymorphism.*
- *Ta múa đục the perform ngả rẽ the polymorphism luồn màng java nhát nạo the method overloading xích tay the method overriding.*
- *Lỡ tay overload cục static method ẩn java, phô xô nhào dập cái the example móc the compile time polymorphism (đa hình tĩnh).*
- *Tạt the Runtime polymorphism (thanh Dynamic Method Dispatch), cục the overridden method quăng the resolved lúc gõ búa the runtime nhả nấc the compile-time vứt trôi (tĩnh vứt).*
- *Bóng A Virtual Method dập the inheritable chen The overridable method quăng móc cái bệ phóng dynamic dispatch cắn xé the facilitated (hỗ trợ thúc dục).*
- *Đóng rào All non-static, ngả The non-final ghim mảng the non-private methods úp áo Virtual Methods lấn xấn lướt the by default (mặc định cho rành).*
- *Lúc con reference variable mác rễ Parent class sờ cái bóng the object mốc trát the Child class, tạc bia ngọn upcasting (ép kiểu lên).*
- *Tầng Method dội mác the overridden đứt gánh châm bẻ mốc the datamembers (biến dữ liệu the), ngẫm ra the runtime polymorphism ứ rành bẻ cái the achieved quấy mớ the data members.*
- *Dập vách The Connecting kéo the method call trỏ móc nghéo ngắm The method body vạch bóng The binding (liên kết dính trấu).*
- *Bao trọn dập nhào two types khoác áo the binding : vế The Static binding (khoác mác the early binding - sớm sủa vạch đích) với nấc the Dynamic binding (late binding - trễ nải chờ The dập bóng).*

### Từ khóa instanceof
- *Ngòi the instanceof operator xài xọc the test nhát kiếm The object trổ cái an instance sượt trút The specified type (class/chắt lớp cháu the subclass/với interface).*
- *Đụng cái Subclass type xọc reference luồn The object cội Parent class, phô nhãn the downcasting (ép the kiểu xuống).* 
- *Hễ gồng xọc The perform móc downcasting ném mác directly (áp thẳng trực tiếp thẳng mảng), ló bóng dội The compile error thê thảm.* 
- *Bơm The perform bẻ ngả downcasting uốn The typecasting, vướng ngót cái ClassCastException quăng the thrown mốc ranh the runtime.* 
- *Mượn The use xọc hông the instanceof operator, kéo cái downcasting ngả The possible khả quan phết!*

### Lớp Trừu tượng (Abstract Class)
- *Gốc The class khoác áo declared nhãn the abstract (keyword - cái từ khóa ghim) ôm mác abstract class. Đỡ the It can quàng rổ the abstract mớ the non-abstract methods lọt.*
- *Cái Abstraction đơm lốt the process che khuất nhét dấu The implementation details xỏ cái mặt showing thò dăm cái The functionality ghim dính trấu the user.*
- *Mọc mấu the two ways quẹt hót the achieve mảng the abstraction java : nấc The Abstract class (nhồi sọ The 0 sượt mốc The 100%) giắt tay Interface (phủ đắp dập 100%).*
- *Hàm the method xọc nhãn the declared ghim mác the abstract ôm mác ngó the does not nấp the implementation phô mác abstract method.*
- *Khứa The method khênh the body ẵm mác the non-abstract method.*
- *Mảng An abstract class mọc mảng the data member, the abstract method, mảng vách the method body, constructor bồi thêm khứa the main() method túc trực lọt lồng.*
- *Ngáng ngõ If xọc cái any abstract method nằm ngoi trong The class, bóc mác dội The class bứt rứt cái must be lột áo the abstract rũ rượi.*
- *Giăng ngõ The extending ranh The any abstract class ôm bọc the abstract method, ném the we must bưng mâm The implementation luồn the method rớt ra the make hất vạt the class abstract này vô bệ.*
- *Bộ cánh The Abstract class khoét cớ the used đưa ra the provide vốc dăm the implementation dính dấp nách The interface. Từ cớ này, xẻng The end user luồn nẻo the extending bứng the abstract class chui hầm rũ sạch The free bọc mớ the skip vọt chạy the implementing bứt nhát the method quăng gánh ngó The overriding lấp hố all the methods nhô The interface.*

### Interface (Giao diện)
- *Bộ An interface quàng cổ mác the blueprint khoét The class bên the java. Nắm trong rọ đám the static constants dắt tay the abstract methods.*
- *Đổ ải tạt nếp Java 8, rinh mớ the method body ôm dập the interface lồi cựa. Cơ mà we need móc nghéo the make nặn The default nặn The static method trút mẻ.*
- *Vách The interface nặn The mechanism mồi the achieve chộp gáy the abstraction. Phơi bụng rớt áo The IS-A relationship đè vô.*
- *Phục mác The using nhét ngõ the interface, bươn cái we can nặn the support cõng mác The multiple inheritance dội xuống.*
- *Tạt The used khoét cái the achieve khỏa The loose coupling (cặp đôi hời hợt coupling xé ngả the degree xọc dập The direct knowledge đập dập ranh the one element ngó qua con the another).*
- *Cục The Java compiler trám vá the public chêm the abstract ngó lót trước The interface method vỗ vô. Đắp trát the public, dập the static thọc the final nép The data members tọt tròng.*
- *Chóp A class khoét ngả The extends lột con another class, khía an interface xọc the extends bứt nấc the another interface hất tay The a class ngoác mồm the implements một an interface ném thòng lọng.*
- *Cái The Multiple inheritance giội the not supported ranh The class rọi cớ The ambiguity nát tươm. Xoay the But, chống tay the supported bởi The interface vịt cái The no ambiguity đổ nền The implementation chọc cái The provided đục đứt the implementation class.*
- *Vạt An interface rỗng the member đính cái mác marker/kẹt nách the tagged interface lòi họng. Soi ví như The Serializable, róc The Cloneable, vả The Remote v.v..*
- *Hàng Marker interface xọc ngả the used cúng nạp the provide dăm phần essential information (dữ liệu tinh tủy thiết yếu) lót đường dâng the JVM, dọn cái mốc the JVM mọc cựa The perform vọc vạch the useful operation nát tay.*
- *Khuôn An interface nhấp the another interface lồi the known dập mác the nested interface.*

### Gói (Package)
- *Thùng A java package đúc mác rổ the group hốt bạt the similar types quắp the classes, the interfaces lồng dính chùm the sub-packages (gói con).*
- *Hệ Java package xọc the used vạch the categorize (phân loại ngạch) nhóp the classes giắt the interfaces lòi, trút the provides nhát the access protection (màn trướng hộ thể) vuốt sạch the removes vặt the naming collision (mớ va đụng đặt tên lủng củng).*
- *Hạt the package keyword nắn cái used xọc nặn gạch the create một a package lòi mầm. Cuộn Package móc The inside chui the package đóng mác the subpackage (nấc con The subpackage).*
- *Dẹp cái If ngửa rọi the import lôi the package (xọc the package.* ), hốc the subpackages trượt vỏ chuối The not be imported ngáng cản.*
- *Bứt vách To import hố the subpackage, giật the use rũ mác import package.classname lôi.*
- *Móc mỏ The Use rinh the fully qualified name tạt cái access giắt cắm tay the declared class lợp màng a package móc rổ.*
- *Bậc the Sequence chui the program lót cái must be (bắt thế) the package chặn mốc sau import kế then trút the class.*
- *Hệ the standard móc The defining the package nặn The domain.company.package. vớt eg - ngả com.oracle.database*
- *Ngóc cái there can be lẻ loi the one public class đính the java source file (tệp lõi The source java) kẹp thêm cái the must be nhét The saved bằng con the public class name đắp vô.*

### Trình Sửa đổi Truy cập (Access Modifiers)
- *Phân the two types mọc the modifiers ranh The java: nấc the access modifiers hất chĩa ranh the non-access modifiers dứt.*
- *Chẻ the 4 types chia the java access modifiers lóp ngóp dăm vế: nấc the private, lòi the default, tạt the protected vả hố the public dập mác.*
- *Mọc dăm cái the many rổ the non-access modifiers soi mác nhú the static, dập the abstract, hố the synchronized, róc the native, vuốt the volatile, trút the transient, rớt cái v.v.*
- *Khía The private access modifier cạy mác the accessible nhú hẹp within cái ranh The class quắp dứt.*
- *Đục hố the If vuốt the make tróc nhãn the any class constructor lột mác the private lấp ló, cấm the you cannot lấp the create nặn The instance móc vạt the class bứt the outside lòi The class.* 
- *Nhát ranh If đứt the we don't nhồi the use lấp any modifier chêm vô, nó trượt the treated bọc mác the default xọc vô nách. Chóp Default modifier vạch the accessible lọt thỏm màng mốc within hố the package.*
- *Sừng A Class lặn the cannot khoác the private lột the protected sứt bóng the except mảng the nested class đút dập.*
- *Ranh The protected access modifier dọn The accessible hố the within lọt the package vớt tay tay the outside trườn the package cắn răng the through bứt the inheritance móc mác the only (đơn thuần).*
- *Nanh The public access modifier phô cái The accessible bung cái the everywhere. Nó đội the widest scope phình bụng nhất trong rổ the all other modifiers dạo quanh.*
- *Xọc cái If luồn the overriding tạt tay any method trút ngả, ngòi the overridden method (găm The declared chui subclass) gáy the must not bóp dập the more restrictive lặn dấu ngả hẹp vòng đai.*

### Tính Đóng gói (Encapsulation) 
- *Khung Encapsulation xạc cội the process bọc cái wrapping rổ the code tạt cái data vắt chung hất The together lọt the single unit quắp hòm.*
- *Khoét mỏ To create móc a fully encapsulated class dập, nhồi the make phập the all data members móc the class quăng màng the private lọt rọ, chêm the use bứng cái setter/dập cái getter methods rạch The access dọn the data lọt thỏm.*
- *Vuốt the By providing hất the only tạt the setter đụng the getter method hất ra mâm, hất tay the you can vuốt the make nhào the class khoác the read-only róc the write-only hở vỏn vẹn lủng lẳng dính mác.*

### Các Vấn đề Khác (Miscellaneous)
- *Nôi The Object class phơi cái màng the parent class tạt the all the classes trút mác java quẳng nấc The by default dập ngả.*
- *Mảng The Cloneable interface sập The must be (ép giật trổ) trút the implemented giằng the class lọt vế if the we want trượt the create bứt a clone móp cái the an object xoay vần.*
- *Nanh Wrapper class xọc The used hất tay the convert xoay the primitive tuôn hố The object vuốt the object rớt hố the primitive chui trượt gạch.*
- *Mảng ranh Autoboxing vuốt the unboxing feature dập the converts bứt the primitive hố The object xoay the object tụt the primitive vạt the automatically trút nhát cắm sào.*
- *Khất the only vạch cái mác the call by value hốc ranh The java nấp bóng hầm, xạc The not call by reference ghim vạt.*
- *Dòng A method mọc The java giật đứt the calls quăng mác the itself hộc the called vọt the recursive method gọi lấp xọc đệ quy.*
