# HTTP và HTTPS

### Table of contents

- [HTTP và HTTPS](#http-và-https)
    - [Table of contents](#table-of-contents)
  - [1. Định nghĩa cơ bản](#1-định-nghĩa-cơ-bản)
  - [2. Bảng so sánh HTTP và HTTPS](#2-bảng-so-sánh-http-và-https)

## 1. Định nghĩa cơ bản

**HTTP (Hypertext Transfer Protocol)**: Giao thức truyền tải siêu văn bản giao tiếp giữa Client và Server. Dữ liệu truyền đi dưới dạng văn bản thuần (Plain Text), không được mã hóa.

**HTTPS (HTTP Secure)**: Là HTTP nhưng được tích hợp thêm giao thức bảo mật SSL/TLS (Secure Sockets Layer/Transport Layer Security). Dữ liệu trước khi truyền đi sẽ được mã hóa thành các ký tự vô nghĩa, tránh bị đánh cắp giữa đường (Man-in-the-middle attack).

## 2. Bảng so sánh HTTP và HTTPS

| Tiêu chí                | HTTP                                            | HTTPS                                                     |
| :---------------------- | :---------------------------------------------- | :-------------------------------------------------------- |
| **Cổng kết nối (Port)** | Mặc định là 80                                  | Mặc định là 443                                           |
| **Mức độ bảo mật**      | Không bảo mật (Dễ bị nghe lén/sniffing dữ liệu) | Bảo mật cao (Dữ liệu được mã hóa)                         |
| **Chứng chỉ**           | Không yêu cầu                                   | Yêu cầu chứng chỉ SSL/TLS (X.509)                         |
| **Tác động SEO**        | Không có ưu thế                                 | Được Google ưu tiên xếp hạng cao hơn                      |
| **Chi phí**             | Miễn phí                                        | Thường tốn phí mua SSL (hoặc dùng Let's Encrypt miễn phí) |
| **Phù hợp với**         | Các trang tin tức, blog đọc thông tin thuần túy | Các trang đăng nhập, thương mại điện tử, cổng thanh toán  |
| **Url**                 | http://                                         | https://                                                  |
