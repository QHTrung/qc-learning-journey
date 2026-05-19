# 4. Test Analysis and Design

### Table of contents

- [4. Test Analysis and Design](#4-test-analysis-and-design)
    - [Table of contents](#table-of-contents)
  - [Keywords](#keywords)
  - [4.1. Test Techniques Overview](#41-test-techniques-overview)

## Keywords

| Keyword                                   | Translate                                   |
| ----------------------------------------- | :------------------------------------------ |
| acceptance criteria                       | Tiêu chí chấp nhận                          |
| acceptance test-driven development (ATDD) | Phát triển hướng kiểm thử chấp nhận         |
| black-box test technique                  | Kỹ thuật kiểm thử hộp đen                   |
| boundary value analysis (BVA)             | Phân tích giá trị biên                      |
| branch coverage                           | Độ bao phủ nhánh                            |
| checklist-based testing                   | Kiểm thử dựa trên checklist                 |
| collaboration-based test approach         | Cách tiếp cận kiểm thử dựa trên sự cộng tác |
| coverage                                  | Độ bao phủ                                  |
| coverage item                             | Hạng mục bao phủ (hoặc Phần tử bao phủ)     |
| decision table testing                    | Kiểm thử bảng quyết định                    |
| equivalence partitioning                  | Phân vùng tương đương                       |
| error guessing                            | Đoán lỗi                                    |
| experience-based test technique           | Kỹ thuật kiểm thử dựa trên kinh nghiệm      |
| exploratory testing                       | Kiểm thử khám phá                           |
| state transition testing                  | Kiểm thử chuyển đổi trạng thái              |
| statement coverage                        | Độ bao phủ câu lệnh                         |
| test technique                            | Kỹ thuật kiểm thử                           |
| white-box test technique                  | Kỹ thuật kiểm thử hộp trắng                 |

## 4.1. Test Techniques Overview

> Tổng quan về các kỹ thuật kiểm thử

Test techniques support the tester in test analysis (what to test) and in test design (how to test). Test techniques help to develop a relatively small, but sufficient, set of test cases in a systematic way. Test techniques also help the tester to define test conditions, identify coverage items, and identify test data during the test analysis and design. Further information on test techniques can be found in the ISO/IEC/IEEE 29119-4 standard, and in (Beizer 1990, Craig 2002, Copeland 2004, Koomen 2006, Jorgensen 2014, Ammann 2016, Forgács 2019).

In this syllabus, test techniques are classified as black-box, white-box, and experience-based.

**Black-box test techniques** (also known as specification-based techniques) are based on an analysis of the specified behavior of the test object without reference to its internal structure. Therefore, the test cases are independent of how the software is implemented. Consequently, if the implementation changes, but the required behavior stays the same, then the test cases are still useful.

**White-box test techniques** (also known as structure-based techniques) are based on an analysis of the test object’s internal structure and processing. As the test cases are dependent on how the software is designed, they can only be created after the design or implementation of the test object.

**Experience-based test techniques** effectively use the knowledge and experience of testers for the design and implementation of test cases. The effectiveness of these test techniques depends heavily on the tester’s skills. Experience-based test techniques can detect defects that may be missed using the black-box test techniques and white-box test techniques. Hence, experience-based test techniques are complementary to the black-box test techniques and white-box test techniques.

> Các kỹ thuật kiểm thử hỗ trợ kiểm thử viên trong quá trình phân tích kiểm thử (kiểm thử cái gì - what to test) và thiết kế kiểm thử (kiểm thử như thế nào - how to test). Các kỹ thuật kiểm thử giúp phát triển một bộ kịch bản kiểm thử (test cases) tương đối nhỏ nhưng đầy đủ một cách có hệ thống. Các kỹ thuật kiểm thử cũng giúp kiểm thử viên xác định các điều kiện kiểm thử (test conditions), nhận diện các hạng mục bao phủ (coverage items) và xác định dữ liệu kiểm thử (test data) trong suốt quá trình phân tích và thiết kế kiểm thử. Thông tin chi tiết hơn về các kỹ thuật kiểm thử có thể được tìm thấy trong tiêu chuẩn ISO/IEC/IEEE 29119-4, và trong các tài liệu của (Beizer 1990, Craig 2002, Copeland 2004, Koomen 2006, Jorgensen 2014, Ammann 2016, Forgács 2019).
>
> Trong giáo trình này, các kỹ thuật kiểm thử được phân loại thành: hộp đen (black-box), hộp trắng (white-box) và dựa trên kinh nghiệm (experience-based).
>
> - **Kỹ thuật kiểm thử hộp đen** (Black-box test techniques - còn gọi là kỹ thuật dựa trên đặc tả / specification-based techniques): Dựa trên việc phân tích hành vi đã được đặc tả của đối tượng kiểm thử mà không cần tham chiếu đến cấu trúc bên trong của nó. Do đó, các kịch bản kiểm thử độc lập với cách phần mềm được triển khai. Hệ quả là, nếu việc triển khai thay đổi nhưng hành vi yêu cầu vẫn giữ nguyên thì các kịch bản kiểm thử đó vẫn hữu ích.
> - **Kỹ thuật kiểm thử hộp trắng** (White-box test techniques - còn gọi là kỹ thuật dựa trên cấu trúc / structure-based techniques): Dựa trên việc phân tích cấu trúc bên trong và quá trình xử lý của đối tượng kiểm thử. Vì các kịch bản kiểm thử phụ thuộc vào cách phần mềm được thiết kế, chúng chỉ có thể được tạo ra sau khi có thiết kế hoặc sự triển khai của đối tượng kiểm thử.
> - **Kỹ thuật kiểm thử dựa trên kinh nghiệm** (Experience-based test techniques): Sử dụng một cách hiệu quả kiến thức và kinh nghiệm của các kiểm thử viên để thiết kế và triển khai các kịch bản kiểm thử. Hiệu quả của các kỹ thuật kiểm thử này phụ thuộc rất nhiều vào kỹ năng của kiểm thử viên. Kỹ thuật kiểm thử dựa trên kinh nghiệm có thể phát hiện các khuyết tật (defects) mà các kỹ thuật kiểm thử hộp đen và hộp trắng có thể bỏ sót. Do đó, kỹ thuật kiểm thử dựa trên kinh nghiệm mang tính bổ khuyết cho các kỹ thuật kiểm thử hộp đen và hộp trắng.
