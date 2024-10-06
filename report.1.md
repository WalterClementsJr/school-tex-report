# Báo cáo đợt 1

Sinh viên: Nguyễn Tân Thiên N18DCCN214

Đề tài: Hệ thống Learning Management System

## Planning

### Tuần 1: 24/6 - 30/6

- Xác định phạm vi, mục tiêu và đối tượng sử dụng của ứng dụng.
- Tiến hành nghiên cứu nghiệp vụ quản lý learning management system.
- Xác định các tính năng và chức năng chính.
- Tạo kế hoạch dự án chi tiết, bao gồm các mốc quan trọng và sản phẩm bàn giao.

### Tuần 2: 1/7 - 7/7

- Phát triển ý tưởng thiết kế UI và hoàn thiện giao diện cho ứng dụng.
- Thiết kế CSDL

### Tuần 3: 8/7 - 15/7

- Thiết lập môi trường development
- Triển khai các chức năng cốt lõi của ứng dụng
- Tích hợp các dịch vụ phụ trợ và API cần thiết
- Triển khai xác thực người dùng
- Tích hợp giao diện và backend

### Tuần 4: 16/7 - 21/7

- Tiến hành test và fix bug cho ứng dụng
- Phân tích từ người dùng để cải thiện khả năng sử dụng và hiệu suất của ứng dụng

### Tuần 5: 22/7 - 28/7 và Tuần 6 29/7 - 4/8

- Hoàn thiện phát triển các chức năng
- Tiến hành vòng kiểm tra và sửa lỗi cuối cùng
- Viết cuốn báo cáo
- Chuẩn bị bài thuyết trình giới thiệu các tính năng, quá trình phát triển và thành tựu của ứng dụng
- Gửi ứng dụng đã hoàn thành và tài liệu đi kèm

## Mindmap

```plantuml
@startmindmap

scale 800 width

<style>
node {
    HorizontalAlignment center
    MaximumWidth 100
}
</style>

+ Academy management system
++ Lý thuyết
+++ Restful Web service
+++ microservice
++++ load balancer
++++ service discovery
++++ API gateway
++++ giao tiếp giữa các service
++++ circuit breaker
++++ distributed tracing
++++ metric
++++ logging
+++ Java
++++ Spring Framework
++++ Spring Cloud
++++ Spring Security
++++ Spring Data
+++++ Spring Data JPA
+++++ Hibernate ORM
+++ Docker
+++ design pattern
++++ dependency injection
++++ singleton
++++ factory methods

-- Thực hành

--- Chức năng

---- tạo & quản lí lớp học ngắn hạn
---- tạo & quản lí giáo trình
---- tạo & quản lí chương trình học
---- tạo & quản lí người dùng
---- upload/download tài liệu học
---- Đăng nhập
---- Đổi ảnh đại diện
---- tìm kiếm và filter cho các giáo trình, khóa học, lớp học và user
---- import data từ file CSV
---- Thống kê lớp học theo tuần, quý

--- hệ thống

---- Các service
----- PostgreSQL
----- API Gateway
----- Eureka (service discovery)
----- service quản lí người dùng
----- service quản lí giáo trình
----- service quản lí chương trình học
----- service quản lí lớp học
----- Service xác thực
----- Zipkin (distributed tracing) 
----- Prometheus & Grafana (quản lí metric)
@endmindmap
```

## UI/UX

- màn hình đăng nhập

![alt text](meta/ui.png)

- màn hình xem/chỉnh sửa thông tin người dùng

![alt text](meta/ui.png)

- màn hình quản lí danh sách người dùng

![alt text](meta/ui.png)

- màn hình quản lí tạo/chỉnh sửa thông tin người dùng

![alt text](meta/ui.png)

- màn hình danh sách giáo trình

![alt text](meta/ui.png)

- màn hình thông tin giáo trình

![alt text](meta/ui.png)

- màn hình tạo giáo trình

![alt text](meta/ui.png)
![alt text](meta/ui.png)
![alt text](meta/ui.png)

- màn hình danh sách phương thức giảng dạy

![alt text](meta/ui.png)

- màn hình tạo/chỉnh sửa phương thức giảng dạy

![alt text](meta/ui.png)

- màn hình danh sách chương trình học

![alt text](meta/ui.png)

- màn hình danh sách lớp học

![alt text](meta/ui.png)

- màn hình thông tin lớp học

![alt text](meta/ui.png)
