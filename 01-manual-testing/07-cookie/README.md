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
