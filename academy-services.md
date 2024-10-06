## 1. Giới thiệu về đề tài

Ứng dụng này được sử dụng để hỗ trợ việc tạo và quản lý các lớp học một cách dễ dàng.
Trang web này giúp nhân viên vận hành của FA quản lý và lập lịch các lớp học, với các tính năng như sau:

- Tạo và quản lý nội dung chương trình học.
- Tạo và quản lý chương trình đào tạo.
- Lập kế hoạch và quản lý các lớp học.
- Báo cáo các lớp học theo tuần, quý.

### 1.1. Mục đích

Để cung cấp một cái nhìn tổng quan về trang web quản lý lớp học, mô tả quy trình chi tiết để tạo, bắt đầu, đóng và quản lý các lớp học bao gồm:

- Luồng business
- Tài liệu thiết kế màn hình
- Giao diện người dùng
- User story
- Các yêu cầu chức năng cụ thể cho dự án này bao gồm:
  - Xác định phạm vi mục tiêu kinh doanh, chức năng kinh doanh và các đơn vị tổ chức cần được bao gồm.
  - Xác định quy trình kinh doanh mà giải pháp phải hỗ trợ.
  - Tạo ra sự hiểu biết chung về yêu cầu chức năng cho tất cả các bên liên quan.
  - Xác định cơ sở để xác định các bài kiểm tra chấp nhận cho giải pháp nhằm xác nhận rằng những gì được cung cấp đáp ứng yêu cầu.
  - Ngoài ra, SRS cũng mô tả các yêu cầu phi chức năng, ràng buộc thiết kế và các yếu tố khác cần thiết để cung cấp một mô tả đầy đủ và toàn diện về yêu cầu cho phần mềm.

### 1.2. Phạm vi

Phạm vi của SRS này xác định các hoạt động của nhân viên vận hành của Academy trong việc quản lý và lập lịch các lớp học.

- Tạo và quản lý nội dung chương trình học.
- Tạo và quản lý chương trình đào tạo.
- Lập kế hoạch và quản lý các lớp học.
- Báo cáo các lớp học theo tuần, quý.

### 1.3. Các khái niệm chuyên môn

| Từ               | Định nghĩa                                       |
| ---------------- | ------------------------------------------------ |
| Syllabus         | Nội dung đào tạo                                 |
| Training program | Chương trình đào tạo. Được tạo từ nhiều syllabus |
| Traning class    | Lớp đào tạo. Có nhiều training program           |
| Trainer          |                                                  |
| Trainee          |                                                  |
|                  |                                                  |

### 1.x. Overview

Mục này sẽ dẫn người dùng đi đến chi tiết tổng quan để giúp người dùng nắm bắt được cách xử lý của hệ thống Academy Management nhanh chóng.

#### Feature 1: Syllabus

User Story 1: Create syllabus
User Story 2: Update syllabus

```plantuml
@startuml

!define SYLLABUS_SAVED :Syllabus saved;
!define ERROR :Error;
!define END stop

start

if (Create new?) then (Yes)
   if (Import file?) then (Yes)
      :Import from CSV file;
      :Submit Syllabus>
   else (No)
      :Create using web portal;
      :Input syllabus details;
      :Submit syllabus>
   endif
else (No)
   :Update/Clone from existing syllabus;
   :Revise data;
   :Submit syllabus>
endif
stop

partition "Submit Syllabus" {
   :Submit syllabus;
   if (Success) then (Yes)
      SYLLABUS_SAVED
   else (Error)
      ERROR
   endif
}

@enduml
```

#### Feature 2: Training program

User Story 3: Create training program
User Story 4: Update training program

```plantuml
@startuml

!define PROGRAM_SAVED :Training program saved;
!define ERROR :Error;
!define END stop

start

if (Create new?) then (Yes)
   if (Import file?) then (Yes)
      :Import from CSV file;
      :Submit Training program>
   else (No)
      :Create using web portal;
      :Input Training Program details;
      :Submit Training Program>
   endif
else (No)
   :Update/Clone from existing Training Program;
   :Revise data;
   :Submit Training Program>
endif
stop

partition "Submit Training Program" {
   :Submit Training Program;
   if (Success) then (Yes)
      PROGRAM_SAVED
   else (Error)
      ERROR
   endif
}

@enduml
```

#### Feature 3: User

#### Feature 4: Training class

User Story 5: Create training class
User Story 6: Update training class

```plantuml
@startuml

!define CLASS_SAVED :Class saved;
!define ERROR :Error;
!define END stop

start

if (Create new?) then (Yes)
   if (Import file?) then (Yes)
      :Import from CSV file;
      :Submit Class>
   else (No)
      :Create using web portal;
      :Input Class details;
      :Submit Class>
   endif
else (No)
   :Update/Clone from existing Class;
   :Revise data;
   :Submit Class>
endif
stop

partition "Submit Class" {
   :Submit Class;
   if (Success) then (Yes)
      CLASS_SAVED
   else (Error)
      ERROR
   endif
}

@enduml
```

## 2. Mô tả

### 2.1. Product Perspective

Website ứng dụng quản lý kế hoạch lớp học được dùng để tạo lớp học với chương trình đào tạo có nội dung chi tiết trong thời gian cụ thể.
Quản trị viên có thể dễ dàng điều chỉnh nội dung chương trình đào tạo với nhiều đối tượng học viên khác nhau.

### 2.2. Các chức năng của sản phẩm

**Chức năng chung**:

| STT | Chức năng                     | Phạm vi phát triển                                                |
| --- | ----------------------------- | ----------------------------------------------------------------- |
| 1.  | Upload file                   | Tải lên tài liệu đào tạo                                          |
| 2.  | Tạo đối tượng                 | Tạo bao gồm chương trình học, chương trình đào tạo, lớp học       |
| 3.  | Chỉnh sửa đối tượng           | Chỉnh sửa bao gồm chương trình học, chương trình đào tạo, lớp học |
| 4.  | Xóa đối tượng                 | Xóa bao gồm chương trình học, chương trình đào tạo, lớp học       |
| 5.  | Thay đổi trạng thái đối tượng | Trạng thái chương trình học, chương trình đào tạo, lớp học        |
| 6.  | Nhập đối tượng                | Nhập danh sách chương trình học, chương trình đào tạo, lớp học    |

**Chức năng chính**:

| Tên chức năng                    | Mô tả                                                                                                                                                                                                                                                                                                          |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Tạo syllabus                  | Dựa trên chủ đề đào tạo cụ thể, người dùng có thể tạo nội dung chi tiết của syllabus. syllabus là dữ liệu chính để tạo chương trình đào tạo.                                                                                                                                                                   |
| 2. Cập nhật syllabus             | Trong danh sách syllabus đã tạo, người dùng chọn syllabus muốn cập nhật, sau đó di chuyển đến màn hình với thông tin chi tiết liên quan. Vì syllabus là dữ liệu chính của chương trình đào tạo, hãy cẩn thận khi cập nhật nó, nó sẽ ảnh hưởng đến tất cả các chương trình sử dụng nó.                          |
| 3. Tạo chương trình đào tạo      | Chương trình đào tạo được tạo ra bằng cách kết hợp nhiều syllabus.                                                                                                                                                                                                                                             |
| 4. Cập nhật chương trình đào tạo | Cho phép người dùng cập nhật các chương trình đào tạo đã tạo.                                                                                                                                                                                                                                                  |
| 5. Tạo lớp học                   | Chương trình đào tạo là dữ liệu meta để tạo một lớp học. Tùy thuộc vào người học khác nhau, người dùng có thể dễ dàng chỉnh sửa nội dung đào tạo để tạo ra một lớp học khác nhau.                                                                                                                              |
| 6. Cập nhật lớp học              | Cho phép người dùng cập nhật lớp học đã tạo.                                                                                                                                                                                                                                                                   |
| 7. Chức năng lọc trong lịch      | Lọc theo ngày, khung thời gian, địa điểm lớp học, trạng thái lớp học                                                                                                                                                                                                                                           |
| 8. Phân bổ tính toán             | Tự động tính toán việc phân bổ syllabus                                                                                                                                                                                                                                                                        |
| 9. Mã lớp học                    | Tự động tạo mã dựa trên địa điểm lớp học, năm tạo, người tham dự, tên lớp học, số thứ tự lớp học. Định dạng: `HCM22_FR.O_DevOps_01`<br>HCM: dữ liệu từ field location<br>22: năm hiện tại của hệ thống<br>FR: dữ liệu từ field Program Content<br>O: dữ liệu từ Format type<br>01: sequence number từ 01 to 99 |

### 2.3. Đặc điểm user

Có bốn loại người dùng sử dụng hệ thống này:

- Administrator: có toàn quyền truy cập trên bất kỳ màn hình nào.
Admin có trách nhiệm bảo trì hệ thống, tham gia sửa lỗi phần mềm, triển khai và bảo trì thường xuyên, có thể tạo giáo trình, chương trình đào tạo và lớp học.

- Class admin: có thể xem lớp đào tạo để hỗ trợ setup phòng, trang thiết bị học tập, kiểm tra tình trạng giảng viên, học viên.
- Trainer: có thể tạo giáo trình (syllabus), tạo chương trình đào tạo (class).
- Trainee: là người học. Có thể:
  - xem chương trình đào tạo cụ thể
  - truy cập và tải xuống tài liệu đào tạo để nghiên cứu.

### 2.4. Constraint hệ thống

Sau đây là các giới hạn chính:

- Maximum file upload size là `40MB`.
- Web application được hỗ trợ trên trình duyệt Chrome, Edge và Firefox.

## 3. Yêu cầu chi tiết

### 3.1. Functionality

### 3.2. Non-functional requirements

| STT | Nội dung                                                                                               | Tiêu chuẩn  | Mô tả                                       |
| --- | ------------------------------------------------------------------------------------------------------ | ----------- | ------------------------------------------- |
|     | Tốc độ truy cập website nhanh, ổn định                                                                 | Hiệu quả    |                                             |
|     | Các chức năng quản lý có UI trực quan, rõ ràng. Người dùng có thể sử dụng khi chưa được đào tạo trước. | Trực quan   |                                             |
|     | System should provide reliable and relevant search results 100% of times.                              | Hiệu quả    |                                             |
|     | maximum 8s to load a page and search a result displayed within 5s.                                     | Performance |                                             |
|     | supported to import and export files in excel, doc, pdf, and attach the other website links.           |             |                                             |
|     | Supportability This allows users with high permission to update roles and permission by themselves.    | Permission  | Ứng dụng có tính năng tùy chỉnh permission. |

### 3.3. Các yêu cầu out of scope

- Quản lý ngân sách của training class
- Tích hợp hệ thống authentication bên ngoài
- App setting

## High level design

```plantuml
@startuml

skinparam dpi 100

package "Public Network" {
  actor "App User" as AppUser
  entity "Web Application" as webapp
  entity "API Gateway" as apigw

}

package "Private Network" {
  entity "Eureka Server" as E
  entity "Authentication Server" as AS
  database Database as DB

  entity "User Service" as User
  entity "Syllabus Service" as Syllabus
  entity "Program Service" as Program
  entity "Class Service" as Class
}

note top of E
  Service discovery
end note

AppUser -- webapp
webapp <--> apigw
User <--> apigw
Syllabus <--> apigw
Program <--> apigw
Class <--> apigw
Syllabus <--> DB
User <--> DB
Program <--> DB
Class <--> DB
AS <--> User
AS <--> apigw

@enduml
```

## Low level design

### Mô hình thực thể kết hợp ERD

![alt text](image-6.png)

<!-- TODO: add relationship blocks -->
```plantuml
@startchen

entity Assessment_Scheme {
}
entity Attendee_Type {
}
entity Class_Admin {
}
entity Class_Attendee_Type {
}
entity Class_Position {
}
entity Class_Syllabus_Unit {
}
entity Class_Technical_Code {
}
entity Class_Technical_Group {
}
entity Class_Training_Program {
}
entity Contact_Point {
}
entity Delivery_Type {
}
entity Fa_User {
}
entity Format_Type {
}
entity Fsu {
}
entity Fsu {
}
entity Location {
}
entity Operation {
}
entity Output_Standard {
}
entity Permission {
}
entity Position {
}
entity Program_Content {
}
entity Program_Syllabus {
}
entity Resource {
}
entity Role {
}
entity Role_Permission {
}
entity Site {
}
entity Skill {
}
entity Syllabus {
}
entity Syllabus_Day {
}
entity Syllabus_Unit {
}
entity Technical_Code {
}
entity Technical_Group {
}
entity Training_Class {
}
entity Training_Material {
}
entity Training_Program {
}
entity Training_Program_Activity {
}
entity Training_Program_Syllabus {
}
entity Unit_Chapter {
}

Assessment_Scheme -N- Syllabus
Class_Admin -N- Training_Class
Class_Syllabus_Unit -N- Location
Class_Syllabus_Unit -N- Training_Program_Syllabus
Contact_Point -N- Fsu
Fa_User -N- Fsu
Fa_User -N- Role
Location -N- Site
Permission -N- Operation
Permission -N- Resource
Program_Syllabus -N- Training_Program
Role_Permission -N- Permission
Role_Permission -N- Role
Syllabus_Day -N- Syllabus
Syllabus_Unit -N- Syllabus_Day
Training_Class -N- Class_Attendee_Type
Training_Class -N- Class_Position
Training_Class -N- Class_Training_Program
Training_Class -N- Format_Type
Training_Class -N- Fsu
Training_Class -N- Program_Content
Training_Class -N- Site
Training_Class -N- Skill
Training_Material -N- Unit_Chapter
Training_Program -N- Attendee_Type
Training_Program -N- Position
Training_Program -N- Technical_Code
Training_Program -N- Technical_Group
Training_Program_Activity -N- Class_Training_Program
Training_Program_Syllabus -N- Class_Training_Program
Unit_Chapter -N- Delivery_Type
Unit_Chapter -N- Output_Standard
Unit_Chapter -N- Syllabus_Unit

@endchen
```

### Mô hình cơ sở dữ liệu

- **Syllabus Service**

```plantuml
@startuml

skinparam dpi 100

top to bottom direction
skinparam linetype ortho

class assessment_scheme {
   assignment: double precision
   final_practice: double precision
   final: double precision
   final_theory: double precision
   gpa: double precision
   quiz: double precision
   + {static} syllabus_id: bigint
   + {static} id: bigint
}
class delivery_type {
   descriptions: varchar(255)
   icon: varchar(255)
   name: varchar(255)
   + {static} id: bigint
}
class output_standard {
   code: varchar(255)
   descriptions: varchar(255)
   name: varchar(255)
   + {static} id: bigint
}
class syllabus {
   created_by: varchar(255)
   created_date: timestamp
   is_deleted: boolean
   modified_by: varchar(255)
   modified_date: timestamp
   uuid: uuid
   ancestor: uuid
   attendee_number: integer
   code: varchar(255)
   course_objective: bytea
   days: integer
   delivery_principle: bytea
   hours: double precision
   level: varchar(255)
   name: varchar(255)
   status: varchar(255)
   technical_requirement: bytea
   version: varchar(255)
   + {static} id: bigint
}
class syllabus_day {
   created_by: varchar(255)
   created_date: timestamp
   is_deleted: boolean
   modified_by: varchar(255)
   modified_date: timestamp
   uuid: uuid
   day_no: integer
   + {static} syllabus_id: bigint
   + {static} id: bigint
}
class syllabus_unit {
   created_by: varchar(255)
   created_date: timestamp
   is_deleted: boolean
   modified_by: varchar(255)
   modified_date: timestamp
   uuid: uuid
   duration: integer
   name: varchar(255)
   unit_no: integer
   + {static} syllabus_day_id: bigint
   + {static} + id: bigint
}
class training_material {
   created_by: varchar(255)
   created_date: timestamp
   is_deleted: boolean
   modified_by: varchar(255)
   modified_date: timestamp
   uuid: uuid
   file_name: varchar(255)
   is_file: boolean
   name: varchar(255)
   url: varchar(255)
   + {static} unit_chapter_id: bigint
   + {static} id: bigint
}
class unit_chapter {
   created_by: varchar(255)
   created_date: timestamp
   is_deleted: boolean
   modified_by: varchar(255)
   modified_date: timestamp
   uuid: uuid
   chapter_no: integer
   duration: integer
   is_online: boolean
   name: varchar(255)
   + {static} delivery_type_id: bigint
   + {static} output_standard_id: bigint
   + {static} syllabus_unit_id: bigint
   + {static} id: bigint
}

assessment_scheme  -[plain]-^  syllabus          : "syllabus_id:id"
syllabus_day       -[plain]-^  syllabus          : "syllabus_id:id"
syllabus_unit      -[plain]-^  syllabus_day      : "syllabus_day_id:id"
training_material  -[plain]-^  unit_chapter      : "unit_chapter_id:id"
unit_chapter       -[plain]-^  delivery_type     : "delivery_type_id:id"
unit_chapter       -[plain]-^  output_standard   : "output_standard_id:id"
unit_chapter       -[plain]-^  syllabus_unit     : "syllabus_unit_id:id"
@enduml
```

- **User service**

```plantuml
@startuml

scale 600 width

top to bottom direction
skinparam linetype ortho

class fa_user {
   {field} created_by: uuid
   {field} created_time: timestamp
   {field} updated_by: uuid
   {field} updated_time: timestamp
   {field} uuid: uuid
   {field} address: varchar(255)
   {field} avatar: varchar(255)
   {field} birthdate: date
   {field} disabled: boolean
   {field} email: varchar(255)
   {field} expired: boolean
   {field} full_name: varchar(255)
   {field} gender: varchar(255)
   {field} locked: boolean
   {field} password: varchar(255)
   {field} site: bigint
   {field} status: varchar(255)
   {field} username: varchar(255)
   + {static} {field} fsu_id: bigint
   + {static} {field} role_id: bigint
   + {static} {field} id: bigint
}
class fsu {
   name: varchar(255)
   + {static} id: bigint
}
class operation {
   created_by: uuid
   created_time: timestamp
   updated_by: uuid
   updated_time: timestamp
   uuid: uuid
   name: varchar(255)
   + {static} id: bigint
}
class permission {
   created_by: uuid
   created_time: timestamp
   updated_by: uuid
   updated_time: timestamp
   uuid: uuid
   name: varchar(255)
   + {static} operation_id: bigint
   + {static} resource_id: bigint
   + {static} id: bigint
}
class resource {
   created_by: uuid
   created_time: timestamp
   updated_by: uuid
   updated_time: timestamp
   uuid: uuid
   name: varchar(255)
   + {static} id: bigint
}
class role {
   created_by: uuid
   created_time: timestamp
   updated_by: uuid
   updated_time: timestamp
   uuid: uuid
   name: varchar(255)
   + {static} id: bigint
}
class role_permission {
   + {static} role_id: bigint
   + {static} permission_id: bigint
}

fa_user          -[plain]-^  fsu             : "fsu_id:id"
fa_user          -[plain]-^  role            : "role_id:id"
permission       -[plain]-^  operation       : "operation_id:id"
permission       -[plain]-^  resource        : "resource_id:id"
role_permission  -[plain]-^  permission      : "permission_id:id"
role_permission  -[plain]-^  role            : "role_id:id"
@enduml
```

| Table Name | Column Name  | Constraint | Data Type    | Nullable | Description                                             |
| ---------- | ------------ | ---------- | ------------ | -------- | ------------------------------------------------------- |
| fa_user    | created_by   |            | uuid         |          | The UUID of the user who created the user entry.        |
|            | created_time |            | timestamp    |          | The timestamp when the entry was created.               |
|            | updated_by   |            | uuid         |          | The ID of the user who last updated the user entry.     |
|            | updated_time |            | timestamp    |          | The timestamp when the user entry was last updated.     |
|            | uuid         | Unique     | uuid         |          | The unique identifier of the user.                      |
|            | address      |            | varchar(255) |          | The address of the user.                                |
|            | avatar       |            | varchar(255) |          | The URL or path to the user's avatar image.             |
|            | birthdate    |            | date         |          | The birthdate of the user.                              |
|            | disabled     |            | boolean      |          | Indicates if the user is disabled or not.               |
|            | email        |            | varchar(255) |          | The email address of the user.                          |
|            | expired      |            | boolean      |          | Indicates if the user account has expired or not.       |
|            | full_name    |            | varchar(255) |          | The full name of the user.                              |
|            | gender       |            | varchar(255) |          | The gender of the user.                                 |
|            | locked       |            | boolean      |          | Indicates if the user account is locked or not.         |
|            | password     |            | varchar(255) |          | The hashed password of the user.                        |
|            | site         |            | bigint       |          | The ID of the site associated with the user.            |
|            | status       |            | varchar(255) |          | The status of the user account.                         |
|            | username     |            | varchar(255) |          | The username of the user.                               |
|            | fsu_id       |            | bigint       |          | The ID of the user's FSU (File Storage Unit).           |
|            | role_id      |            | bigint       |          | The ID of the role assigned to the user.                |
|            | id           | PK         | bigint       |          | The primary key of the user table.                      |
| fsu        | name         |            | varchar(255) |          | The name of the FSU (File Storage Unit).                |
|            | id           | PK         | bigint       |          | The primary key of the FSU table.                       |
| operation  | created_by   |            | uuid         |          | The ID of the user who created the operation.           |
|            | created_time |            | timestamp    |          | The timestamp when the operation was created.           |
|            | updated_by   |            | uuid         |          | The ID of the user who last updated the operation.      |
|            | updated_time |            | timestamp    |          | The timestamp when the operation was last updated.      |
|            | uuid         |            | uuid         |          | The unique identifier of the operation.                 |
|            | name         |            | varchar(255) |          | The name of the operation.                              |
|            | id           | PK         | bigint       |          | The primary key of the operation table.                 |
| permission | created_by   |            | uuid         |          | The ID of the user who created the permission.          |
|            | created_time |            | timestamp    |          | The timestamp when the permission was created.          |
|            | updated_by   |            | uuid         |          | The ID of the user who last updated the permission.     |
|            | updated_time |            | timestamp    |          | The timestamp when the permission was last updated.     |
|            | uuid         |            | uuid         |          | The unique identifier of the permission.                |
|            | name         |            | varchar(255) |          | The name of the permission.                             |
|            | operation_id |            | bigint       |          | The ID of the operation associated with the permission. |
|            | resource_id  |            | bigint       |          | The ID of the resource associated with the permission.  |
|            | id           | PPK        | bigint       |          | Auto generated ID.                                      |

- **Training program service**

```plantuml
@startuml

scale 800 width

top to bottom direction
skinparam linetype ortho

class attendee_type {
   description: varchar(255)
   attendee_type_name: varchar(255)
   + {static} attendee_type_id: bigint
}
class position {
   description: varchar(255)
   position_name: varchar(255)
   + {static} position_id: bigint
}
class program_syllabus {
   uuid: uuid
   + {static} training_program_id: bigint
   + {static} id: bigint
}
class technical_code {
   description: varchar(255)
   technical_code_name: varchar(255)
   + {static} technical_code_id: bigint
}
class technical_group {
   description: varchar(255)
   technical_group_name: varchar(255)
   + {static} technical_group_id: bigint
}
class training_program {
   created_by: varchar(255)
   created_date: timestamp
   updated_by: varchar(255)
   updated_date: timestamp
   uuid: uuid
   code: varchar(255)
   days: integer
   hours: integer
   issued_date: timestamp
   issued_status: varchar(255)
   name: varchar(255)
   status: integer
   + {static} attendee_id: bigint
   + {static} position_id: bigint
   + {static} technical_code_id: bigint
   + {static} technical_group_id: bigint
   + {static} id: bigint
}

program_syllabus  -[plain]-^  training_program : "training_program_id:id"
training_program  -[plain]-^  attendee_type    : "attendee_id:attendee_type_id"
training_program  -[plain]-^  position         : "position_id"
training_program  -[plain]-^  technical_code   : "technical_code_id"
training_program  -[plain]-^  technical_group  : "technical_group_id"
@enduml
```

| Tên bảng         | Tên cột              | Constraint | Kiểu dữ liệu | nullable | Mô tả                       |
| ---------------- | -------------------- | ---------- | ------------ | -------- | --------------------------- |
| attendee_type    | description          |            | varchar(255) |          | Mô tả loại người tham dự    |
|                  | attendee_type_name   |            | varchar(255) |          | Tên loại người tham dự      |
|                  | attendee_type_id     | PK         | bigint       |          | ID loại người tham dự       |
| position         | description          |            | varchar(255) |          | Mô tả vị trí                |
|                  | position_name        |            | varchar(255) |          | Tên vị trí                  |
|                  | position_id          |            | bigint       |          | ID vị trí                   |
| program_syllabus | uuid                 |            | uuid         |          | UUID chương trình đào tạo   |
|                  | training_program_id  |            | bigint       |          | ID chương trình đào tạo     |
|                  | id                   | PK         | bigint       |          | ID                          |
| technical_code   | description          |            | varchar(255) |          | Mô tả mã kỹ thuật           |
|                  | technical_code_name  |            | varchar(255) |          | Tên mã kỹ thuật             |
|                  | technical_code_id    |            | bigint       |          | ID mã kỹ thuật              |
| technical_group  | description          |            | varchar(255) |          | Mô tả nhóm kỹ thuật         |
|                  | technical_group_name |            | varchar(255) |          | Tên nhóm kỹ thuật           |
|                  | technical_group_id   | PK         | bigint       |          | ID nhóm kỹ thuật            |
| training_program | created_by           |            | varchar(255) |          | UUID User tạo               |
|                  | created_date         |            | timestamp    |          | Ngày tạo                    |
|                  | updated_by           |            | varchar(255) |          | UUID User cập nhật lần cuối |
|                  | updated_date         |            | timestamp    |          | Ngày cập nhật               |
|                  | uuid                 |            | uuid         |          | UUID chương trình đào tạo   |
|                  | code                 |            | varchar(255) |          | Mã chương trình đào tạo     |
|                  | days                 |            | integer      |          | Số ngày                     |
|                  | hours                |            | integer      |          | Số giờ                      |
|                  | issued_date          |            | timestamp    |          | Ngày phát hành              |
|                  | issued_status        |            | varchar(255) |          | Trạng thái phát hành        |
|                  | name                 |            | varchar(255) |          | Tên chương trình đào tạo    |
|                  | status               |            | integer      |          | Trạng thái                  |
|                  | attendee_id          |            | bigint       |          | ID người tham dự            |
|                  | position_id          |            | bigint       |          | ID vị trí                   |
|                  | technical_code_id    |            | bigint       |          | ID mã kỹ thuật              |
|                  | technical_group_id   |            | bigint       |          | ID nhóm kỹ thuật            |
|                  | id                   | PK         | bigint       |          | Primary Key                 |

- **Class service**

```plantuml
@startuml

scale 800 width

top to bottom direction
skinparam linetype ortho

class class_admin {
   created_by: varchar(255)
   created_date: timestamp
   updated_by: varchar(255)
   updated_date: timestamp
   uuid: uuid
   admin_uuid: uuid
   + {static} class_id: bigint
   + {static} id: bigint
}
class class_attendee_type {
   description: varchar(255)
   name: varchar(255)
   + {static} id: bigint
}
class class_position {
   name: varchar(255)
   + {static} id: bigint
}
class class_syllabus_unit {
   syllabus_unit_id: uuid
   trainer_uuid: uuid
   + {static} location_id: bigint
   + {static} training_program_syllabus_id: bigint
   + {static} id: bigint
}
class class_training_program {
   created_by: varchar(255)
   created_date: timestamp
   updated_by: varchar(255)
   updated_date: timestamp
   uuid: uuid
   days: integer
   hours: integer
   name: varchar(255)
   training_program_uuid: uuid
   + {static} id: bigint
}
class contact_point {
   content: varchar(255)
   type: varchar(255)
   + {static} fsu_id: bigint
   + {static} id: bigint
}
class format_type {
   abbreviation: varchar(255)
   name: varchar(255)
   + {static} id: bigint
}
class fsu {
   name: varchar(255)
   + {static} id: bigint
}
class location {
   address: varchar(255)
   name: varchar(255)
   site: bigint
   + {static} id: bigint
}
class program_content {
   name: varchar(255)
   + {static} id: bigint
}
class site {
   abbreviation: varchar(255)
   name: varchar(255)
   + {static} id: bigint
}
class skill {
   name: varchar(255)
   + {static} id: bigint
}
class training_class {
   created_by: varchar(255)
   created_date: timestamp
   updated_by: varchar(255)
   updated_date: timestamp
   uuid: uuid
   accepted_attendee: integer
   actual_attendee: integer
   actual_end_date: date
   actual_start_date: date
   approved_by: varchar(255)
   approved_date: timestamp
   class_status: varchar(255)
   code: varchar(255)
   duration: integer
   end_time: time
   expected_end_date: date
   expected_start_date: date
   name: varchar(255)
   planned_attendee: integer
   remark: varchar(255)
   review_by: varchar(255)
   review_date: timestamp
   slot_time: varchar(255)
   start_time: time
   university_code: varchar(255)
   + {static} attendee_level_id: bigint
   + {static} class_training_program_id: bigint
   + {static} format_type_id: bigint
   + {static} fsu_id: bigint
   + {static} position_id: bigint
   + {static} program_content_id: bigint
   site: bigint
   + {static} skill_id: bigint
   + {static} id: bigint
}
class training_program_activity {
   days: integer
   hours: integer
   sort: integer
   uuid: uuid
   + {static} class_training_program_id: bigint
   created_by: varchar(255)
   created_date: timestamp
   description: varchar(255)
   name: varchar(255)
   updated_by: varchar(255)
   updated_date: timestamp
   + {static} id: bigint
}
class training_program_syllabus {
   days: integer
   hours: integer
   sort: integer
   uuid: uuid
   + {static} class_training_program_id: bigint
   name: varchar(255)
   syllabus_uuid: uuid
   + {static} id: bigint
}

class_admin                -[plain]-^  training_class            : "class_id:id"
class_syllabus_unit        -[plain]-^  location                  : "location_id:id"
class_syllabus_unit        -[plain]-^  training_program_syllabus : "training_program_syllabus_id:id"
contact_point              -[plain]-^  fsu                       : "fsu_id:id"
location                   -[plain]-^  site                      : "site:id"
training_class             -[plain]-^  class_attendee_type       : "attendee_level_id:id"
training_class             -[plain]-^  class_position            : "position_id:id"
training_class             -[plain]-^  class_training_program    : "class_training_program_id:id"
training_class             -[plain]-^  format_type               : "format_type_id:id"
training_class             -[plain]-^  fsu                       : "fsu_id:id"
training_class             -[plain]-^  program_content           : "program_content_id:id"
training_class             -[plain]-^  site                      : "site:id"
training_class             -[plain]-^  skill                     : "skill_id:id"
training_program_activity  -[plain]-^  class_training_program    : "class_training_program_id:id"
training_program_syllabus  -[plain]-^  class_training_program    : "class_training_program_id:id"
@enduml
```

| Tên bảng               | Tên cột                      | Constraint | Kiểu dữ liệu | Nullable | Mô tả                           |
| ---------------------- | ---------------------------- | ---------- | ------------ | -------- | ------------------------------- |
| class_admin            | created_by                   |            | varchar(255) |          | UUID User tạo                   |
|                        | created_date                 |            | timestamp    |          | Ngày tạo                        |
|                        | updated_by                   |            | varchar(255) |          | UUID User cập nhật lần cuối     |
|                        | updated_date                 |            | timestamp    |          | Ngày cập nhật                   |
|                        | uuid                         |            | uuid         |          | UUID                            |
|                        | admin_uuid                   |            | uuid         |          | UUID của admin                  |
|                        | class_id                     |            | bigint       |          | ID lớp học                      |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| class_attendee_type    | description                  |            | varchar(255) |          | Mô tả loại người tham dự        |
|                        | name                         |            | varchar(255) |          | Tên loại người tham dự          |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| class_position         | name                         |            | varchar(255) |          | Tên vị trí                      |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| class_syllabus_unit    | syllabus_unit_id             |            | uuid         |          | UUID đơn vị giảng dạy           |
|                        | trainer_uuid                 |            | uuid         |          | UUID người huấn luyện           |
|                        | location_id                  |            | bigint       |          | ID địa điểm                     |
|                        | training_program_syllabus_id |            | bigint       |          | ID chương trình đào tạo         |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| class_training_program | created_by                   |            | varchar(255) |          | UUID User tạo                   |
|                        | created_date                 |            | timestamp    |          | Ngày tạo                        |
|                        | updated_by                   |            | varchar(255) |          | UUID User cập nhật lần cuối     |
|                        | updated_date                 |            | timestamp    |          | Ngày cập nhật                   |
|                        | uuid                         |            | uuid         |          | UUID                            |
|                        | days                         |            | integer      |          | Số ngày                         |
|                        | hours                        |            | integer      |          | Số giờ                          |
|                        | name                         |            | varchar(255) |          | Tên chương trình đào tạo        |
|                        | training_program_uuid        |            | uuid         |          | UUID chương trình đào tạo       |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| contact_point          | content                      |            | varchar(255) |          | Nội dung                        |
|                        | type                         |            | varchar(255) |          | Loại                            |
|                        | fsu_id                       |            | bigint       |          | ID fsu                          |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| format_type            | abbreviation                 |            | varchar(255) |          | Kiểu dạy của class              |
|                        | name                         |            | varchar(255) |          | Tên                             |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| fsu                    | name                         |            | varchar(255) |          | Tên fsu                         |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| location               | address                      |            | varchar(255) |          | Địa chỉ                         |
|                        | name                         |            | varchar(255) |          | Tên địa điểm                    |
|                        | site                         |            | bigint       |          |                                 |
|                        | id                           | PK         | bigint       |          | location ID                     |
| program_content        | name                         |            | varchar(255) |          | Tên nội dung chương trình       |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| site                   | abbreviation                 |            | varchar(255) |          | Viết tắt                        |
|                        | name                         |            | varchar(255) |          | Tên                             |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| skill                  | name                         |            | varchar(255) |          | Tên kỹ năng                     |
|                        | id                           | PK         | bigint       |          | Primary Key                     |
| training_class         | created_by                   |            | varchar(255) |          | UUID User tạo                   |
|                        | created_date                 |            | timestamp    |          | Ngày tạo                        |
|                        | updated_by                   |            | varchar(255) |          | UUID User cập nhật lần cuối     |
|                        | updated_date                 |            | timestamp    |          | Ngày cập nhật                   |
|                        | uuid                         |            | uuid         |          | UUID                            |
|                        | accepted_attendee            |            | integer      |          | Số người tham gia đã chấp nhận  |
|                        | actual_attendee              |            | integer      |          | Số người tham gia thực tế       |
|                        | actual_end_date              |            | date         |          | Ngày kết thúc thực tế           |
|                        | actual_start_date            |            | date         |          | Ngày bắt đầu thực tế            |
|                        | approved_by                  |            | varchar(255) |          | Người phê duyệt                 |
|                        | approved_date                |            | timestamp    |          | Ngày phê duyệt                  |
|                        | class_status                 |            | varchar(255) |          | Trạng thái lớp học              |
|                        | code                         |            | varchar(255) |          | Mã lớp học                      |
|                        | duration                     |            | integer      |          | Thời lượng (giờ)                |
|                        | end_time                     |            | time         |          | Thời gian kết thúc              |
|                        | expected_end_date            |            | date         |          | Ngày kết thúc dự kiến           |
|                        | expected_start_date          |            | date         |          | Ngày bắt đầu dự kiến            |
|                        | name                         |            | varchar(255) |          | Tên lớp học                     |
|                        | planned_attendee             |            | integer      |          | Số người tham gia dự kiến       |
|                        | remark                       |            | varchar(255) |          | Ghi chú                         |
|                        | review_by                    |            | varchar(255) |          | Người đánh giá                  |
|                        | review_date                  |            | timestamp    |          | Ngày đánh giá                   |
|                        | slot_time                    |            | varchar(255) |          | Thời gian mở slot               |
|                        | start_time                   |            | time         |          | Thời gian bắt đầu               |
|                        | university_code              |            | varchar(255) |          | Mã trường đại học               |
|                        | attendee_level_id            |            | bigint       |          | ID cấp độ người tham dự         |
|                        | class_training_program_id    |            | bigint       |          | ID chương trình đào tạo lớp học |
|                        | format_type_id               |            | bigint       |          |                                 |

### Đối Tượng Tham Gia Và Yêu Cầu Chức Năng

### Mô hình use case của hệ thống

```plantuml
@startuml

actor "Unauthenticated User" as UnauthenticatedUser

usecase "Forgot password" as ForgotPassword
usecase "Log in" as LogIn

UnauthenticatedUser -left-> LogIn
UnauthenticatedUser --> ForgotPassword

@enduml
```

TODO

```plantuml
@startuml

package "Authenticated User" {
   actor Trainee
   actor Trainer
   actor Admin
   actor "Super Admin" as SuperAdmin
}
package Syllabus {
   usecase "Create new syllabus" as CreateNewSyllabus
   usecase "Add existing syllabus" as AddExistingSyllabus
   usecase "Delete syllabus" as DeleteSyllabus
   usecase "Update syllabus" as UpdateSyllabus
}
package "Training Program" {
   usecase "View training program" as ViewTrainingProgram
   usecase "Training program management" as TrainingProgramManagement
   usecase "Select training program" as SelectTrainingProgram
   
   usecase "Add location for unit" as AddLocationForUnit
   usecase "Update location for unit" as UpdateLocationForUnit
   usecase "Add trainer for unit" as AddTrainerForUnit
   usecase "Update trainer for unit" as UpdateTrainerForUnit
}

package Class {
   usecase "Update Class" as UpdateClass
   usecase "Create class" as CreateClass
   usecase "Import class" as ImportClass
   usecase "Delete class" as DeleteClass
   usecase "Deactivate class" as DeactivateClass
   usecase "Class management" as ClassManagement
   usecase "View class list" as ViewClassList
   usecase "Paginate class" as PaginateClass
   usecase "Filter Class" as FilterClass
   usecase "Active class" as ActiveClass
   usecase "View class detail" as ViewClassDetail
}

usecase "Download materials" as DownloadMaterials
usecase "Logout" as Logout

Trainee --> DownloadMaterials
Trainee --> ViewTrainingProgram

TrainingProgramManagement <|.. CreateNewSyllabus
TrainingProgramManagement <|.. AddExistingSyllabus
TrainingProgramManagement <|.. DeleteSyllabus
TrainingProgramManagement <|.. UpdateSyllabus
TrainingProgramManagement <|.. AddLocationForUnit
TrainingProgramManagement <|.. UpdateLocationForUnit
TrainingProgramManagement <|.. AddTrainerForUnit
TrainingProgramManagement <|.. UpdateTrainerForUnit
TrainingProgramManagement <|.. SelectTrainingProgram

Trainer --> ViewTrainingProgram
Trainer --> TrainingProgramManagement

Admin --> ClassManagement
Admin --> UpdateClass
Admin --> CreateClass

ClassManagement <|.. ImportClass
ClassManagement <|.. DeleteClass
ClassManagement <|.. DeactivateClass

Admin --> ViewClassList

ViewClassList <|.. PaginateClass
ViewClassList <|.. FilterClass
ViewClassList <|.. ActiveClass
ViewClassList <|.. ViewClassDetail

SuperAdmin --> ViewClassList

Trainee --> Logout
Trainer --> Logout
Admin --> Logout
SuperAdmin --> Logout

@enduml
```

### Đặc tả use case

#### 3.1.1. Use Case 1: Login

| Screen on Web | Platform | Function | As a user | I want to        | So that I can          | Business rule                                                                                                                                                                                                         |
| ------------- | -------- | -------- | --------- | ---------------- | ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1             | Web      | Login    | End user  | Login to account | Access the application | khi User nhập sai thông tin đăng nhập, hệ thống hiển thị lỗi EM01 "Invalid username or password", khi nhập thiếu trường: EM02 "Required field!"<br><br>User nhập đúng thông tin đăng nhập -> System dẫn đến trang chủ |

| No  | Screen item name                                          | Type       | Attribute | Length | Display | Input | Required | Supplementary explanation                                                                                                                                                                                                                                                    |
| --- | --------------------------------------------------------- | ---------- | --------- | ------ | ------- | ----- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Enter Email                                               | Textbox    | X         | Max:40 | ○       | ○     | ○        | Need to have an email domain                                                                                                                                                                                                                                                 |
| 2   | Password                                                  | Textbox    | X         | Min:12 | ○       | ○     | ○        | Hide/Unhide Password should be password of fsoft account                                                                                                                                                                                                                     |
| 3   | Sign in                                                   | Button     | -         | -      | ○       | x     | ○        | [Ev01] Process Flow: Step 1: after inserting email address and password, user clicks Login button, system returns error message (failure) or directs user to Homepage (success). False: Display error message "Invalid username or password." True: Direct user to home page |
| 4   | Forgot password?                                          | Link       | -         | -      | ○       | x     | ○        | [Ev02] Process Flow: Step 1: Click Forgot password link, system directs user to the Forgot password page to reset password                                                                                                                                                   |
| 5   | If you don't have an account, please contact <FA@fpt.com> | Label/Link | -         | -      | ○       | x     | ○        | [Ev03] Process Flow: Step 1: If user has no account, click <FA.HCM@fsoft.com.vn> link, system will open Outlook to compose a new email. Step 2: User fills in all info and send email to <FA.HCM@fsoft.com.vn> to create a new account                                       |
| 6   | Academy Training Management                               | Label      | -         | -      | ○       | x     | ○        | System name                                                                                                                                                                                                                                                                  |

```plantuml
@startuml

scale 800 width

actor User
participant "Web App" as w
participant "Authentication Service" as as
participant "User Service" as us
database "Database" as db

User -> w : Input account credentials
w -> w : Input validation
w -> as : Forward Request
as -> us : Authenticate Request
us -> db : Fetch User by Username and password
db -> us : Return User
us -> as : Return Authenticated User
as -> w : Forward Response
w -> User : Login Response

@enduml
```

#### 3.1.2. Use Case: List Syllabus

#### 3.1.3. Use Case: Syllabus details

#### 3.1.4. Use Case: Tạo / update Syllabus

#### 3.1.5. Use case: List Training Program

#### 3.1.6. Use Case: Chi tiết Training Program

#### 3.1.7. Use case: Tạo Training Program

#### 3.1.8. Use case: List Class

#### 3.1.9. Use case: Training Class Details

#### 3.1.10. Use case: Tạo training class

#### 3.1.11. Use case: Training Calendar

#### 3.1.12. Use case: List Trainer

#### 3.1.13. Use case: Thông tin Trainer

#### 3.1.14. Use case: Thông tin Trainee

## Giao diện dành cho người dùng

### Login

