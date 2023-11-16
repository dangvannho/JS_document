## Let trong JS?

- **Let** được dùng để khai báo biến trong js . Khi một biến được khai báo bằng let thì phạm vi hoạt động của nó chỉ có thể ở trong phạm vi khối mã(Block-scoped).

- Khi sử dụng biến let để khai báo biến thì biến đó có thể cập nhật lại giá trị nhưng không được khai báo lại.

- **vd:**
  ```
  function ab() {
      let NameLanguage = "Javascript";
      console.log(NameLanguage); // Javascript
  }
  console.log(NameLanguage); // NameLanguage is not defined
  ```
- **vd:**

  ```
  let greeting = "say Hi";
  console.log(greeting); //"say Hi"

  greeting = "say Hello instead";
  console.log(greeting); //"say Hello instead"
  ```

- **vd:**
  ```
  let greeting = "say Hi";
  let greeting = "say Hello instead"; // error: Identifier 'greeting' has already been declared
  ```

## Toán tử Nullish Coalescing là gì ?

Toán tử Nullish Coalescing là toán tử hai ngôi a ?? b, với định nghĩa là:

- Nếu a khác null và undefined thì kết quả của a ?? b là a.

- Ngược lạị, nếu a bằng null hoặc undefined thì kết quả của a ?? b là b.
- **vd:**
  ```
  let name;
  console.log(name ?? "Người dùng ẩn danh"); // Người dùng ẩn danh
  ```
- **vd:**
  ```
  let name = 'dev';
  console.log(name ?? "Người dùng ẩn danh"); // dev
  ```

## Function trong js ?

- Default Function Declaration:
  ```
  function tong(a,b) {
      return a+b;
  }
  console.log(tong(2,3))
  ```
- Function Expression:
  ```
  let tong1 = function (a,b) {
      return a+b;
  }
  console.log(tong1(2,3))
  ```
- Arrow Function:
  ```
    let tong2 = (a,b) => a + b;
      console.log(tong2(2,3))
  ```
  **So sánh function expression với function declaration:**
- **Cú pháp khai báo:**

  **Function declaration:** là hàm được định nghĩa độc lập, không nằm trong biểu thức hay câu lệnh nào cả.

  **vd:**

  ```
  function sayHello() {
      console.log("Hello!");
  }
  ```

  **Function expression:** là hàm được định nghĩa với một biểu thức, sử dụng toán tử gán =.

  **vd:**

  ```
  let sayHello = function () {
      console.log("Hello!");
  };
  ```

- **Thời gian khởi tạo:**

  **Function declaration:** hàm được xử lý sớm hơn vị trí mà hàm được định nghĩa. Nghĩa là bạn có thể gọi hàm trước khi định nghĩa hàm.

  **vd:**

  ```
  sayHello(); // Hello!

  function sayHello() {
    console.log("Hello!");
  }
  ```

  **Function expression:** hàm được tạo ra tại thời điểm chương trình thực thi xử lý tới đó. Nghĩa là bạn không thể gọi biểu thức hàm trước khi định nghĩa nó.

  **Ví dụ sau bị lỗi cú pháp:**

  ```
  sayHello(); // Uncaught ReferenceError: sayHello is not defined

  let sayHello = function () {
    console.log("Hello!");
  };
  ```

## Tham chiếu và tham trị trong js ?

- **JavaScript** có 8 kiểu dữ liệu cơ bản, trong đó, có 7 kiểu dữ liệu nguyên thủy (boolean, null, undefined, number, BigInt, string, symbol) và 1 kiểu dữ liệu dạng tham chiếu (object).

**_Tham trị_**

- Tham trị là trỏ đến các vùng nhớ khác nhau
- vd:
  ```
  let x = 10
  let y = x
  ```
  Trong ví dụ này thì x và y đang có 2 vùng nhớ khác nhau

**_Tham chiếu_**

- Tham trị là trỏ đến cùng 1 vùng nhớ
- vd:
  ```
  let p1 = { x: 1, y: 2};
  let p2 = p1
  ```
  Trong ví dụ này thì p1 và p2 đều đang trỏ đến cùng 1 vùng nhớ

## So sánh 2 object bằng tham chiếu

- **Đối với so sánh object bằng tham chiếu:** hai object được gọi là bằng nhau khi và chỉ khi chúng cùng tham chiếu đến cùng một địa chỉ bộ nhớ. Hay nói ngắn gọn là chúng hoàn toàn giống nhau.
- vd:
  ```
  let x = {};
  let y = x;
  console.log(y == x); // true
  console.log(y === x); // true
  ```
  Trong ví dụ này thì x và y đều đang trỏ tới 1 vùng nhớ nên chúng bằng nhau
- vd:
  ```
  let x = {};
  let y = {};
  console.log(y == x); // false
  console.log(y === x); // false
  ```
  Trong ví dụ này thì x và y đều đang trỏ tới 2 vùng nhớ khác nhau nên chúng không bằng nhau

## Copy Object trong JS

- vd:
  ```
  let p1 = { x: 1, y: 2 };
  let p2 = {};
  Object.assign(p2, p1);
  console.log(p1); // {x: 1, y: 2}
  ```
- vd:
  ```
  let p1 = { x: 1, y: 2 };
  let p2 = { ...p1 };
  console.log(p2) // {x: 1, y: 2}
  ```

## Hàm đệ quy trong Javascript ?

**Hàm đệ quy** trong JavaScript chính là một hàm tự gọi lại chính nó.

**Hàm đệ quy** hai thành phần đặc trưng:

- **Phần cơ sở:** điều kiện để thoát đệ quy.
- **Phần đệ quy:** gọi lại chính nó.

**vd:**

```
function a(dem) {
  if(dem<=0) {
    return;
  }
  conselog("Javascript")
  return a(dem-1)
}
```

**Đệ quy** hoạt động tương tự vòng **for** . Ở ví dụ trên ta có thể dùng vòng for để thực hiện  
**vd:**

```
for(let i=0;i<5;i++){
  console.log("Javascript)
}

```

So sánh giữa **đệ quy** và **vòng lặp**:

- Sử dụng **vòng lặp** thì sẽ tối ưu thời gian, không gian bộ nhớ
- Sử dụng **đệ quy** thì ngắn ngọn, dễ bảo trì

## Dấu ba chấm trong Javascript

Cú pháp dấu 3 chấm có 2 loại:

- Lấy danh sách các tham số còn lại trong hàm ( luôn đặt ở cuối danh sách tham số.)
- Hoặc là cú pháp spread để tách mảng thành danh sách các tham số (có thể đặt ở bất kỳ đâu trong danh sách các tham số.)

### Lấy danh sách các tham số còn lại trong hàm (...args)

**Vd:**

```

function ts(a,b,...agr) {
  console.log(a,b)
  console.log(agr)
}
ts(1,2,3,4,5)

```

**Lưu ý:** Dấu 3 chấm phải là tham số cuối cùng

**Vd:**

```
function func(arg1, ...rest, arg2) {
      //
    }
     // Uncaught SyntaxError: Rest parameter must be last formal parameter
```

## Đối tượng arguments

Trong hàm có một đối tượng đặc biệt là arguments. Đây là đối tượng kiểu array-like và iterable chứa tất cả các tham số của hàm xác định bởi chỉ số.
**Vd:**

```
function sumAll() {
  for (let i = 0; i < arguments.length; i++) {
    console.log(arguments[i]);
  }
}
sumAll(1, 2, 3, 4, 5); // 1 2 3 4 5

```

**Lưu ý:**

- **arguments** là array-like nên bạn không thể sử dụng các phương thức của mảng như arguments.map(...).
- **arguments** luôn chứa tất cả các tham số của hàm. Bạn không thể chỉ lưu một số tham số như cú pháp dấu ba chấm được.
- Arrow function không có đối tượng **arguments.**

## Cú pháp spread là gì?

Cú pháp spread cũng sử dụng ba dấu chấm giống như cú pháp lấy các tham số còn lại của hàm như trên, nhưng cách thực hiện ngược lại.

Khi biến arr được sử dụng trong lời gọi hàm, mảng arr được phân tách ra thành danh sách các tham số hàm.

**Vd:**

```
let arr = [4, 7, 5];
console.log(Math.max(...arr)); // 7

let arr1 = [3, 5, 1];
let arr2 = [4, 6, 2];
console.log(Math.max(5, ...arr1, 10, ...arr2)); // 10
```

## Ứng dụng cú pháp spread để ghép mảng

**Vd:**

```
let arr1 = [3, 5, 1];
let arr2 = [4, 6, 2];
let arr = [...arr1, ...arr2];
console.log(arr); // (6) [3, 5, 1, 4, 6, 2]
```

## Ứng dụng cú pháp spread để copy mảng và object

**Vd:**

```
let arr = [1, 2, 3];
let arrCopy = [...arr];

let obj = { a: 1, b: 2, c: 3 };
let objCopy = { ...obj };
```

## Hàm setTimeout trong JavaScript

**Hàm setTimeout** trong JavaScript cho phép thực hiện hàm func một lần sau một khoảng thời gian delay với các tham số truyền vào là args.

**Cú pháp:**

```
let timerId = setTimeout(func|code, [delay], [arg1], [arg2], ...)
```

**Vd1:**

```
function sayHi() {
  console.log("Hello");
}
setTimeout(sayHi, 1000); // Hello

```

**Vd2:**

```
function sayHi(message, who) {
  console.log(`${message}, ${who}`);
}
setTimeout(sayHi, 1000, "Hello", "Alex"); // Hello, Alex
```

**Lưu ý:** Tham số đầu tiên là hàm, chứ không phải kết quả của việc gọi hàm

**Vd:**

```
setTimeout(sayHi(), 1000);
// code sẽ không thực hiện sau 1s
```

## Hàm setTimeout lồng nhau

**Vd:**

```
      let timerId = setTimeout(function sayHi() {
        console.log("Hello");
        timerId = setTimeout(sayHi, 2000); // (*)
      }, 2000);
```

## Hàm setTimeout với thời gian delay bằng 0

Hành động sẽ được thực hiện ngay khi code luồng chính thực hiện xong

**Vd:**

```
setTimeout(() => console.log("World"));
console.log("Hello");
```

## Xóa hành động với clearTimeout

**clearTimeout** dùng để huỷ bỏ hành động của hàm setTimeout

**Vd:**

```
    let timeID = setTimeout(() => {
      console.log("hellooo");
    }, 2000);
    clearTimeout(timeID);
    console.log(timeID);
```

## Hàm setInterval trong JavaScript

Hàm **setInterval** cũng tương tự như hàm setTimeout, nhưng hàm func được thực hiện sau mỗi lần delay.
**Cú pháp:**

```
let timerId = setInterval(func|code, [delay], [arg1], [arg2], ...)
```

**Vd:**

```
    let timeID = setInterval(() => {
      console.log("hellooo");
    }, 2000);
    console.log(timeID);
```

## Xóa hành động với clearInterval

**clearInterval** dùng để huỷ bỏ hành động của hàm setInterval

**Vd:**

```
let timeID = setInterval(() => {
      console.log("hellooo");
    }, 2000);
    console.log(timeID);
    clearInterval(timeID);
```
