# 4. Test Analysis and Design

### Table of contents

- [4. Test Analysis and Design](#4-test-analysis-and-design)
    - [Table of contents](#table-of-contents)
  - [Keywords](#keywords)
  - [4.1. Test Techniques Overview](#41-test-techniques-overview)
  - [4.2. Black-Box Test Techniques](#42-black-box-test-techniques)
    - [4.2.1. Equivalence Partitioning](#421-equivalence-partitioning)
    - [4.2.2 Boundary Value Analysis](#422-boundary-value-analysis)

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

## 4.2. Black-Box Test Techniques

> Các kỹ thuật kiểm thử hộp đen

### 4.2.1. Equivalence Partitioning

> Phân vùng tương đương

Equivalence Partitioning (EP) divides data into partitions (known as equivalence partitions) based on the expectation that all the elements of a given partition are to be processed in the same way by the test object. The theory behind this technique is that if a test case, that tests one value from an equivalence partition, detects a defect, this defect should also be detected by test cases that test any other value from the same partition. Therefore, one test for each partition is sufficient.

Equivalence partitions can be identified for any data element related to the test object, including inputs, outputs, configuration items, internal values, time-related values, and interface parameters. The partitions may be continuous or discrete, ordered or unordered, finite or infinite. The partitions must not overlap and must be non-empty sets.

For simple test items, EP can be easy, but in practice, understanding how the test object will treat different values is often complicated. Therefore, partitioning should be done with care.

A partition containing valid values is called a valid partition. A partition containing invalid values is called an invalid partition. The definitions of valid and invalid values may vary among teams and organizations. For example, valid values may be interpreted as those that should be processed by the test object or as those for which the specification defines their processing. Invalid values may be interpreted as those that should be ignored or rejected by the test object or as those for which no processing is defined in the test object specification.

In EP, the coverage items are the equivalence partitions. To achieve 100% coverage with this test technique, test cases must exercise all identified partitions (including invalid partitions) by covering each partition at least once. Coverage is measured as the number of partitions exercised by at least one test case, divided by the total number of identified partitions, and is expressed as a percentage.

Many test items include multiple sets of partitions (e.g., test items with more than one input parameter), which means that a test case will cover partitions from different sets of partitions. The simplest coverage criterion in the case of multiple sets of partitions is called Each Choice coverage (Ammann 2016). Each Choice coverage requires test cases to exercise each partition from each set of partitions at least once. Each Choice coverage does not take into account combinations of partitions.

> Phân vùng tương đương (EP) phân chia dữ liệu thành các phân vùng (được gọi là các vùng tương đương) dựa trên kỳ vọng rằng tất cả các phần tử trong một phân vùng cho trước đều được đối tượng kiểm thử xử lý theo cùng một cách. Cơ sở lý thuyết của kỹ thuật này là: nếu một kịch bản kiểm thử (test case) kiểm tra một giá trị đại diện trong một vùng tương đương và phát hiện ra khuyết tật (defect), thì khuyết tật này cũng sẽ được tìm thấy bởi các kịch bản kiểm thử kiểm tra bất kỳ giá trị nào khác trong cùng phân vùng đó. Do đó, chỉ cần một bài kiểm thử cho mỗi phân vùng là đủ.
>
> Các vùng tương đương có thể được xác định cho bất kỳ phần tử dữ liệu nào liên quan đến đối tượng kiểm thử, bao gồm đầu vào (inputs), đầu ra (outputs), các hạng mục cấu hình (configuration items), các giá trị nội bộ (internal values), các giá trị liên quan đến thời gian và các tham số giao diện (interface parameters). Các phân vùng có thể là liên tục hoặc rời rạc, được sắp xếp hoặc không được sắp xếp, hữu hạn hoặc vô hạn. Các phân vùng phải không được trùng lặp (overlap) và phải là các tập hợp khác rỗng.
>
> Đối với các mục kiểm thử đơn giản, việc áp dụng EP có thể dễ dàng, nhưng trong thực tế, việc thấu hiểu cách đối tượng kiểm thử xử lý các giá trị khác nhau thường rất phức tạp. Vì vậy, việc phân vùng cần phải được thực hiện một cách cẩn trọng.
>
> - Một phân vùng chứa các giá trị hợp lệ được gọi là phân vùng hợp lệ (valid partition).
> - Một phân vùng chứa các giá trị không hợp lệ được gọi là phân vùng không hợp lệ (invalid partition).
>
> Định nghĩa về giá trị hợp lệ và không hợp lệ có thể khác nhau giữa các đội ngũ và tổ chức. Ví dụ, các giá trị hợp lệ có thể được hiểu là những giá trị sẽ được đối tượng kiểm thử xử lý, hoặc là những giá trị đã được tài liệu đặc tả định nghĩa rõ quy trình xử lý. Các giá trị không hợp lệ có thể được hiểu là những giá trị sẽ bị đối tượng kiểm thử bỏ qua hoặc từ chối, hoặc là những giá trị không được định nghĩa quy trình xử lý trong tài liệu đặc tả của đối tượng kiểm thử.
>
> Trong kỹ thuật EP, các hạng mục bao phủ (coverage items) chính là các vùng tương đương. Để đạt được độ bao phủ 100% (100% coverage) với kỹ thuật kiểm thử này, các kịch bản kiểm thử phải thực thi qua tất cả các phân vùng đã được xác định (bao gồm cả các phân vùng không hợp lệ) bằng cách bao phủ mỗi phân vùng ít nhất một lần. Độ bao phủ được đo bằng số lượng phân vùng được thực thi bởi ít nhất một kịch bản kiểm thử, chia cho tổng số phân vùng đã được xác định, và được thể hiện dưới dạng phần trăm.
>
> Nhiều mục kiểm thử bao gồm nhiều tập hợp phân vùng khác nhau (ví dụ: các mục kiểm thử có nhiều hơn một tham số đầu vào), điều này có nghĩa là một kịch bản kiểm thử sẽ bao phủ các phân vùng từ các tập hợp phân vùng khác nhau. Tiêu chí bao phủ đơn giản nhất trong trường hợp có nhiều tập hợp phân vùng được gọi là độ bao phủ Mỗi lựa chọn (Each Choice coverage) (Ammann 2016). Độ bao phủ Mỗi lựa chọn yêu cầu các kịch bản kiểm thử phải thực thi mỗi phân vùng từ mỗi tập hợp phân vùng ít nhất một lần. Độ bao phủ Mỗi lựa chọn không tính đến các tổ hợp (combinations) của các phân vùng.

> Bài toán ví dụ: Tính năng Thanh toán bằng Mã QR (QR Pay)
> Giả sử hệ thống cổng thanh toán có một tính năng nhận diện giao dịch QR Pay từ Merchant với hai tham số đầu vào cần kiểm thử:
>
> - Số tiền thanh toán (Amount): Quy định từ 10,000 VND đến 50,000,000 VND cho một giao dịch.
> - Loại tài khoản (Account Type): Hệ thống chỉ chấp nhận hai loại tài khoản là Cá nhân (Personal) và Doanh nghiệp (Business).
>
> Giải bài toán bằng Equivalence Partitioning:
> **Bước 1: Xác định phân vùng tương đương**
> Dựa trên quy định nghiệp vụ (Specification), chia dữ liệu thành các tập hợp phân vùng hợp lệ và không hợp lệ cho từng tham số đầu vào:
>
> - Tập hợp 1: Tham số Amount
>   - Phân vùng 1: (Invalid) < 10,000 -> 5,000
>   - Phân vùng 2: (Valid) [10,000 - 50,000,000] -> 500,000
>   - Phân vùng 3: (Invalid) > 50,000,000 -> 60,000,000
> - Tập hợp 2: Tham số Account Type
>   - Phân vùng 4: (Valid) Personal
>   - Phân vùng 5: (Valid) Business
>   - Phân vùng 6: (Invalid) Null
>
> **Bước 2: Thiết kế Test Cases theo độ bao phủ "Mỗi lựa chọn" (Each Choice Coverage)**
> Để đạt độ bao phủ 100% Each Choice, quy định yêu cầu mỗi phân vùng của mỗi tập hợp phải được xuất hiện ít nhất một lần trong bộ test case, không bắt buộc phải kiểm thử mọi tổ hợp trùng lặp giữa chúng.
> |TC|Amount|Account Type|Phân vùng được bao phủ|Expected Result|
> |---|---|---|---|:---|
> |TC_01| 500,000 VND| Personal| Bao phủ Phân vùng 2 và Phân vùng 4| Giao dịch thành công (Hợp lệ)|
> |TC_02| 5,000 VND| Business |Bao phủ Phân vùng 1 và Phân vùng 5| Hệ thống từ chối - Lỗi số tiền không hợp lệ|
> |TC_03| 60,000,000 VND|Null|Bao phủ Phân vùng 3 và Phân vùng 6|Hệ thống từ chối - Lỗi dữ liệu không hợp lệ|
>
> **Phân tích độ bao phủ:**
> Có thể thấy, chỉ với 3 kịch bản kiểm thử, tất cả 6 phân vùng được xác định (từ Phân vùng 1 đến Phân vùng 6) đều đã được thực thi ít nhất một lần. Bộ test này đã đạt 100% Each Choice Coverage, giúp tiết kiệm tối đa thời gian thay vì phải tạo ra 9 tổ hợp ($3 \times 3$) nếu phối hợp kiểm thử toàn bộ.

### 4.2.2 Boundary Value Analysis

> Phân tích giá trị biên

**Boundary Value Analysis (BVA)** is a test technique based on exercising the boundaries of equivalence partitions. Therefore, BVA can only be used for ordered partitions. The minimum and maximum values of a partition are its boundary values. In the case of BVA, if two elements belong to the same partition, all elements between them must also belong to that partition.

BVA focuses on the boundary values of the partitions because developers are more likely to make errors with these boundary values. Typical defects found by BVA are located where implemented boundaries are misplaced to positions above or below their intended positions or are omitted altogether.

This syllabus covers two versions of the BVA: 2-value and 3-value BVA. They differ in terms of coverage items per boundary that need to be exercised to achieve 100% coverage.

In 2-value BVA (Craig 2002, Myers 2011), for each boundary value there are two coverage items: this boundary value and its closest neighbor belonging to the adjacent partition. To achieve 100% coverage with 2-value BVA, test cases must exercise all coverage items, i.e., all identified boundary values. Coverage is measured as the number of boundary values that were exercised, divided by the total number of identified boundary values, and is expressed as a percentage.

In 3-value BVA (Koomen 2006, O’Regan 2019), for each boundary value there are three coverage items: this boundary value and both its neighbors. Therefore, in 3-value BVA some of the coverage items may not be boundary values. To achieve 100% coverage with 3-value BVA, test cases must exercise all coverage items, i.e., identified boundary values and their neighbors. Coverage is measured as the number of boundary values and their neighbors exercised, divided by the total number of identified boundary values and their neighbors, and is expressed as a percentage.

3-value BVA is more rigorous than 2-value BVA as it may detect defects overlooked by 2-value BVA. For example, if the decision “if (x ≤ 10) …” is incorrectly implemented as “if (x = 10) …”, no test data derived from the 2-value BVA (x = 10, x = 11) can detect the defect. However, x = 9, derived from the 3-value BVA, is likely to detect it.

> **Phân tích giá trị biên (BVA)** là một kỹ thuật kiểm thử dựa trên việc thực thi các giá trị biên của các vùng tương đương. Do đó, BVA chỉ có thể được sử dụng cho các phân vùng được sắp xếp (ordered partitions). Các giá trị nhỏ nhất và lớn nhất của một phân vùng chính là các giá trị biên của nó. Trong trường hợp của BVA, nếu hai phần tử thuộc cùng một phân vùng, thì tất cả các phần tử nằm giữa chúng cũng phải thuộc về phân vùng đó.
>
> BVA tập trung vào các giá trị biên của các phân vùng vì các lập trình viên có nhiều khả năng mắc lỗi tại các giá trị biên này hơn. Các khuyết tật điển hình được tìm thấy bởi BVA thường nằm ở nơi mà các biên được triển khai bị đặt sai vị trí (cao hơn hoặc thấp hơn vị trí mong muốn) hoặc bị bỏ sót hoàn toàn.
>
> Giáo trình này bao gồm hai phiên bản của BVA: BVA 2 giá trị (2-value BVA) và BVA 3 giá trị (3-value BVA). Chúng khác nhau về số lượng hạng mục bao phủ (coverage items) trên mỗi biên cần phải thực thi để đạt được độ bao phủ 100%.
>
> Trong BVA 2 giá trị (Craig 2002, Myers 2011): Đối với mỗi giá trị biên sẽ có hai hạng mục bao phủ: chính giá trị biên đó và người láng giềng gần nhất của nó thuộc về phân vùng kế cận. Để đạt độ bao phủ 100% với BVA 2 giá trị, các kịch bản kiểm thử phải thực thi tất cả các hạng mục bao phủ, tức là tất cả các giá trị biên đã được xác định. Độ bao phủ được đo bằng số lượng giá trị biên đã được thực thi, chia cho tổng số giá trị biên đã được xác định, và được thể hiện dưới dạng phần trăm.
>
> Trong BVA 3 giá trị (Koomen 2006, O’Regan 2019): Đối với mỗi giá trị biên sẽ có ba hạng mục bao phủ: chính giá trị biên đó và cả hai người láng giềng của nó. Do đó, trong BVA 3 giá trị, một số hạng mục bao phủ có thể không phải là giá trị biên. Để đạt độ bao phủ 100% với BVA 3 giá trị, các kịch bản kiểm thử phải thực thi tất cả các hạng mục bao phủ, tức là các giá trị biên đã xác định và các láng giềng của chúng. Độ bao phủ được đo bằng số lượng giá trị biên và các láng giềng của chúng đã được thực thi, chia cho tổng số giá trị biên và các láng giềng đã được xác định, và được thể hiện dưới dạng phần trăm.
>
> BVA 3 giá trị nghiêm ngặt hơn BVA 2 giá trị vì nó có thể phát hiện các khuyết tật bị BVA 2 giá trị bỏ sót. Ví dụ, nếu câu lệnh điều kiện if (x <= 10) ... bị triển khai sai thành if (x == 10) ..., không có dữ liệu kiểm thử nào được tạo ra từ BVA 2 giá trị ($x = 10$, $x = 11$) có thể phát hiện được khuyết tật này. Tuy nhiên, giá trị $x = 9$ được tạo ra từ BVA 3 giá trị có nhiều khả năng sẽ phát hiện được nó.
