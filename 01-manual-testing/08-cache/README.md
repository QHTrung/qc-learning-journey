# Cache

### Table of contents

- [Cache](#cache)
  - [Table of contents](#table-of-contents)
  - [1. Cache là gì?](#1-cache-là-gì)
  - [2. Phân loại Cache](#2-phân-loại-cache)
    - [2.1 Browser Cache](#21-browser-cache)
    - [2.2 Server Cache (Backend)](#22-server-cache-backend)
    - [2.3 CDN Cache (Mạng lưới)](#23-cdn-cache-mạng-lưới)

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
