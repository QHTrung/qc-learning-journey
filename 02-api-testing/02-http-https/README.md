# HTTP và HTTPS

### Table of contents

- [HTTP và HTTPS](#http-và-https)
  - [Table of contents](#table-of-contents)
  - [1. Định nghĩa cơ bản](#1-định-nghĩa-cơ-bản)
  - [2. Bảng so sánh HTTP và HTTPS](#2-bảng-so-sánh-http-và-https)
  - [3. Cách thức hoạt động của HTTPS (Quá trình TLS Handshake)](#3-cách-thức-hoạt-động-của-https-quá-trình-tls-handshake)

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

## 3. Cách thức hoạt động của HTTPS (Quá trình TLS Handshake)

Bản chất của Handshake là: Dùng Mã hóa bất đối xứng (chậm nhưng an toàn để trao đổi chìa khóa) $\rightarrow$ thống nhất ra một Khóa đối xứng (nhanh hơn) để mã hóa toàn bộ dữ liệu về sau.

Để thiết lập một kết nối HTTPS an toàn, Client và Server phải thực hiện "bắt tay" (Handshake) qua các bước:

**Bước 1**: Lời chào từ Khách (Client Hello)
Client gửi một thông điệp mở đầu đến Server, bao gồm:

- Phiên bản TLS mà Client hỗ trợ (ví dụ: TLS 1.2, TLS 1.3).

- Danh sách các thuật toán mã hóa mà Client có thể dùng (Cipher Suites).

- Một chuỗi ký tự ngẫu nhiên được tạo ra từ phía khách (Client Random).

**Bước 2**: Phản hồi từ Chủ (Server Hello & Certificate)
Server chọn các cấu hình phù hợp nhất từ danh sách của Client và gửi lại:

- Phiên bản TLS và Cipher Suite được chọn để sử dụng.
- Một chuỗi ký tự ngẫu nhiên từ phía chủ (Server Random).
- Chứng chỉ SSL/TLS của Server (chứa Public Key - Khóa công khai của Server).

**Bước 3:** Xác thực Chứng chỉ (Certificate Verification)

- Client tiến hành kiểm tra chứng chỉ của Server với các tổ chức chứng thực (CA) uy tín được tích hợp sẵn trên thiết bị/trình duyệt.

- Nếu chứng chỉ hợp pháp, Client mới tin tưởng đi tiếp sang Bước 4. Nếu không hợp lệ, trình duyệt sẽ lập tức hiện cảnh báo đỏ "Kết nối của bạn không an toàn".

**Bước 4**: Tạo Khóa Bí Mật Tạm Thời (Pre-Master Secret)

- Client tự tạo ra một chuỗi ngẫu nhiên thứ ba gọi là Pre-Master Secret.

- Client lấy Public Key (nhận từ Server ở Bước 2) để mã hóa chuỗi Pre-Master Secret này, sau đó gửi sang cho Server.

> Lưu ý: Lúc này, chỉ có duy nhất Private Key (Khóa bí mật) nằm an toàn trên Server mới có thể giải mã được gói tin này. Kẻ xấu bắt trộm gói tin trên đường truyền cũng bất lực.

**Bước 5**: Tạo Khóa Phiên Chính Thức (Session Key)

- Server dùng Private Key của mình để giải mã và lấy ra chuỗi Pre-Master Secret.

- Lúc này, cả Client và Server đều đã có đủ 3 nguyên liệu ngẫu nhiên: Client Random, Server Random, và Pre-Master Secret.

- Cả hai bên độc lập dùng thuật toán để tự tính toán ra một chìa khóa chung duy nhất, gọi là Session Key (Khóa đối xứng dùng cho phiên làm việc này).

**Bước 6**: Hoàn tất và Đóng gói (Finished)

- Client gửi một thông điệp được mã hóa bằng Session Key vừa tạo để báo: "Tôi đã sẵn sàng, từ giờ tôi sẽ mã hóa bằng khóa này".

- Server nhận được, giải mã thành công và gửi lại một thông điệp tương tự xác nhận: "Tôi cũng đã sẵn sàng".

Kết quả: Quá trình Handshake kết thúc thành công. Kể từ giây phút này, mọi dữ liệu (HTTP Request/Response) truyền qua lại đều được mã hóa cực nhanh bằng Session Key chung.

![TLS Handshake](../images/TLS%20handshake.png)
