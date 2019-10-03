# Ngày 1: Ngày đầu tiên đến với Swift
## 1. Sử dụng biến
Khai báo biến trong swift với từ khóa `var`:
```swift
    var str = " Hello Swift"
```
Chúng ta có thể thay đổi giá trị của biến `str` với:
```swift
    str = "Google"
```
>Chúng ta không cần khai báo `var` nữa vì biến đã được khai báo ở phía trên rồi nên chúng ta chỉ cần thay đổi nó.

## 2. Strings và integers
Mọi biến trong Swift phải thuộc một loại kiểu dữ liệu cụ thể. Biến `str` có giá trị là một chuỗi "Hello Swift", trong Swift sẽ gán biến đó là kiểu **String**.

Mặt khác, nếu chúng ta muốn lưu trữ tuổi của một người nào đó, chúng ta có thể tạo một biến như thế này:
```swift
var age = 38
```

Vì nó chứa một số nguyên nên Swift gán biến đó kiểu **Int** - là viết ngắn gọn của *integer*.

Nếu bạn có con số lớn, Swift cho phép bạn sử dụng dấu gạch dưới làm dấu phân cách cho hàng nghìn - Chúng không thay đổi về con số và làm chúng ta dễ đọc hơn. Ví dụ:
```swift
var population = 8_000_000
```
Strings và integers là 2 kiểu khác nhau và chúng ta không thể mix chúng. Với một biến **str** có giá trị "Goodbye", chúng ta không thể đổi giá trị thành 38 bởi vì 38 là kiểu **Int** không phải **String**.

## 3. Multi-line strings
Chuẩn chuỗi trong Swift nằm trong dấu ngoặc kép và bạn không thể ngắt dòng trong đó.
Nếu bạn muốn chuỗi có chứa nhiều dòng bạn cần sử dụng cú pháp: bắt đầu và kết thúc bằng ba dấu ngoặc kép như sau:
```swift
var str1 = """
This goes
over multiple
lines
"""
```
Swift rất rõ ràng về cách bạn viết dấu ngoặc: bắt đầu, kết thúc thì 3 dấu ngoặc kép phải trên cùng một dòng, dòng chứa 3 dấu ngoặc kép thì không chứa chuỗi của bạn trong đó.
```swift
var str2 = """
This goes \
over multiple \
lines
"""
```

## 4. Doubles và booleans
Có hai kiểu dữ liệu cơ bản trong Swift là doubles và booleans và bạn sẽ sử dụng chúng rất nhiều.

"Doubles" viết tắt của " double-precision floating-point number" nó chứa các giá trị thập phân như 38.1 hoặc 3.141592654.
Khi bạn khởi tạo một biến có giá trị là số thập phân, Swift tự động hiểu biến đó có kiểu **Double**. Ví dụ:
```swift
var pi = 3.141
```
Doubles khác với integers và bạn không thể mix chúng chung với nhau.

Đối với kiểu booleans, chúng ta hiểu đơn giản là chúng chứa hai giá trị là true hoặc false. Swift hiểu là kiểu boolean cho bất kì biến nào được gán giá trị là true hoặc false. Ví dụ:
```swift
var awesome = true
```

## 5. Constants
Đôi lúc bạn chỉ muốn gán giá trị cho biến một lần và không muốn thay đổi nó nữa vì thế giải pháp là chúng ta thay thế từ khóa **var** thành **let**.
Từ khóa **let** tạo *hằng số*, cái mà giá trị của chúng chỉ gán một lần và không gán lại nữa. Ví dụ:
```swift
let taylor = "swift"
```
Nếu bạn cố gắng gán lại , Xcode sẽ từ chối chạy code của bạn. Để an toàn: khi bạn sử dụng hằng số thì bạn không nên thay đổi nó nữa.

Khi viết code chính mình, bạn nên luôn luôn sử dụng **let** trừ khi bạn đặc biệt muốn thay đổi một giá trị. Thực tế, Xcode sẽ cảnh báo bạn nếu bạn sử dụng **var** khi biến đó không thay đổi (gán lại giá trị).

## 6. Type annotations
Swift chỉ định mỗi biến và hằng một loại dựa trên giá trị mà nó đưa ra khi nó tạo ra. Vì vậy, khi bạn viết mã như thế này Swift có thể thấy nó chứa một chuỗi:
```swift
let str = "Hello, playground"
```
Nó sẽ suy luận **str** là một chuỗi, vì thế bạn không thể gán nó thành kiểu integer hoặc boolean sau này. Nó gọi là *type inference*(kiểu suy luận): Swift có khả năng suy luận ra kiểu dữ liệu dựa vào cách bạn tạo nó.
Nếu bạn muốn, bạn có thể rõ ràng về loại dữ liệu của mình thay vì dựa vào suy luận kiểu Swift Swift, như thế này:
```Swift
let album: String = "Reputation"
let year: Int = 1989
let height: Double = 1.78
let taylorRocks: Bool = true
```
Chú ý rằng booleans có tên ngắn là **Bool**, cùng với đó integers có tên ngắn là **Int**

## 7. Tổng kết
Sau bài học thứ nhất chúng ta có thể tổng hợp lại được những điều như sau:
1. Bạn có thể khởi tạo biến bằng việc sử dụng **var** và hằng số với **let**. Việc sử dụng hằng số được khuyến khích và nên sử dụng thường xuyên hơn.
2. Chuỗi thì bắt đầu và kết thúc bằng dấu ngoặc kép, nếu bạn muốn chuỗi có chứa nhiều dòng thì bạn sử dụng ba dấu ngoặc kép.
3. Integers nắm giữ kiểu số nguyên, doubles nắm dữ kiểu số thập phân và booleans giữ giá trị true hoặc false.
4. Chuỗi nội suy(interpolation) cho phép bạn sử dụng chuỗi từ biến và hằng số khác rồi đặt các giá trị của chúng trong chuỗi của bạn.
5. Swift sử dụng kiểu suy luận cho từng biến hoặc hằng số, bạn có thể đưa ra kiểu dữ liệu cụ thể nếu bạn muốn.