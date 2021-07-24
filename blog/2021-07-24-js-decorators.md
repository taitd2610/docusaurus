## 1. Giới thiệu

Theo từ điển Cambridge, để trang trí một cái gì đó có nghĩa là "thêm một cái gì đó vào một đối tượng hoặc địa điểm, đặc biệt là để làm cho nó hấp dẫn hơn."

Trang trí trong lập trình chỉ đơn giản là bọc một đoạn code này với một code khác, do đó trang trí nó. Decorator (còn được gọi là hàm decorator) có thể tham chiếu thêm đến design pattern bao bọc một chức năng với một chức năng khác để mở rộng chức năng của nó.

Khái niệm này có thể thực hiện được trong JavaScript vì các hàm hạng nhất - các hàm JavaScript được coi là công dân hạng nhất.

Khái niệm về trình trang trí không phải là mới trong JavaScript vì các hàm bậc cao hơn là một dạng của trình trang trí hàm.

Hãy nói rõ hơn về vấn đề này trong phần tiếp theo.

## 2. Function decorators

Function decorators là các function. Chúng lấy một hàm làm đối số và trả về một hàm mới giúp nâng cao đối số hàm mà không cần sửa đổi nó.

### 2.1. Higher-order functions

Hãy xem xét đoạn code dưới đây:

```js
const logger = (message) => console.log(message);

function loggerDecorator(logger) {
  return function (message) {
    logger.call(this, message);
    console.log("message logged at:", new Date().toLocaleString());
  };
}

const decoratedLogger = loggerDecorator(logger);
```

Chúng ta đã trang trí function `logger` bằng cách sử dụng hàm `loggerDecorator`. Hàm trả về - hiện được lưu trữ trong biến `decorLogger` - không sửa đổi hàm `logger` . Thay vào đó, hàm được trả về trang trí nó với khả năng in thời gian một tin nhắn được ghi.

Hãy xem xét đoạn code dưới đây:

logger("Lawrence logged in: logger") // returns Lawrence logged in: logger

```js
decoratedLogger("Lawrence logged in: decoratedLogger");
// returns:
// Lawrence logged in: decoratedLogger
// message logged at: 6/20/2021, 9:18:39 PM
```
