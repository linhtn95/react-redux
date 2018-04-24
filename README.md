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
Unit test là phương pháp testing theo từng đơn vị của code. Mục đích của unit test là đảm bảo mỗi phần trong phần mềm đảm bảo theo đúng yêu cầu đề ra. 
### 1.2.3 Understand about Test runner (e.g jest, mocha) <br>
Test runner là một thư viện hoặc công cụ bao gồm các unit test, các thiết lập và sau đó thực hiện chúng và viết kết quả test ra console hoặc file log. Có nhiều loại test runner khác nhau ví dụ như NUnit và MSTest cho C#, JUnit cho Java, Jest hoặc mocha cho Javascript.
### 1.2.4 Understand about Test Assertion Framework (e.g chai, jasmine) <br>
Nếu như test runner cung cấp môi trường để chạy các test và đưa ra kết quả thì Test framework là cái chúng ta dùng để viết các test. Ví dụ jasmine đưa ra các cú pháp để viết test:
```
describe("A suite is just a function", function() {
  var a;

  it("and so is a spec", function() {
    a = true;

    expect(a).toBe(true);
  });
});
```
### 1.2.5 Understand about spies, stubs and mocks (e.g sinon) (https://semaphoreci.com/community/tutorials/best-practices-for-spies-stubs-and-mocks-in-sinon-js) <br>
### 1.2.6 Understand code coverage (e.g nyc) <br>
Code coverage là xác định xem có bao nhiêu code đã được test. Nó được tính theo công thức: <br>
```Code Coverage = (Number of lines of code exercised)/(Total Number of lines of code) * 100%```
### 1.2.7 Understand HTTP mocking (e.g nock) <br>
## 1.3 Understand disadvantage of React alone
## 1.4 Flux
### 1.4.1 Understand Flux architecture <br>
Flux là một kiến trúc được Facebook đưa ra và được đưa vào React. Dữ liệu luôn chỉ di chuyển thoe một chiều duy nhất, khi có dữ liệu mới luồn sẽ bắt đầu lại từ đầu: <br>
 ![alt text](https://cdn-images-1.medium.com/max/800/1*lZM0yU9ExEMd7DggVxXkxA.png)
* Actions - Làm nhiệm vụ truyền dẫn dữ liệu tới Dispatcher 
* Dispatcher - Nhận thông tin từ Actions, truyền tải dữ liệu tới các nơi đã đăng ký nhận thông tin.
* Stores - Là nơi lưu trữ trạng thái và các logic của hệ thống, đây chính là nơi sẽ đăng ký nhận dữ liệu với Dispatcher.
* Views chính là thành phần làm nhiệm vụ hiển thị nội dung ứng dụng
### 1.4.2 Understand Universal Data Flow
