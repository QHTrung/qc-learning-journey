# Cookie - Session - Web Storage (Local Storage + Session Storage)

### Table of contents

- [Cookie - Session - Web Storage (Local Storage + Session Storage)](#cookie---session---web-storage-local-storage--session-storage)
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
  - [3. Web Storage](#3-web-storage)
    - [3.1 Local Storage](#31-local-storage)
    - [3.2 Session Storage](#32-session-storage)
  - [4. Bảng so sánh (COOKIE - SESSION - LOCAL STORAGE - SESSION STORAGE)](#4-bảng-so-sánh-cookie---session---local-storage---session-storage)

## 1. Cookie

### 1.1 Cookie là gì?

Cookie là những tệp văn bản nhỏ (text files) được Server (máy chủ) tạo ra và gửi về để lưu trữ tại Browser (trình duyệt) của người dùng.

Bản chất: Vì giao thức HTTP là Stateless (không lưu lại trạng thái, mỗi Request là hoàn toàn độc lập), nên Cookie sinh ra để giúp Server "nhớ" được trình duyệt này là ai trong các lần gửi request tiếp theo.

Khi trình duyệt gửi request đến server, cookie sẽ được gửi kèm trong HTTP Header.

Ví dụ:

Server trả về:

```
Set-Cookie: session_id=abc123; Path=/; HttpOnly
```

Trình duyệt lưu lại và gửi trong request tiếp theo:

```
Cookie: session_id=abc123
```

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

```
Session ID: XYZ123
```

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

```
session_id=XYZ123
```

**Bước 5**: Request tiếp theo

```
Cookie:
session_id=XYZ123
```

**Bước 6**: Server tra Session

Server nhận:

```
session_id=XYZ123
```

tra cứu:

```
XYZ123 -> User Trung
```

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

## 3. Web Storage

Web Storage là cơ chế cho phép trình duyệt lưu dữ liệu dưới dạng key-value.

Ví dụ:

```
localStorage.setItem("username", "trung");
```

hoặc:

```
sessionStorage.setItem("username", "trung");
```

QA có thể xem bằng:

F12
→ Application
→ Local Storage
→ Session Storage

**Bản chất của Web Storage (Local & Session Storage)**

Cả hai đều là các cơ chế lưu trữ dữ liệu ngay tại Client (Trình duyệt), được giới thiệu từ chuẩn HTML5 để khắc phục nhược điểm của Cookie.

- Dung lượng lớn: Lưu được từ 5MB - 10MB (trong khi Cookie chỉ lưu được tối đa 4KB).

- Hiệu năng cao: Dữ liệu lưu ở đây không tự động gửi kèm lên Server qua mỗi request giống như Cookie, giúp tiết kiệm băng thông đường truyền.

### 3.1 Local Storage

Local Storage lưu dữ liệu lâu dài trên trình duyệt.

Ví dụ:

```
localStorage.setItem("theme", "dark");
```

**Đặc điểm**

Dữ liệu vẫn tồn tại sau khi:

✅ Refresh trang

✅ Đóng tab

✅ Đóng browser

✅ Restart máy

Chỉ mất khi:

```
localStorage.clear();
```

hoặc user xóa cache/browser data.

**Ví dụ thực tế**

Remember Me hoặc Website lưu:

```
{
  "theme": "dark",
  "language": "vi"
}
```

User mở lại website sau 1 tháng:

> Theme vẫn là Dark
> Language vẫn là Tiếng Việt

### 3.2 Session Storage

Session Storage chỉ tồn tại trong một tab hoặc cửa sổ trình duyệt.

Ví dụ:

```
sessionStorage.setItem("step", "2");
```

**Đặc điểm**

Dữ liệu còn khi:

✅ Refresh

Dữ liệu mất khi:

❌ Đóng tab

❌ Đóng browser

**Ví dụ thực tế**

Form đăng ký nhiều bước được lưu trong Session Storage và khi Đóng tab thì mất data

## 4. Bảng so sánh (COOKIE - SESSION - LOCAL STORAGE - SESSION STORAGE)

| Tiêu chí                                     | Cookie                                                                                                    | Session                                                                                  | Local Storage                                                                                 | Session Storage                                                                          |
| :------------------------------------------- | :-------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------- |
| **Vị trí lưu trữ** _(Where)_                 | **Client** (Trình duyệt)                                                                                  | **Server** (RAM, DB hoặc Redis của máy chủ)                                              | **Client** (Trình duyệt)                                                                      | **Client** (Trình duyệt)                                                                 |
| **Dung lượng tối đa** _(Capacity)_           | Rất nhỏ (**~4 KB**)                                                                                       | **Không giới hạn** (Phụ thuộc vào bộ nhớ Server)                                         | Lớn (**5 MB – 10 MB** tùy trình duyệt)                                                        | Lớn (**5 MB – 10 MB** tùy trình duyệt)                                                   |
| **Thời gian sống** _(Lifespan)_              | Tùy cấu hình (Mất khi đóng tab nếu là Session Cookie, hoặc lưu đến ngày cụ thể nếu là Persistent Cookie). | Ngắn (Mất khi đăng xuất hoặc hết thời gian chờ - **Timeout**).                           | **Vĩnh viễn** (Chỉ mất khi dùng code xóa hoặc user chủ động clear cache).                     | Theo **Tab** (Mất ngay lập tức khi Trẫm **đóng tab** đó lại).                            |
| **Luồng truyền dữ liệu** _(Data Transfer)_   | **Tự động gửi kèm** lên Server qua mỗi Request HTTP $\rightarrow$ Tốn băng thông nếu lưu nhiều.           | Chỉ lưu ở Server. Chỉ có **Session ID** được gửi đi để đối chiếu.                        | **Không** tự động gửi lên Server $\rightarrow$ Tiết kiệm băng thông, tối ưu hiệu năng.        | **Không** tự động gửi lên Server $\rightarrow$ Tiết kiệm băng thông, tối ưu hiệu năng.   |
| **Phạm vi truy cập** _(Scope)_               | Mọi tab/cửa sổ mở cùng Domain.                                                                            | Mọi tab/cửa sổ mở cùng Domain (miễn là dùng chung Session ID).                           | Mọi tab/cửa sổ mở cùng Domain.                                                                | **Duy nhất trong tab đó**. Tab khác (dù cùng domain) cũng không đọc được.                |
| **Độ bảo mật** _(Security)_                  | **Trung bình.** Dễ bị tấn công XSS/CSRF nếu thiếu cấu hình bảo mật (`HttpOnly`, `Secure`).                | **Cao nhất.** Vì dữ liệu nằm hoàn toàn ở phía Server, Client chỉ giữ mã định danh.       | **Thấp.** Hacker có thể dùng JavaScript độc hại để lấy toàn bộ dữ liệu qua lỗi XSS.           | **Thấp.** Hacker có thể dùng JavaScript độc hại để lấy toàn bộ dữ liệu qua lỗi XSS.      |
| **Mục đích sử dụng chính** _(Best Use Case)_ | Lưu trữ trạng thái đăng nhập hệ thống, cấu hình ngôn ngữ, tracking quảng cáo.                             | Lưu trữ dữ liệu đăng nhập nhạy cảm, thông tin tài khoản, giỏ hàng cần xử lý nghiêm ngặt. | Lưu trữ cấu hình giao diện (Sáng/Tối), các dữ liệu cần cache lại để ứng dụng khởi động nhanh. | Lưu trữ dữ liệu tạm thời khi điền Form nhiều bước, trạng thái bộ lọc (Filter) của trang. |
