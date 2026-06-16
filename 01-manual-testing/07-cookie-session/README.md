# Cookie - Session

### Table of contents

- [Cookie - Session](#cookie---session)
  - [Table of contents](#table-of-contents)
  - [1. Cookie](#1-cookie)
    - [1.1 Cookie là gì?](#11-cookie-là-gì)
    - [1.2 Cookie hoạt động như thế nào?](#12-cookie-hoạt-động-như-thế-nào)
    - [1.3 Cookie được lưu ở đâu?](#13-cookie-được-lưu-ở-đâu)
    - [1.4 Các thành phần chính của một Cookie](#14-các-thành-phần-chính-của-một-cookie)
    - [1.5 Phân loại Cookie](#15-phân-loại-cookie)
  - [2. Session](#2-session)
    - [2.1 Session là gì?](#21-session-là-gì)
    - [2.2 Session hoạt động như thế nào?](#22-session-hoạt-động-như-thế-nào)
    - [2.3 Các thuộc tính quan trọng của Session](#23-các-thuộc-tính-quan-trọng-của-session)
    - [2.4 So sánh nhanh Cookie và Session](#24-so-sánh-nhanh-cookie-và-session)

## 1. Cookie

### 1.1 Cookie là gì?

Cookie là những tệp văn bản nhỏ (text files) được Server (máy chủ) tạo ra và gửi về để lưu trữ tại Browser (trình duyệt) của người dùng.

Bản chất: Vì giao thức HTTP là Stateless (không lưu lại trạng thái, mỗi Request là hoàn toàn độc lập), nên Cookie sinh ra để giúp Server "nhớ" được trình duyệt này là ai trong các lần gửi request tiếp theo.

Khi trình duyệt gửi request đến server, cookie sẽ được gửi kèm trong HTTP Header.

Ví dụ:

Server trả về:

`Set-Cookie: session_id=abc123; Path=/; HttpOnly`

Trình duyệt lưu lại và gửi trong request tiếp theo:

`Cookie: session_id=abc123`

### 1.2 Cookie hoạt động như thế nào?

**Bước 1**: User đăng nhập

Người dùng nhập:

> Username: trung
> Password: 123456

**Bước 2**: Server xác thực thành công
Server tạo:

> session_id = abc123xyz

và trả về:

> Set-Cookie: session_id=abc123xyz

**Bước 3**: Browser lưu cookie

> session_id=abc123xyz

**Bước 4**: Các request sau
Browser tự động gửi:

> Cookie: session_id=abc123xyz

Server biết đây là user đã đăng nhập.

### 1.3 Cookie được lưu ở đâu?

Đều lưu cookie trong bộ nhớ trình duyệt hoặc file local.

QA có thể xem bằng:

F12 &rarr; Application &rarr; Storage &rarr; Cookies

Ví dụ:
|Name| Value|
|:--|--|
|session_id |abc123|
|language |vi|
|theme |dark|

### 1.4 Các thành phần chính của một Cookie

Khi F12 (DevTools) &rarr; tab Application &rarr; Cookies, cần chú ý các thuộc tính sau:

- Name & Value: Tên và giá trị của cookie (thường được mã hóa chuỗi).
- Domain & Path: Phạm vi hợp lệ mà cookie được phép gửi đi.
- Expires / Max-Age: Thời gian sống của cookie. Nếu không có, nó là Session Cookie (xóa khi đóng trình duyệt).
- HttpOnly: Thuộc tính bảo mật cực kỳ quan trọng. Nếu HttpOnly = True, bên thứ ba không thể dùng JavaScript (document.cookie) để hack và lấy cookie này $\rightarrow$ Chống lỗi bảo mật XSS.
- Secure: Nếu Secure = True, cookie chỉ được gửi qua giao thức mã hóa bảo mật HTTPS.
- SameSite: Kiểm soát việc cookie có được gửi kèm trong các request từ trang web khác hay không (Strict, Lax, hoặc None) $\rightarrow$ Chống lỗi bảo mật CSRF.

### 1.5 Phân loại Cookie

| Loại Cookie        | Đặc điểm                                                                     | Ví dụ                                                                                  |
| :----------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Session Cookie     | Lưu tạm thời ở bộ nhớ RAM, tự mất khi đóng trình duyệt hoặc hết hạn session. | Giữ trạng thái đăng nhập, giỏ hàng hiện tại khi đang mua sắm.                          |
| Persistent Cookie  | Lưu cứng vào ổ đĩa, có ngày hết hạn cụ thể, tắt trình duyệt bật lại vẫn còn. | Tính năng "Ghi nhớ đăng nhập" (Remember me), cấu hình ngôn ngữ hiển thị.               |
| First-party Cookie | Do chính Domain của trang web đang truy cập tạo ra.                          | Cookie do chính shopee.vn tạo khi lướt Shopee.                                         |
| Third-party Cookie | Do một Domain khác (bên thứ 3) nhúng vào trang web hiện tại tạo ra.          | Các cookie quảng cáo của Google, Facebook Tracker dùng để theo dõi hành vi người dùng. |

## 2. Session

### 2.1 Session là gì?

Session là một phiên làm việc của người dùng trên hệ thống, tính từ lúc bắt đầu truy cập (hoặc đăng nhập) cho đến khi đăng xuất hoặc tắt ứng dụng.

Bản chất lưu trữ: Trái ngược với Cookie (lưu ở Client/Trình duyệt), dữ liệu của Session được lưu trữ tập trung ở phía Server (trong bộ nhớ RAM của server hoặc Database/Redis).

Cơ chế liên kết: Để biết Trình duyệt nào đang giữ Session nào, Server sẽ sinh ra một chuỗi mã duy nhất gọi là Session ID (hoặc JSESSIONID, PHPSESSID). Mã này được gửi về lưu tại Trình duyệt dưới dạng một Cookie bảo mật. Mỗi khi Trình duyệt gửi request tiếp theo, nó sẽ kèm theo Session ID này để Server nhận diện.

HTTP vốn là giao thức stateless (không nhớ trạng thái).

> Ví dụ:
>
> Request 1 -> Login
> Request 2 -> Xem profile
> Request 3 -> Thanh toán

Server không tự biết 3 request này đến từ cùng một người &rarr; Session được tạo ra để giải quyết vấn đề đó.

### 2.2 Session hoạt động như thế nào?

**Bước 1**: User đăng nhập

```
Username: trung
Password: 123456
```

**Bước 2**: Server xác thực thành công

Server tạo session và lưu trong bộ nhớ hoặc database.

`Session ID: XYZ123`

```
XYZ123
├── User ID: 1001
├── Name: Trung
├── Role: Merchant
└── Login Time: 10:00
```

**Bước 3**: Session ID gửi về Browser

```
Set-Cookie:
session_id=XYZ123
```

**Bước 4**: Browser lưu Cookie

`session_id=XYZ123`

**Bước 5**: Request tiếp theo

```
Cookie:
session_id=XYZ123
```

**Bước 6**: Server tra Session

Server nhận:
`session_id=XYZ123`
tra cứu:
`XYZ123 -> User Trung`

=> Xác định đây là user đã đăng nhập.

### 2.3 Các thuộc tính quan trọng của Session

- **Session ID**: Chuỗi ký tự định danh, bắt buộc phải ngẫu nhiên và có độ phức tạp cao để tránh bị hacker đoán được.

- **Session Timeout / Idle Timeout**: Thời gian tối đa một Session được phép "đứng im" (không thao tác). Nếu quá thời gian này (ví dụ 15 phút), Server sẽ tự động hủy Session và yêu cầu đăng nhập lại.

- **Absolute Timeout**: Thời gian sống tối đa của một Session kể từ lúc sinh ra, bất kể user có đang hoạt động liên tục hay không (dùng để tăng tính bảo mật).

### 2.4 So sánh nhanh Cookie và Session

| Đặc tính        | Cookie                                              | Session                                                               |
| :-------------- | --------------------------------------------------- | --------------------------------------------------------------------- |
| Vị trí lưu trữ  | Lưu tại Client (Trình duyệt).                       | Lưu tại Server.                                                       |
| Độ bảo mật      | Thấp hơn (Dễ bị user sửa đổi hoặc bị hack qua XSS). | Cao hơn (User không thể can thiệp trực tiếp vào dữ liệu trên server). |
| Dữ liệu lưu trữ | Chuỗi văn bản (Text) dung lượng nhỏ (< 4KB).        | Có thể lưu dữ liệu phức tạp (Object, Array), dung lượng lớn hơn.      |
| Thời gian sống  | Có thể lưu rất lâu (Persistent Cookie).             | Thường ngắn, mất khi đóng trình duyệt hoặc hết hạn Timeout.           |
