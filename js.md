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

- Copy nông (shallow copy) sử dụng hàm Object.assign() hoặc cú pháp spread (...)
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
