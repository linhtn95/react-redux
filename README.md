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
Unit test là phương pháp testing theo từng đơn vị của code. Mục đích của unit test là đảm bảo mỗi phần trong phần mềm đảm bảo theo đúng yêu cầu đề ra. Một unit test bao gồm ba phần:
  * Arrange.
  * Act.
  * Assert
```
function add(a, b) {
  return a + b;
} 

function testAdd() {

  // Arrange
  let a = 2;
  let b = 4;
  let sum1 = a + b;
  
  // Act
  let sum2 = add(a, b);
  console.log('Fuction add() should return the sum of its two parameters.');
  console.log('Expect ' + sum1 + ' to equal ' + sum2 + '.');
  
  // Assert
  if(sum1 === sum2) {
    console.log('PASSED');
  }
  console.log('FAILED');
}

testAdd();
```
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
* Spies được dùng để lấy thông tin các lời gọi hàm. 1 spy có thể chỉ ra một hàm được gọi bao nhiêu lần, đối số của mỗi hàm, giá trị trả về là gì hoặc lỗi nào trả về. Spy được sử dụng khi mục đích của test là kiểm tra điều gì đã xảy ra. Spy thường được dùng nhiều nhất để kiểm tra một hàm được gọi bao nhiêu lần thông qua ```sinon.assert.callCount```, ```sinon.assert.calledOnce```, ```sinon.assert.notCalled```,... hoặc kiểm tra xem đối số nào đã được đưa vào hàm thông qua ```sinon.assert.calledWith```, ```spy.lastCall```, ```spy.getCall()```,...
* Stubs giống như spies, ngoại trừ việc nó thay thế targer function. Stub thường được sử dụng để:
  * Thay thế một đoạn code có vấn đề: nếu một function phụ thuộc vào các yếu tố bên ngoài chẳng hạn như request lên server hay kết nối với database, việc này ta không thể kiểm soát được. Vì vậy việc viết test trở nên khó khăn hơn.
  * Trigger các code path khác nhau: nếu đoạn code ta đang test gọi một hàm khác chúng ta cần test nó sẽ hoạt động như thế nào nếu có lỗi.
  * Stubs có thể đơn giản hóa việc testing code bất đồng bộ.
* Mock: nên được sử dụng chủ yếu khi dùng stub nhưng cần xác mình nhiều hành vi cụ thể hơn trên đó.
### 1.2.6 Understand code coverage (e.g nyc) <br>
Code coverage là xác định xem có bao nhiêu code đã được test. Nó được tính theo công thức: <br>
```Code Coverage = (Number of lines of code exercised)/(Total Number of lines of code) * 100%```
### 1.2.7 Understand HTTP mocking (e.g nock) <br>
HTTP mocking tạo một server ảo để có thể kiểm tra từng request có reponse về theo đúng yêu cầu hay không.
## 1.3 Understand disadvantage of React alone <br>
- Truyền props từ component cha xuống component con và từ component con lên component cha rất phức tạp nếu ứng dụng có nhiều tầng component.
## 1.4 Flux
### 1.4.1 Understand Flux architecture <br>
Flux là một kiến trúc được Facebook đưa ra và được đưa vào React. Dữ liệu luôn chỉ di chuyển theo một chiều duy nhất, khi có dữ liệu mới luồng sẽ bắt đầu lại từ đầu: <br>
 ![alt text](https://cdn-images-1.medium.com/max/800/1*lZM0yU9ExEMd7DggVxXkxA.png)
* Actions - Làm nhiệm vụ truyền dẫn dữ liệu tới Dispatcher 
* Dispatcher - Nhận thông tin từ Actions, truyền tải dữ liệu tới các nơi đã đăng ký nhận thông tin.
* Stores - Là nơi lưu trữ trạng thái và các logic của hệ thống, đây chính là nơi sẽ đăng ký nhận dữ liệu với Dispatcher.
* Views chính là thành phần làm nhiệm vụ hiển thị nội dung ứng dụng
### 1.4.2 Understand Universal Data Flow <br>
Flux giúp làm việc với các component dễ dàng hơn thông qua luồng dữ liệu một chiều (Unidirectional Data Flow).
![alt text](https://cdn-images-1.medium.com/max/800/1*lZM0yU9ExEMd7DggVxXkxA.png)
  * Views chính là thành phần làm nhiệm vụ hiển thị nội dung ứng dụng. 
  * Khi người dùng tương tác với ứng dụng(click button, nhập dữ liệu...) làm thay đổi state của ứng dụng, view sẽ thông qua action gửi thông tin tới dispatcher.
  * Sau khi nhận được thông tin từ Action, Dispatcher làm nhiệm vụ gửi nội dung nhận được tới các Store đăng ký lắng nghe sự kiện thay đổi từ trước đó.
  * Store sau khi nhận thông tin, tiến hành cập nhật lại state.
  * Sau đó view hiển thị lại nội dung.
### 1.4.3 Understand Action, Dispatcher, Store, View
* Action: 1 action được hiểu là mỗi sự kiện làm thay đổi trạng thái của ứng dụng và sẽ tạo ra một object action tương ứng với type và payload của action đó sau đó nó sẽ được chuyển tới Dispatcher.
* Dispatcher: có nhiệm vụ nhận action payload từ action và gửi nó tới các callback đã được đăng kí trước.
* Store: là nơi chứa các trạng thái, logic của ứng dụng. Store có chứa các method callback đã được đăng ký với Dispatcher.
* View: nhận input data từ người dùng cũng như lắng nghe các thay đổi từ Store để hiển thị kết quả, trạng thái của ứng dụng.
## 1.5 Redux
### 1.5.1 Understand Redux (https://redux.js.org/) <br>
Redux là thư viện được thiết kế dựa trên kiến trúc Flux giúp quản lí state của ứng dụng dễ dàng hơn. Ví dụ như project của chúng ta có nhiều component và việc truyền dữ liệu qua lại giữa các component sẽ rất phức tạp vì vậy Redux đưa ra một giải pháp là các state được lưu trữ tại một điểm duy nhất - gọi là Store. <br>
Redux có 3 nguyên tắc như sau:
* Single source of truth: State của toàn bộ ứng dụng được lưu trong trong 1 store duy nhất là 1 Object mô hình tree.
* State is read-only: Chỉ có 1 cách duy nhất để thay đổi state đó là tạo ra một action.
* Changes are made with pure functions: Để chỉ rõ state tree được thay đổi bởi 1 action bạn phải viết pure reducers.
### 1.5.2 Understand Action, Reducers, Store, Data Flow <br>
Redux có 4 thành phần chính: 
* Action: Là nơi mang các thông tin dùng để gửi từ ứng dụng đến Store. Các thông tin này là 1 object có 2 thuộc tính:
  - type: kiểu mô tả action.
  - payload: giá trị tham số truyền vào.
* Reducers: là nơi xác định state thay đổi như thế nào. Reducer nhận 2 tham số vào: 1 state cũ và action được gửi lên sau đó trả ra một state mới, ko làm thay đổi state cũ.
* Store:  Là nơi quản lý State, cho phép truy cập State qua getState(), update State qua dispatch(action), đăng kí listener qua subscribe(listener).
* View: Hiển thị dữ liệu được cung cấp bởi Store. <br>
Data flow: Vòng đời của 1 ứng dung Redux bao gồm 4 bước:
* Gọi store.dispatch(action): 1 action là một object mô tả những gì sẽ xảy ra.
* Redux store gọi reducer function: store sẽ gửi hai tham số là state hiện tại và action.
* Root reducer có thể kết hợp output của nhiều reducers thành một single state tree: Redux có helper function combineReducers(), giúp cho việc chia nhỏ function thành các function quản lý các nhánh của state tree.
* Redux store lưu lại toàn bộ state tree được trả về bởi root reducer: state tree mới này sẽ là trạng thái mới của ứng dụng. Mỗi một listener registered với store.subscribe(listener) sẽ được gọi. Listenter có thể gọi store.getState() để lấy current state.
### 1.5.3 Understand Async Action, Async Flow, Middleware
* Async Action: 
* Async Flow:
* Middleware
