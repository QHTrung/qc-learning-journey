# CORS (Cross-Origin Resource Sharing)

### Table of contents

- [CORS (Cross-Origin Resource Sharing)](#cors-cross-origin-resource-sharing)
  - [Table of contents](#table-of-contents)
  - [1. CORS là gì?](#1-cors-là-gì)
  - [2. Tại sao cần CORS?](#2-tại-sao-cần-cors)
  - [3. Luồng hoạt động của CORS (Cơ chế Preflight Request)](#3-luồng-hoạt-động-của-cors-cơ-chế-preflight-request)
  - [4. Header quan trọng trong CORS](#4-header-quan-trọng-trong-cors)

## 1. CORS là gì?

**CORS (Cross-Origin Resource Sharing)** là cơ chế bảo mật của trình duyệt cho phép hoặc chặn việc một website truy cập tài nguyên từ một website khác.

Ví dụ:

Frontend:

```
https://app.company.com
```

Gọi API:

```
https://api.company.com
```

Đây được gọi là **Cross-Origin Request.**

Thế nào là khác Origin? Hai URL được coi là khác Origin nếu chúng khác nhau một trong ba yếu tố:

- Giao thức (Protocol/Scheme)
- Tên miền (Domain/Host)
- Cổng (Port).

## 2. Tại sao cần CORS?

Giả sử bạn đang đăng nhập ngân hàng:

```
https://bank.com
```

Trong tab khác:

```
https://evil.com
```

Nếu không có CORS:

```
fetch("https://bank.com/account");
```

Website độc hại có thể đọc dữ liệu tài khoản của bạn.

&rarr; CORS được tạo ra để ngăn điều đó.

## 3. Luồng hoạt động của CORS (Cơ chế Preflight Request)

Khi mã JavaScript ở trang web (Client) gửi một request có nguy cơ làm thay đổi dữ liệu (như POST, PUT, DELETE) sang một Server khác Origin, Trình duyệt sẽ tự động thực hiện 2 bước:

Preflight Request: Trình duyệt tự động gửi một request "dò đường" với Method là OPTIONS lên Server để hỏi: "Origin có được phép không?"

Actual Request:

- Nếu Server phản hồi: "Được phép" $\rightarrow$ Trình duyệt mới gửi tiếp Request chính thức (POST/PUT/DELETE) đi.
- Nếu Server phản hồi: "Không" $\rightarrow$ Trình duyệt lập tức chặn đứng Request đó lại và bắn ra lỗi đỏ chót ở tab Console.

```
Access to fetch at 'https://api.test.com' from origin 'https://app.test.com' has been blocked by CORS policy
```

## 4. Header quan trọng trong CORS

**Access-Control-Allow-Origin**: Xác định những Origin nào được phép lấy dữ liệu. Nếu Server để là \* nghĩa là chấp nhận tất cả mọi nguồn (thường dùng cho API công khai). Nếu dùng cho hệ thống nội bộ, Server bắt buộc phải chỉ định rõ đích danh domain

Ví dụ:

```
Access-Control-Allow-Origin: https://app.test.com
```

> Chỉ cho phép: https://app.test.com

Cho phép tất cả:

```
Access-Control-Allow-Origin: *
```

**Access-Control-Allow-Methods**: Danh sách các hàm (POST, GET, PUT, DELETE) mà Client được phép dùng.

```
Access-Control-Allow-Methods: GET,POST,PUT,DELETE
```

**Access-Control-Allow-Headers**: Các Header tùy chỉnh (Custom Headers) mà Client được phép gửi lên (ví dụ: Authorization, Content-Type).

```
Access-Control-Allow-Headers: Content-Type, Authorization
```

**Access-Control-Allow-Credentials**: Nếu set là true, Client mới được phép gửi kèm Cookie hoặc Token bảo mật lên Server khác Origin.

```
Access-Control-Allow-Credentials: true
```

> Cho phép gửi: Cookie, Session, Authorization
