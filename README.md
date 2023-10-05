# Report

## Nội dung Lý thuyết

Tìm hiểu:
- Restful Web Service
- kiến trúc microservice và cách tìm cách áp dụng vào trong hệ thống
- công nghệ container (Docker), cách sử dụng, quản lý container và giao tiếp giữa các container
- load balancer, service discovery, API gateway, giao tiếp giữa các service, circuit breaker, distributed tracing, message queue, thu thập, quản lý và hiển thị metric, logging (observability)
- Java, Spring Framework, Spring Cloud, Spring Security, Spring Data, Hibernate ORM
- design patterns

## Nội dung Thực hành

- Phân tích & thiết kế CSDL trên PostgreSQL
- Các chức năng quản lý:

  + tạo và quản lí lớp học ngắn hạn, bao gồm chương trình đào tạo và nội dung đào tạo
  + tạo và quản lí bài học và đính kèm tài liệu học
  + tạo và quản lí người dùng (bao gồm học viên và giảng viên)

- Chức năng tìm kiếm và filter cho các bài học, khóa học, lớp học và user
- Chức năng import data có sẵn từ file CSV
- Thống kê các lớp học theo tuần, quý
- Áp dụng kiến trúc microservice: 4 service độc lập thực hiện một chức năng cụ thể
  + service quản lí bài học
  + service quản lí chương trình đào tạo
  + service quản lí lớp học
  + service quản lí thông tin người dùng

- sử dụng Eureka làm service discovery để cho các component có thể xác định chính xác địa chỉ của các service khác trong hệ thống
- Tạo authentication server để handle security logic cho toàn bộ hệ thống
- Tạo API gateway để điều phối, bảo mật và quản lý communication giữa các service
- Quản lý metric của các service bằng Prometheus để theo dõi tài nguyên sử dụng, thời gian phản hồi, phát hiện sự cố, alert,... và dùng Grafana để hiển thị các thông số một cách trực quan
- Áp dụng Zipkin cho distributed tracing để theo dõi đường đi của request qua các service, giúp phân tích và hiểu rõ hơn về quá trình xử lý, tìm kiếm và debug.
- Sử dụng Docker trong quá trình phát triển
- Áp dụng SOLID trong lập trình hướng đối tượng

# Usage

## PlantUML

Make diagrams files and build to vector/image file.

```xml
java -jar $env:PLANTUML_JAR %file%
```

## LaTex

```sh
lualatex -shell-escape -synctex=1 -interaction=nonstopmode -file-line-error -recorder  "~/report/docs/tex/c2.project.1.tex
```

with VSCode tooling: Build with recipe -> `latexmk` (lualatex) (for building `report.tex`)

