# Spring-Boot-Document
Document how to create Spring Boot project

### CÁC BƯỚC LÀM SPRING BOOT
0) thêm các dependency cần thiết trong pom.xml
1) Tạo database trong Mysql hay gì đó (rảnh tạo luôn table)
2) Tạo cấu trúc các file package (2 và 3 có thể đổi chỗ)
- src/main/java/pagkage chính (tất cả bên dưới là package)
+ controller
+ model
+ repository
+ exception
+ service 
+ serviceimpl (serviceimp có thể nằm chung với pagkage service cũng ok khỏi tạo pagkage)
3) Cấu hình database trong application.properties (username, password,...)
-> Chạy ứng dụng xem kết nối thành công chưa
4) Tạo class enity trong package model ở trên (vd như Student, Employee,...)
- Các annotation cần có @Entity @Table @Id @Column @GeneratedValue
6) Tạo cái repository interface (trong pagkage repository)
- Các annotation cần có @Repository
vd như ra cái public interface EmployeeRepository extends JpaRepository<Employee,Long>{}
=> Employee là tên class cái thứ 4) vừa tạo, Long là thuộc tính ID của cái class đó (private long ID)
6) Package Exception (trường hợp ko tìm thấy data) (ko cần thiết)
Annotaton cái class này là @ResponseStatus
7) Tạo interface trong pagkage service
8) Tạo class trong pagkage serviceimpl implement cái interface ở trên (nhớ implements để kế thừa)
- Các annotation cần có @Service @Autowired @Override
10) Tạo controller trong pagkage controller
- Các annotation cần có  @Controller @Autowired @RequestMapping

### CÁC LỖI THƯỜNG GẶP 
- Thiếu các annotation
- Phần "@{value1}" trong file html (thường nằm ở button) thì cái value1 bằng với cái value trong controller (chỗ @RequestMapping), mỗi cái value phải riêng biệt ko được trùng tên
- ví dụ 2 cái dưới, cái đầu sẽ gọi ở controller, cái 2 chỉ chuyển hướng trong file (nên làm cái đầu)
<a th:href="@{/addEmployee}" class="btn btn-success">Add Employee</a>
<a href="/" class="btn btn-success">User</a>   

### PROJECT LỚN
https://openplanning.net/10683/tao-ung-dung-web-ban-hang-voi-spring-boot-hibernate

