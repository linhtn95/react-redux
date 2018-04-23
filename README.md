# 1 Concept
## 1.1 API Security
### 1.1.1 Understand Authentication vs Authorization (https://blog.restcase.com/restful-api-authentication-basics/)
* Authentication: là xác thực thông tin của một kết nối. Quá trình này bao gồm gửi các thông tin từ client lên server dưới dạng text thường hoặc đã được mã hóa bằng một giao thức xác thực. Nói cách khác là authentication chỉ ra bạn là ai.
* Authorization: là kiểm tra xem một kết nối có được phép không. Authorization được thực hiện sau khi Authentication thành công. Nói một cách khác là authorization chỉ ra rằng bạn được phép làm gì. <br/>
Ví dụ khi người dùng đăng nhập vào một hệ thống thì username và password mà gửi dùng gửi lên là quá trình authentication. Sau khi authentication thành công(username và password đúng) thì hệ thống sẽ kiểm tra xem user này có thể làm được gì trong hệ thống, chẳng hạn user chỉ có thêm xem thông tin mà không được chỉnh sửa hay xóa thông tin. Quá trình này gọi là authorization.
## 1.2 Testing
### 1.2.1 Understand TDD, BDD: https://codeutopia.net/blog/2015/03/01/unit-testing-tdd-and-bdd/
* 
