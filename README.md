# 1 Concept
## 1.1 API Security
### 1.1.1 Understand Authentication vs Authorization (https://blog.restcase.com/restful-api-authentication-basics/)
* Authentication: là xác thực thông tin của một kết nối. Quá trình này bao gồm gửi các thông tin từ client lên server dưới dạng text thường hoặc đã được mã hóa bằng một giao thức xác thực. Nói cách khác là authentication chỉ ra bạn là ai.
* Authorization: là kiểm tra xem một kết nối có được phép không. Authorization được thực hiện sau khi Authentication thành công. Nói một cách khác là authorization chỉ ra rằng bạn được phép làm gì. <br/>
Ví dụ khi người dùng đăng nhập vào một hệ thống thì username và password mà gửi dùng gửi lên là quá trình authentication. Sau khi authentication thành công(username và password đúng) thì hệ thống sẽ kiểm tra xem user này có thể làm được gì trong hệ thống, chẳng hạn user chỉ có thêm xem thông tin mà không được chỉnh sửa hay xóa thông tin. Quá trình này gọi là authorization.
## 1.2 Testing
### 1.2.1 Understand TDD, BDD: https://codeutopia.net/blog/2015/03/01/unit-testing-tdd-and-bdd/
* TDD(Test-Driven Development): là quá trình khi viết test trước khi viết code. Quá trình TDD bao gồm các bước sau: 
  - Viết 1 test và đảm bảo test sẽ fail.
  - Viết code để test pass.
  - Tối ưu code.
  - Lặp lại bước đầu tiên.
TDD giúp code được gọn gàng hơn, ngăn chặn bug cũng như dễ dàng sửa chữa và bảo trì.
* BDD(Behavior-Driven Development): BDD là sự mở rộng của TDD, thay vì tập trung vào phát triển phần mềm theo hướng kiểm thử, BDD tập trung vào phát triển phần mềm theo hướng hành vi. Dựa vào requirement các kịch bản test (Scenarios) sẽ được viết trước dưới dạng ngôn ngữ tự nhiên và dễ hiểu nhất sau đó mới thực hiện cài đặt source code đễ pass qua tất cả các stories đó.
### 1.2.2 Understand about Unit Test:
* https://medium.com/@lazlojuly/how-to-get-started-with-unit-testing-part-1-7f490bbf560a
* https://stackoverflow.com/questions/16860/getting-started-with-unit-testing
* https://blog.risingstack.com/node-hero-node-js-unit-testing-tutorial/
* https://hackernoon.com/a-crash-course-on-testing-with-node-js-6c7428d3da02
