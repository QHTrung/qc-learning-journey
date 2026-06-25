# Kiến thức tổng quan về API Testing

### Table of contents

- [Kiến thức tổng quan về API Testing](#kiến-thức-tổng-quan-về-api-testing)
  - [Table of contents](#table-of-contents)
  - [1. API (Application Programming Interface)](#1-api-application-programming-interface)
  - [2. URL và Endpoint](#2-url-và-endpoint)

## 1. API (Application Programming Interface)

Giao diện lập trình ứng dụng, đóng vai trò là "cầu nối" cho phép hai hệ thống phần mềm giao tiếp và trao đổi dữ liệu với nhau một cách an toàn.

Cơ chế hoạt động: Hoạt động theo mô hình Client-Server. Client gửi yêu cầu (Request) $\rightarrow$ API tiếp nhận, kiểm tra tính hợp lệ và chuyển đến Server $\rightarrow$ Server xử lý, truy vấn Database $\rightarrow$ API nhận kết quả từ Server và trả về Client (Response).

Ví dụ: Hệ thống e-commerce của trẫm gọi API của cổng thanh toán (Payment Gateway) để tiến hành xác thực và trừ tiền khách hàng.

## 2. URL và Endpoint

Một URL của API thường được chia nhỏ thành nhiều phần để máy chủ định tuyến (routing) chính xác:

$$\text{https://} \underbrace{\text{api.pay.com}}_{\text{Domain/Host}} \text{/} \underbrace{\text{v1}}_{\text{Versioning}} \text{/} \underbrace{\text{transactions}}_{\text{Resource/Endpoint}} \underbrace{\text{?status=success\&page=2}}_{\text{Query Parameters}}$$

- Base URL (`https://api.pay.com`): Địa chỉ máy chủ lưu trữ API.

- Versioning (`/v1`): Phiên bản của API. Cực kỳ quan trọng trong kiểm thử để đảm bảo tính tương thích ngược khi hệ thống nâng cấp lên /v2.

- Endpoint (`/transactions`): Đường dẫn trỏ thẳng đến tài nguyên cụ thể.

- Query Parameters (`?status=success&page=2`): Phần nằm sau dấu `?` . Dùng để lọc, sắp xếp hoặc phân trang` dữ liệu.

Ví dụ:

![URL Image](../images/url.png)
