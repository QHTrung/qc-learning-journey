# VERIFICATION VS VALIDATION & VAI TRÒ QC

## 1. Bảng so sánh cốt lõi

| Tiêu chí            | Verification (Xác minh)                                                            |                                  Validation (Xác nhận)                                  |
| ------------------- | ---------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------: |
| Câu hỏi bản chất    | Are we building the product right? <br>(Có xây dựng sản phẩm đúng thiết kế không?) | Are we building the right product?<br>(Có xây dựng đúng sản phẩm khách hàng cần không?) |
| Trạng thái hệ thống | Kiểm thử tĩnh (Static): Không chạy code.                                           |                     Kiểm thử động (Dynamic): Có chạy code thực tế.                      |
| Mục tiêu            | Đảm bảo phần mềm tuân thủ các tài liệu đặc tả (SRS, Design).                       |              Đảm bảo phần mềm đáp ứng đúng nhu cầu thực tế của người dùng.              |
| Hoạt động chính     | Review tài liệu, Walkthrough, Inspection, Code review.                             |              Black-box testing, System testing, Integration testing, UAT.               |
| Thực hiện bởi       | QA, Dev (Peer review), QC (Review tài liệu).                                       |                       QC Engineer, Khách hàng / Người dùng cuối.                        |

## 2. Vai trò và Trách nhiệm của QC Engineer

Trong dự án phần mềm, một QC Engineer sẽ đảm nhận cả hai vai trò để tối ưu hóa chất lượng sản phẩm, nhưng với tỷ trọng khác nhau:

- **Verification** (~20% thời gian - Giai đoạn đầu): QC tham gia vào việc review tài liệu yêu cầu (SRS) và các luồng nghiệp vụ. Việc này giúp phát hiện sớm các điểm mâu thuẫn, thiếu logic trước khi Dev tiến hành viết code, giúp dự án tiết kiệm chi phí sửa lỗi.

- **Validation** (~80% thời gian - Giai đoạn sau): Đây là nhiệm vụ cốt lõi. QC trực tiếp thiết kế Test Case, thực thi kiểm thử trên hệ thống thật, phát hiện và log bug, kiểm tra luồng dữ liệu end-to-end nhằm đảm bảo phần mềm hoạt động mượt mà và chính xác.

## 3. Ví dụ thực tế (Domain Thanh toán / QR Pay)

- **Hoạt động Verification**: QC đọc tài liệu hệ thống MMS, kiểm tra xem công thức tính phí giao dịch hoặc quy trình đối soát (Reconciliation) giữa Ngân hàng và Merchant viết trong tài liệu đã đúng logic kinh doanh chưa (chưa thực hiện giao dịch).

- **Hoạt động Validation**: QC mở ứng dụng ngân hàng, thực hiện quét mã QR thật để thanh toán giao dịch 50,000 VND. Sau đó, QC kiểm tra tài khoản có bị trừ đúng số tiền, hệ thống MMS có ghi nhận trạng thái thành công và Merchant có nhận được tiền hay không.
