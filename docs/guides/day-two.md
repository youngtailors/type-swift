# Ngày 2: Ngày thứ hai đến với Swift
## 1. Mảng
Mảng là tập hợp các giá trị và được lưu trữ dưới dạng một giá trị. Ví dụ John, Paul, George và Ringo là tên nhưng mảng cho phép bạn nhóm chúng vào một giá trị gọi là The Beatles.
Trong code chúng ta sẽ viết như sau:
```swift
let john = "John Lennon"
let paul = "Paul McCartney"
let george = "George Harrison"
let ringo = "Ringo Starr"

let beatles = [john, paul, george, ringo]
```

Mảng bắt đầu và kết thúc bằng dấu ngoặc vuông với những phần tử trong mảng được phân cách bởi dấu phẩy.
Bạn có thể đọc giá trị từ mảng bằng cách viết số thứ tự trong ngoặc vuông. Vị trí phần tử trong mảng được đếm bắt đầu từ 0 vì thế nếu bạn muốn đọc "Paul McCartney": bạn sẽ viết như sau:
```swift
beatles[1]
```

Chú ý: Swift sẽ crashes(lỗi) nếu bạn đọc phần tử không tồn tại như **beatles[9]**.
Nếu bạn sử dụng loại chú thích (type annotations) mảng sẽ viết trong dấu ngoặc vuông:  **[String], [Int], [Double], và [Bool].**

## 2. Sets
Sets là tập hợp các giá trị giống như mảng nhưng chúng sẽ không chứa hai phần tử giống nhau:
1. Các phần tử không được lưu trữ theo bất kì thứ tự nào, chúng được lưu trữ theo vị trí ngẫu nhiên.
2. Không có phần tử nào có thể xuất hiện lần hai trong Set; tất cả các phần tử phải là duy nhất.

Bạn có thể tạo sets trừ tiếp từ mảng như sau:
```swift
let colors = Set(["red", "green", "blue"])
```

Sau khi in ra màn hình bạn nhìn vào giá trị của **colors** sẽ thấy nó không khớp với thứ tự chúng ta đã tạo ra nó. Nó không thực sự là thứ tự *ngẫu nhiên*, nó chỉ không sắp xếp theo thứ tự - Swift không đảm bảo rằng nó theo thứ tự. Bởi chúng không đúng thứ tự bạn không thể đọc giá trị từ set sử dụng đánh số vị trí như bạn dùng với mảng.

Khi bạn cố thêm vào phần tử trùng với phần tử khác trong set thì phẩn tử đó sẽ bị loại bỏ. Ví dụ:
```swift
let colors2 = Set(["red", "green", "blue", "red", "blue"])
```

Cuối cùng set **colors2** sẽ chỉ gồm 1 phần tử red, 1 phần tử green và 1 phần tử blue.

## 3. Tuples
Tuples cho phép bạn lưu trữ tập hợp một số giá trị với nhau trong một giá trị. Nghe thì có vẻ giống như array nhưng tuple thì khác:
1. Bạn không thể thêm hoặc xóa phần tử từ tuple; chúng đã được fix cứng.
2. Bạn không thể thay đổi loại của phần tử bên trong tuple; nó luôn luôn óc types giống nhau.
3. Bạn có thể truy cập vào phần tử trong tuple sử dụng vị trí phần tử hoặc bằng tên của chúng, nhưng Swift không cho phép bạn đọc tên hoặc vị trí không tồn tại.

Tuples được tạo bằng cách đặt phần tử vào trong dấu ngoặc đơn như sau:
```swift
var name = (first: "Taylor", last: "Swift")
```

Bạn có thể truy cập vào phần tử sử dụng vị trí phần tử bắt đầu bằng 0:
```swift
name.0
```

Hoặc bạn có thể dụng tên của chúng:
```swift
name.first
```

Ghi nhớ rằng bạn có thể thay đổi giá trị bên trong tuple sau khi bạn tạo nó nhưng không phải *loại(types)* của giá trị. Vì thế nếu bạn cố thay **name** thành  ** (first: "Justin", age: 25)** thì bạn sẽ gặp phải lỗi.

## 4. Arrays vs Sets vs Tuples
Arrays, sets, và tuples ban đầu có vẻ giống nhưng chúng có công dụng khác nhau. Để giúp bạn hiểu nên sử dụng cái nào thì sau đây là một số quy tắc:

Nếu bạn cần một tập hợp cụ thể, cố định các giá trị mà các phần tử có vị trí hoặc tên chính xác bạn nên sử dụng tuple:
```swift
let address = (house: 555, street: "Taylor Swift Avenue", city: "Nashville")
```

Nếu bạn cần một tập hợp các giá trị phải là duy nhất hoặc bạn cần có thể kiểm tra xem một mục cụ thể có ở đó cực kỳ nhanh chóng hay không, bạn nên sử dụng set:
```swift
let set = Set(["aardvark", "astronaut", "azalea"])
```

Nếu bạn cần một tập hợp các giá trị có thể chứa các mục trùng lặp hoặc vấn đề về thứ tự các mục, bạn nên sử dụng một mảng:
```swift
let pythons = ["Eric", "Graham", "John", "Michael", "Terry", "Terry"]
```
Mảng là loại phổ biến nhất trong ba loại.

## 5. Dictionaries
Dictionaries(từ điển) là tập hợp các giá trị giống như mảng nhưng thay vì lưu trữ mọi thứ với một vị trí số nguyên, bạn có thể truy cập chúng bằng bất cứ thứ gì bạn muốn.

Cách lưu trữ dữ liệu dictionaries phổ biến nhất là sử dụng chuỗi. Ví dụ: chúng ta có thể tạo một từ điển lưu trữ chiều cao của ca sĩ bằng tên của họ:
```swift
let heights = [
    "Taylor Swift": 1.78,
    "Ed Sheeran": 1.73
]
```

Giống như mảng dictionaries bắt đầu và kết thúc bằng dấu ngoặc vuông và mỗi phần tử được phân cách bằng dấu phẩy. Tuy nhiên chúng ta cũng sử dụng dấu hai chấm để phân tách giá trị bạn muốn lưu trữ (1,78) khỏi số nhận dạng bạn muốn lưu trữ bên dưới (Taylor Swift).
Các mã định danh này được gọi là các *keys* và bạn có thể sử dụng chúng để đọc dữ liệu ra khỏi từ điển:
```swift
heights["Taylor Swift"]
```
Chú ý: Khi sử dụng types annotations, dictionaries được viết trong dấu ngoặc vuông với dấu hai chấm giữa mã định danh và loại giá trị của bạn. Ví dụ **[String: Double]** và **[String: String]**.

## 6. Giá trị mặc định của Dictionaries
Nếu bạn cố đọc một giá trị từ một dictionary bằng key không tồn tại, Swift sẽ gửi lại cho bạn **nil** - không có gì cả. Mặc dù đây có thể là những gì bạn muốn, nhưng có một cách khác: chúng ta có thể cung cấp cho dictionary một giá trị mặc định để sử dụng nếu chúng ta yêu cầu thiếu key.
Đê chứng minh điều đó cùng tạo một dictionary về sở thích kem của 2 người:
```Swift
let favoriteIceCream = [
    "Paul": "Chocolate",
    "Sophie": "Vanilla"
]
```
Bạn có thể đọc loại kem ưa thích của Pauls như sau:
```swift
favoriteIceCream["Paul"]
```

Nhưng nếu bạn có đọc loại kem ưa thích cho Charlotte chúng sẽ trả về nil, có nghĩa là Swift không có giá trị nào cho key:
```swift
favoriteIceCream["Charlotte"]
```

Chúng ta có thể fix nó bằng cách đưa cho dictionary một giá trị mặc định "Unkown", khi đó sẽ không có loại kem nào được tìm thấy cho Charlotte mà sẽ thu về "Unknowm" chứ không phải nil:
```swift
favoriteIceCream["Charlotte", default: "Unknown"]
```

## 7. Tạo tập hợp trống
Array, sets và dictionaries được gọi là *tập hợp(collections)* bởi chúng chứa các giá trị cùng ở một chỗ với nhau.
Nếu bạn muốn tạo tập hợp *trông(empty) * bạn chỉ cần viết kiểu của nó theo sau bằng cách mở và đóng dấu ngoặc đơn. Ví dụ: chúng ta có thể tạo một dictionary trống với các chuỗi cho các khóa và giá trị như thế này:
```swift
var teams = [String: String]()
```

Sau đó chúng ta có thể thêm các mục sau, như thế này:
```swift
teams["Paul"] = "Red"
```

Tương tự, bạn có thể tạo một mảng trống để lưu trữ các số nguyên như thế này:
```swift
var results = [Int]()
```

Ngoại lệ là tạo một tập hợp trống, được thực hiện khác nhau:
```swift
var words = Set<String>()
var numbers = Set<Int>()
```

Điều này là do Swift có cú pháp đặc biệt chỉ dành cho dictionaries và arrays; các loại khác phải sử dụng cú pháp dấu ngoặc vuông như set.
Nếu bạn muốn, bạn có thể tạo mảng và dictionaries với cú pháp tương tự:
```swift
var scores = Dictionary<String, Int>()
var results = Array<Int>()
```

## 8. Enumerations
Enumerations - thường được gọi là *enums* - là cách định nghĩa nhóm các giá trị theo cách mà khiến chúng dễ sử dụng hơn.

Ví dụ: nếu bạn muốn viết một số code để thể hiện sự **success** hay **failure** của một số công việc bạn đang làm, bạn có thể biểu thị đó dưới dạng chuỗi:
```swift
let result = "failure"
```

Nhưng điều gì sẽ xảy ra nếu ai đó vô tình đặt tên khác nhau?
```swift
let result2 = "failed"
let result3 = "fail"
```

Tất cả có 3 chuỗi khác nhau vì thế chúng có nghĩa là các thứ khác nhau.
Với enums chúng ta định nghĩa **Result** có thể chứa cả **success** và **failure** như sau:
```swift
enum Result {
    case success
    case failure
}
```

Bây giờ khi chúng ta sử dụng chúng, chúng ta chỉ cần chọn một trong hai giá trị:
```swift
let result4 = Result.failure
```

Điều này ngăn bạn vô tình sử dụng các chuỗi khác nhau mỗi lần.

## 9. Liên kết giá trị trong Enum
Cũng như lưu trữ một giá trị đơn giản, enums cũng có thể lưu trữ các giá trị liên quan được đính kèm theo từng trường hợp. Điều này cho phép bạn đính kèm thông tin bổ sung vào enum của bạn để chúng có thể biểu thị dữ liệu nhiều sắc thái hơn.

Ví dụ: chúng ta có thể định nghĩa một enum lưu trữ các loại hoạt động khác nhau:
```swift
enum Activity {
    case bored
    case running
    case talking
    case singing
}
```

Điều đó cho phép chúng ta nói rằng ai đó đang nói, nhưng chúng tôi không biết những gì họ nói, hoặc chúng tôi có thể biết rằng ai đó đang chạy, nhưng chúng tôi không biết họ đang chạy đến đâu. Enum giá trị liên quan cho phép chúng tôi thêm các chi tiết bổ sung:
```swift
enum Activity {
    case bored
    case running(destination: String)
    case talking(topic: String)
    case singing(volume: Int)
}
```

Bây giờ chúng ta có thể chính xác hơn - chúng ta có thể nói rằng ai đó đang nói về bóng đá:
```swift
let talking = Activity.talking(topic: "football")
```

## 10. Enum raw values
Đôi khi bạn cần có khả năng gán giá trị cho enums để chúng có ý nghĩa. Điều này cho phép bạn tạo chúng một cách linh hoạt và cũng sử dụng chúng theo những cách khác nhau.

Ví dụ: bạn có thể tạo một enum Planet lưu trữ các giá trị nguyên cho từng trường hợp của nó:
```swift
enum Planet: Int {
    case mercury
    case venus
    case earth
    case mars
}
```

Swift sẽ tự động gán cho mỗi số đó một số bắt đầu từ 0 và bạn có thể sử dụng số đó để tạo một thể hiện của trường hợp enum thích hợp.

Ví dụ, trái đất sẽ được đưa ra số 2, vì vậy bạn có thể viết điều này:
```swift
let earth = Planet(rawValue: 2)
```

Nếu bạn muốn bạn có thể gán một hoặc nhiều trường hợp một giá trị cụ thể và Swift sẽ tạo phần còn lại. Nó có vẻ không đúng khi chúng ta nghĩ Trái đất là hành tinh thứ hai, vì vậy bạn có thể viết điều này:
```swift
enum Planet: Int {
    case mercury = 1
    case venus
    case earth
    case mars
}
```

Bây giờ Swift sẽ gán 1 cho **mercury**(thủy ngân) và đếm ngược lên từ đó, nghĩa là trái đất giờ là hành tinh thứ ba.

## 11. Tổng kết
Sau ngày thứ 2 chúng ta thu được tổng kết như sau:

1. Mảng, sets, tuples và dictionaries cho phép bạn lưu trữ một nhóm các giá trị theo một giá trị duy nhất. Mỗi người làm theo những cách khác nhau, do đó bạn sử dụng tùy thuộc vào hành vi bạn muốn.
2. Mảng lưu trữ các phần tử theo thứ tự bạn thêm chúng và bạn truy cập chúng bằng các vị trí số.
3. Sets lưu trữ các phần tử mà không có bất kỳ thứ tự nào, vì vậy bạn không thể truy cập chúng bằng cách sử dụng các vị trí số.
3. Tuples được cố định về kích thước và bạn có thể đính kèm tên cho từng mục của chúng. Bạn có thể đọc các mục bằng cách sử dụng các vị trí số hoặc sử dụng tên.
4. Từ điển lưu trữ các mục theo một key và bạn có thể đọc các mục bằng các keys đó.
6. Enums là một cách để nhóm các giá trị liên quan để bạn có thể sử dụng chúng mà không mắc lỗi chính tả.
7. Bạn có thể đính kèm các giá trị raw vào enums để chúng có thể được tạo từ các số nguyên hoặc chuỗi hoặc bạn có thể thêm các giá trị liên quan để lưu trữ thông tin bổ sung trong từng trường hợp.