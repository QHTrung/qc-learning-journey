# Cookie

## 1. Cookie là gì?

Cookie là những tệp văn bản nhỏ (text files) được Server (máy chủ) tạo ra và gửi về để lưu trữ tại Browser (trình duyệt) của người dùng.

Bản chất: Vì giao thức HTTP là Stateless (không lưu lại trạng thái, mỗi Request là hoàn toàn độc lập), nên Cookie sinh ra để giúp Server "nhớ" được trình duyệt này là ai trong các lần gửi request tiếp theo.

Khi trình duyệt gửi request đến server, cookie sẽ được gửi kèm trong HTTP Header.

Ví dụ:

Server trả về:

`Set-Cookie: session_id=abc123; Path=/; HttpOnly`

Trình duyệt lưu lại và gửi trong request tiếp theo:

`Cookie: session_id=abc123`

## 2. Cookie hoạt động như thế nào?

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

## 3. Cookie được lưu ở đâu?

Đều lưu cookie trong bộ nhớ trình duyệt hoặc file local.

QA có thể xem bằng:

F12 &rarr; Application &rarr; Storage &rarr; Cookies

Ví dụ:
|Name| Value|
|:--|--|
|session_id |abc123|
|language |vi|
|theme |dark|

## 4. Các thành phần chính của một Cookie

Khi F12 (DevTools) &rarr; tab Application &rarr; Cookies, cần chú ý các thuộc tính sau:

- Name & Value: Tên và giá trị của cookie (thường được mã hóa chuỗi).
- Domain & Path: Phạm vi hợp lệ mà cookie được phép gửi đi.
- Expires / Max-Age: Thời gian sống của cookie. Nếu không có, nó là Session Cookie (xóa khi đóng trình duyệt).
- HttpOnly: Thuộc tính bảo mật cực kỳ quan trọng. Nếu HttpOnly = True, bên thứ ba không thể dùng JavaScript (document.cookie) để hack và lấy cookie này $\rightarrow$ Chống lỗi bảo mật XSS.
- Secure: Nếu Secure = True, cookie chỉ được gửi qua giao thức mã hóa bảo mật HTTPS.
- SameSite: Kiểm soát việc cookie có được gửi kèm trong các request từ trang web khác hay không (Strict, Lax, hoặc None) $\rightarrow$ Chống lỗi bảo mật CSRF.

## 5. Phân loại Cookie

| Loại Cookie        | Đặc điểm                                                                     | Ví dụ                                                                                  |
| :----------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Session Cookie     | Lưu tạm thời ở bộ nhớ RAM, tự mất khi đóng trình duyệt hoặc hết hạn session. | Giữ trạng thái đăng nhập, giỏ hàng hiện tại khi đang mua sắm.                          |
| Persistent Cookie  | Lưu cứng vào ổ đĩa, có ngày hết hạn cụ thể, tắt trình duyệt bật lại vẫn còn. | Tính năng "Ghi nhớ đăng nhập" (Remember me), cấu hình ngôn ngữ hiển thị.               |
| First-party Cookie | Do chính Domain của trang web đang truy cập tạo ra.                          | Cookie do chính shopee.vn tạo khi lướt Shopee.                                         |
| Third-party Cookie | Do một Domain khác (bên thứ 3) nhúng vào trang web hiện tại tạo ra.          | Các cookie quảng cáo của Google, Facebook Tracker dùng để theo dõi hành vi người dùng. |
