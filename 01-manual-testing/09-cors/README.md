# CORS (Cross-Origin Resource Sharing)

### Table of contents

- [CORS (Cross-Origin Resource Sharing)](#cors-cross-origin-resource-sharing)
  - [Table of contents](#table-of-contents)
  - [1. CORS là gì?](#1-cors-là-gì)
  - [2. Tại sao cần CORS?](#2-tại-sao-cần-cors)

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
