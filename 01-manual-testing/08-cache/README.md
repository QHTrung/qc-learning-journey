# Cache

### Table of contents

- [Cache](#cache)
  - [Table of contents](#table-of-contents)
  - [1. Cache là gì?](#1-cache-là-gì)
  - [2. Phân loại Cache](#2-phân-loại-cache)
    - [2.1 Browser Cache](#21-browser-cache)
    - [2.2 Server Cache (Backend)](#22-server-cache-backend)
    - [2.3 CDN Cache (Mạng lưới)](#23-cdn-cache-mạng-lưới)
  - [3. Cache Hit, Cache Miss và TTL](#3-cache-hit-cache-miss-và-ttl)
  - [4. Cache-Control Header](#4-cache-control-header)
  - [5. ETag (Entity Tag)](#5-etag-entity-tag)

## 1. Cache là gì?

Cache là một chủ đề cực kỳ quan trọng với QA vì rất nhiều bug "khó hiểu" thực chất xuất phát từ cache.

Cache là kỹ thuật lưu trữ tạm thời các dữ liệu thường xuyên được sử dụng (như hình ảnh, file CSS/JS, kết quả truy vấn database) vào một bộ nhớ tốc độ cao.

**Mục đích**: Giúp tăng tốc độ tải trang, giảm tải cho Server và tiết kiệm băng thông mạng. Thay vì mỗi lần đều phải chạy vào tận Server/Database để lấy dữ liệu, hệ thống sẽ lấy ngay từ bộ nhớ Cache.

## 2. Phân loại Cache

### 2.1 Browser Cache

Vị trí lưu trữ: Ngay trên trình duyệt của người dùng.

Dữ liệu thường lưu: File tĩnh: .css, .js, logo, hình ảnh sản phẩm.

Tác động đối với QC: Khi Dev vừa fix bug giao diện/logic JS, QC vào test mà vẫn thấy lỗi cũ $\rightarrow$ Do trình duyệt đang ăn cache cũ, cần

- Hard Reload (Ctrl + F5 / Cmd + Shift + R / Ctrl + Shift + R).
- Disable Cache: F12 &rarr; Network &rarr; Disable Cache

### 2.2 Server Cache (Backend)

Vị trí lưu trữ: Trên máy chủ ứng dụng (sử dụng Redis, Memcached).

Dữ liệu thường lưu: Kết quả các câu lệnh SQL phức tạp, danh mục sản phẩm ít thay đổi.

Tác động đối với QC: Dev báo đã sửa data dưới DB, nhưng trên giao diện vẫn thấy data cũ $\rightarrow$ Server chưa clear cache.

### 2.3 CDN Cache (Mạng lưới)

Vị trí lưu trữ: Các máy chủ trung gian đặt ở nhiều quốc gia (Cloudflare, Akamai).

Dữ liệu thường lưu: Toàn bộ nội dung tĩnh của trang web để phân phối nhanh theo vị trí địa lý.

Tác động đối với QC: Thường gặp lỗi khi deploy phiên bản mới lên môi trường Production nhưng CDN chưa kịp cập nhật.

## 3. Cache Hit, Cache Miss và TTL

Cache Hit: Trình duyệt yêu cầu một tài nguyên (ví dụ: logo.png) $\rightarrow$ Tài nguyên đó đã có sẵn trong bộ nhớ đệm $\rightarrow$ Trình duyệt lấy ra dùng ngay lập tức, không cần gửi request lên Server. (Tốc độ tải bằng 0ms, hiển thị trong tab Network là from disk cache hoặc from memory cache).

Cache Miss: Trình duyệt tìm tài nguyên trong bộ nhớ đệm nhưng không thấy (hoặc đã quá hạn) $\rightarrow$ Bắt buộc phải gửi request lên Server để tải lại từ đầu. (Status Code trả về là 200 OK).

Cache Invalidation / Clearing: Hành động xóa dữ liệu cũ trong cache để nạp dữ liệu mới.

TTL (Time-To-Live): Khoảng thời gian (tuổi thọ) mà dữ liệu được phép tồn tại trong bộ nhớ Cache kể từ lúc được nạp vào. Khi hết thời gian TTL, dữ liệu sẽ bị coi là "stale" (hết hạn/cũ) và lần gọi tiếp theo sẽ dẫn đến Cache Miss.

Ví dụ:

> **TTL = 5 phút**
> 10:00 Cache tạo
> 10:03 Dùng cache
> 10:05 Cache hết hạn
> 10:06 Query lại DB

## 4. Cache-Control Header

Đây là HTTP Header nằm trong cả Request và Response do Server định nghĩa để cấu hình cho Trình duyệt biết cách thức và thời gian được phép lưu cache của tài nguyên đó.

Các giá trị Cache-Control phổ biến mà QA cần check trong tab Network &rarr; Headers:

- **public**: Tài nguyên có thể được cache bởi bất kỳ bên nào (cả Trình duyệt của user và các máy chủ trung gian CDN).

- **private**: Tài nguyên chỉ được cache ở Trình duyệt của cá nhân người dùng đó, cấm các máy chủ trung gian CDN lưu lại (Thường dùng cho trang cá nhân, thông tin tài khoản).

- **max-age= `<seconds>`**: Định nghĩa thời gian TTL bằng giây. Ví dụ: max-age=31536000 nghĩa là cho phép trình duyệt cache file này trong vòng 1 năm.

- **no-cache**: Trình duyệt vẫn có thể lưu cache, nhưng bắt buộc phải gửi request lên Server để xác thực xem file đó đã thay đổi chưa trước khi đem ra dùng (kết hợp với ETag).

- **no-store**: Cấm tuyệt đối! Không được phép lưu cache tài nguyên này dưới bất kỳ hình thức nào. Mỗi lần gọi là một lần tải mới hoàn toàn (Thường dùng cho dữ liệu thanh toán ngân hàng, thông tin cực kỳ nhạy cảm).

Ví dụ:

```
Cache-Control: no-cache
```

## 5. ETag (Entity Tag)

ETag là một chuỗi ký tự định danh duy nhất (giống như một dấu vân tay hoặc mã hash) đại diện cho một phiên bản cụ thể của tài nguyên trên Server.

Cơ chế hoạt động:

1. Lần đầu tiên tải file: Server trả về file kèm theo một Header tên là ETag: "v123". Trình duyệt sẽ lưu file này và cả mã ETag vào bộ nhớ.
   ```
   ETag: "v123"
   ```
2. Lần tải tiếp theo (Khi Cache đã hết hạn max-age hoặc có cấu hình no-cache): Trình duyệt không tải lại ngay mà gửi một request lên Server kèm theo Header If-None-Match: "v123" để hỏi: "File này có gì mới không?".
   ```
   If-None-Match: "v123"
   ```
3. Server kiểm tra:
   - Nếu file CHƯA thay đổi: Server trả về Status Code 304 Not Modified (Không có nội dung truyền về). Trình duyệt lập tức lấy file cũ trong cache ra dùng $\rightarrow$ Tiết kiệm băng thông tối đa.
   - Nếu file ĐÃ thay đổi: Server thấy mã hash mới (ví dụ là "v124"), Server sẽ trả về Status Code 200 OK kèm theo nội dung file mới và mã ETag mới.
