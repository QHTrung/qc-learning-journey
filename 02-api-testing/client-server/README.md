# Mô hình Client - Server

### Table of contents

- [Mô hình Client - Server](#mô-hình-client---server)
  - [Table of contents](#table-of-contents)
  - [1. Khái niệm](#1-khái-niệm)
  - [2. Thành phần của mô hình Client - Server](#2-thành-phần-của-mô-hình-client---server)
    - [2.1 Client](#21-client)
    - [2.2 Server](#22-server)
  - [3. Quy trình hoạt động](#3-quy-trình-hoạt-động)
  - [4. Kiến trúc Client - Server](#4-kiến-trúc-client---server)
    - [4.1 Kiến trúc 2-Tier (Two-Tier Architecture)](#41-kiến-trúc-2-tier-two-tier-architecture)
    - [4.2 Kiến trúc 3-Tier (Three-Tier Architecture)](#42-kiến-trúc-3-tier-three-tier-architecture)

## 1. Khái niệm

Mô hình Client - Server là kiến trúc mạng trong đó một hoặc nhiều Client (máy khách) gửi yêu cầu (request) đến Server (máy chủ) để truy cập dữ liệu hoặc sử dụng dịch vụ. Server sẽ xử lý yêu cầu và trả về kết quả (response) cho Client.

![Client - Server Image](../images/client-server.png)

Ví dụ:
Trình duyệt Chrome mở website.
Ứng dụng Mobile Banking truy vấn số dư tài khoản.
Ứng dụng thương mại điện tử lấy danh sách sản phẩm.

## 2. Thành phần của mô hình Client - Server

### 2.1 Client

Client là thiết bị hoặc ứng dụng gửi yêu cầu đến Server.

Ví dụ:

Trình duyệt web (Chrome, Firefox)
Ứng dụng mobile
Desktop application
API Client (Postman)

Chức năng:

- Hiển thị giao diện cho người dùng.
- Thu thập dữ liệu đầu vào.
- Gửi request đến Server.
- Nhận và hiển thị response.

### 2.2 Server

Server là hệ thống tiếp nhận và xử lý yêu cầu từ Client.

Ví dụ:

Web Server
Application Server
Database Server

Chức năng:

- Xử lý nghiệp vụ.
- Xác thực người dùng.
- Truy xuất dữ liệu.
- Trả kết quả về Client.

## 3. Quy trình hoạt động

Ví dụ người dùng đăng nhập vào hệ thống:

1. User nhập username/password
2. Client gửi request Login
3. Server nhận request
4. Server kiểm tra thông tin
5. Server trả kết quả
6. Client hiển thị thành công/thất bại

![Client Server Workflow](../images/client-server%20workflow.png)

## 4. Kiến trúc Client - Server

### 4.1 Kiến trúc 2-Tier (Two-Tier Architecture)

Cấu trúc: Chỉ gồm 2 lớp: Client <-> Database Server. Client kết nối và tương tác trực tiếp với Cơ sở dữ liệu.

Đặc điểm: Toàn bộ logic nghiệp vụ (Business Logic) được cài đặt ngay tại ứng dụng phía Client.

Hạn chế: Kém bảo mật (vì Client giữ thông tin kết nối DB) và khó mở rộng khi số lượng người dùng tăng cao.

### 4.2 Kiến trúc 3-Tier (Three-Tier Architecture)

Đây là kiến trúc phổ biến nhất hiện nay, tách biệt hoàn toàn giao diện, logic và dữ liệu thành 3 lớp độc lập:

| Lớp (Tier) | Tên gọi                            | Chức năng chính                                                                             | Thành phần tiêu biểu                               |
| :--------- | :--------------------------------- | :------------------------------------------------------------------------------------------ | :------------------------------------------------- |
| **Tier 1** | Presentation Tier (Giao diện)      | Hiển thị thông tin và nhận tương tác từ người dùng. Không xử lý logic nặng.                 | Web Browser, Mobile App (iOS/Android).             |
| **Tier 2** | Application Tier (Logic nghiệp vụ) | Trung tâm xử lý. Nhận yêu cầu từ Tier 1, thực thi logic, tính toán và giao tiếp với Tier 3. | API Server (Java, Python, .NET), Payment Services. |
| **Tier 3** | Data Tier (Dữ liệu)                | Lưu trữ, quản lý và bảo mật toàn bộ dữ liệu của hệ thống.                                   | Database (MySQL, Oracle, PostgreSQL).              |
