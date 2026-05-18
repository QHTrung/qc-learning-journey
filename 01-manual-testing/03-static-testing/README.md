# 3. Static Testing

> Kiểm thử tĩnh

### Table of contents

- [3. Static Testing](#3-static-testing)
  - [Table of contents](#table-of-contents)
  - [Keywords](#keywords)
  - [3.1 Static Testing Basics](#31-static-testing-basics)
    - [3.1.1 Work Products Examinable by Static Testing](#311-work-products-examinable-by-static-testing)
    - [3.1.2. Value of Static Testing](#312-value-of-static-testing)
    - [3.1.3. Differences between Static Testing and Dynamic Testing](#313-differences-between-static-testing-and-dynamic-testing)

## Keywords

| Keyword          |                             Translate                             |
| ---------------- | :---------------------------------------------------------------: |
| anomaly          |               Bất thường (hoặc Dấu hiệu bất thường)               |
| dynamic testing  |                           Kiểm thử động                           |
| formal review    |       Duyệt tài liệu chính thức (hoặc Đánh giá chính thức)        |
| informal review  | Duyệt tài liệu không chính thức (hoặc Đánh giá không chính thức)  |
| Inspection       |               Kiểm tra chuyên sâu (hoặc Thanh tra)                |
| review           |              Duyệt tài liệu (hoặc Đánh giá tài liệu)              |
| static analysis  |                          Phân tích tĩnh                           |
| static testing   |                           Kiểm thử tĩnh                           |
| technical review |                         Đánh giá kỹ thuật                         |
| walkthrough      | Hướng dẫn sơ bộ (hoặc Đọc kiểm duyệt qua / Xem lướt qua cấu trúc) |

## 3.1 Static Testing Basics

> Khái niệm cơ bản về kiểm thử tĩnh

In contrast to dynamic testing, in static testing the software under test does not need to be executed. Code, process specification, system architecture specification or other work products are evaluated through manual examination (e.g., reviews) or with the help of a tool (e.g., static analysis). Test objectives include improving quality, detecting defects and assessing characteristics like readability, completeness, correctness, testability and consistency. Static testing can be applied for both verification and validation.

Testers, business representatives (Product Owner, business analyst etc.) and developers work together during example mappings, collaborative user story writing and backlog refinement sessions to ensure that user stories and related work products meet defined criteria, e.g., the Definition of Ready (see section 5.1.3). Review techniques can be applied to ensure user stories are complete and understandable and include testable acceptance criteria. By asking the right questions, testers explore, challenge and help improve the proposed user stories.

Static analysis can identify problems prior to dynamic testing while often requiring less effort, since no test cases are required, and tools (see chapter 6) are typically used. Static analysis is often incorporated into CI frameworks (see section 2.1.4). While largely used to detect specific code defects, static analysis is also used to evaluate maintainability and security. Spelling checkers and readability tools are other examples of static analysis tools.

> Trái ngược với kiểm thử động (dynamic testing), trong kiểm thử tĩnh (static testing), phần mềm đang được kiểm thử không cần phải khởi chạy. Mã nguồn, đặc tả quy trình, đặc tả kiến trúc hệ thống hoặc các sản phẩm công việc (work products) khác được đánh giá thông qua việc kiểm tra thủ công (ví dụ: duyệt tài liệu / reviews) hoặc với sự hỗ trợ của công cụ (ví dụ: phân tích tĩnh / static analysis). Các mục tiêu kiểm thử bao gồm nâng cao chất lượng, phát hiện khuyết tật (defects) và đánh giá các đặc tính như tính dễ đọc, tính đầy đủ, tính chính xác, tính khả kiểm (testability) và tính nhất quán. Kiểm thử tĩnh có thể được áp dụng cho cả quá trình kiểm tra xác nhận (verification) và xác nhận giá trị (validation).
>
> Các kiểm thử viên (testers), đại diện kinh doanh (Product Owner, chuyên viên phân tích nghiệp vụ / business analyst, v.v.) và các lập trình viên (developers) làm việc cùng nhau trong các buổi thiết lập bản đồ ví dụ (example mappings), cùng nhau viết câu chuyện người dùng (collaborative user story writing) và các buổi tinh chỉnh phân mục tồn đọng (backlog refinement sessions) nhằm đảm bảo rằng các câu chuyện người dùng (user stories) và các sản phẩm công việc liên quan đáp ứng được các tiêu chí đã xác định, ví dụ: Tiêu chí sẵn sàng (Definition of Ready - xem mục 5.1.3). Các kỹ thuật duyệt tài liệu (review techniques) có thể được áp dụng để đảm bảo các câu chuyện người dùng được đầy đủ, dễ hiểu và bao gồm các tiêu chí chấp nhận (acceptance criteria) có thể kiểm thử được. Bằng cách đặt các câu hỏi chính xác, các kiểm thử viên có thể khám phá, phản biện và giúp cải thiện các câu chuyện người dùng được đề xuất.
>
> Phân tích tĩnh (static analysis) có thể nhận diện các vấn đề trước khi tiến hành kiểm thử động, đồng thời thường đòi hỏi ít công sức hơn do không yêu cầu các kịch bản kiểm thử (test cases) và thường sử dụng các công cụ chuyên dụng (xem chương 6). Phân tích tĩnh thường được tích hợp vào các khung tích hợp liên tục (CI frameworks - xem mục 2.1.4). Mặc dù phần lớn được sử dụng để phát hiện các khuyết tật mã nguồn cụ thể, phân tích tĩnh cũng được sử dụng để đánh giá tính khả bảo trì (maintainability) và tính bảo mật (security). Các công cụ kiểm tra chính tả và công cụ đánh giá độ dễ đọc là những ví dụ khác về công cụ phân tích tĩnh.

### 3.1.1 Work Products Examinable by Static Testing

> Các sản phẩm công việc có thể kiểm tra bằng Kiểm thử tĩnh

Almost any work product can be examined using static testing. Examples include requirement specification documents, source code, test plans, test cases, product backlog items, test charters, project documentation, contracts and models.

Any work product that can be read and understood can be the subject of a review. However, for static analysis, work products need a structure against which they can be checked (e.g., models, code or text with a formal syntax).

Work products that are not appropriate for static testing include those that are difficult to interpret by human beings and that should not be analyzed by tools (e.g., 3rd party executable code due to legal reasons).

> Hầu như bất kỳ sản phẩm công việc (work product) nào cũng có thể được kiểm tra bằng cách sử dụng kiểm thử tĩnh. Các ví dụ bao gồm tài liệu đặc tả yêu cầu, mã nguồn, kế hoạch kiểm thử (test plans), kịch bản kiểm thử (test cases), các hạng mục trong phân mục tồn đọng sản phẩm (product backlog items), hiến chương kiểm thử (test charters), tài liệu dự án, hợp đồng và các mô hình.
>
> Bất kỳ sản phẩm công việc nào có thể đọc và hiểu được đều có thể trở thành đối tượng của một buổi duyệt tài liệu (review). Tuy nhiên, đối với phân tích tĩnh (static analysis), các sản phẩm công việc cần phải có một cấu trúc cụ thể để dựa vào đó tiến hành kiểm tra (ví dụ: các mô hình, mã nguồn hoặc văn bản có cú pháp chính thức).
>
> Các sản phẩm công việc không phù hợp cho kiểm thử tĩnh bao gồm những sản phẩm khó diễn giải bởi con người và không nên phân tích bằng các công cụ (ví dụ: mã nguồn thực thi của bên thứ ba vì các lý do pháp lý).

### 3.1.2. Value of Static Testing

> Giá trị của Kiểm thử tĩnh

Static testing can detect defects in the earliest phases of the SDLC, fulfilling the principle of early testing (see section 1.3). It can also identify defects which cannot be detected by dynamic testing (e.g., unreachable code, design patterns not implemented as desired, defects in non-executable work products).

Static testing provides the ability to evaluate the quality of, and to build confidence in work products. By verifying the documented requirements, the stakeholders can also make sure that these requirements describe their actual needs. Since static testing can be performed early in the SDLC, a shared understanding can be created among the involved stakeholders. Communication will also be improved between the involved stakeholders. For this reason, it is recommended to involve a wide variety of stakeholders in static testing.

Even though reviews can be costly to implement, the overall project costs are usually much lower than when no reviews are performed because less time and effort needs to be spent on fixing defects later in the project.

Certain code defects can be detected using static analysis more efficiently than in dynamic testing, usually resulting in both fewer code defects and a lower overall development effort.

> Kiểm thử tĩnh có thể phát hiện các khuyết tật (defects) từ những giai đoạn sớm nhất của vòng đời phát triển phần mềm (SDLC), đáp ứng nguyên lý kiểm thử sớm (xem mục 1.3). Nó cũng có thể nhận diện các khuyết tật mà kiểm thử động không thể phát hiện được (ví dụ: mã nguồn không bao giờ được thực thi/unreachable code, các mẫu thiết kế không được triển khai như mong muốn, hoặc các khuyết tật trong các sản phẩm công việc không thể thực thi).
>
> Kiểm thử tĩnh mang lại khả năng đánh giá chất lượng và tạo dựng niềm tin vào các sản phẩm công việc. Bằng cách kiểm tra xác nhận (verifying) các yêu cầu đã được tài liệu hóa, các bên liên quan (stakeholders) cũng có thể đảm bảo rằng các yêu cầu này mô tả đúng nhu cầu thực tế của họ. Vì kiểm thử tĩnh có thể được thực hiện sớm trong SDLC, một sự hiểu biết chung (shared understanding) có thể được thiết lập giữa các bên liên quan tham gia vào dự án. Giao tiếp giữa các bên liên quan cũng sẽ được cải thiện. Vì lý do này, việc thu hút sự tham gia của nhiều nhóm bên liên quan khác nhau vào kiểm thử tĩnh là rất được khuyến khích.
>
> Mặc dù việc triển khai các buổi duyệt tài liệu (reviews) có thể tốn kém, nhưng tổng chi phí dự án thường thấp hơn nhiều so với khi không thực hiện duyệt tài liệu, bởi vì sẽ tốn ít thời gian và công sức hơn cho việc sửa các khuyết tật ở giai đoạn muộn của dự án.
>
> Một số khuyết tật mã nguồn nhất định có thể được phát hiện bằng cách sử dụng phân tích tĩnh một cách hiệu quả hơn so với kiểm thử động, điều này thường giúp giảm bớt các khuyết tật mã nguồn lẫn giảm thiểu tổng công sức phát triển phần mềm.

### 3.1.3. Differences between Static Testing and Dynamic Testing

> Sự khác biệt giữa kiểm thử tĩnh và kiểm thử động

Static testing and dynamic testing practices complement each other. They have similar objectives, such as supporting the detection of defects in work products (see section 1.1.1), but there are also some differences, such as:

- Static testing and dynamic testing (with analysis of failures) can both lead to the detection of defects, however there are some defect types that can only be found by either static or dynamic testing.
- Static testing finds defects directly, while dynamic testing causes failures from which the associated defects are determined through subsequent analysis
- Static testing may more easily detect defects that lay on paths through the code that are rarely executed or hard to reach using dynamic testing
- Static testing can be applied to non-executable work products, while dynamic testing can only be applied to executable work products
- Static testing can be used to measure quality characteristics that are not dependent on executing code (e.g., maintainability), while dynamic testing can be used to measure quality characteristics that are dependent on executing code (e.g., performance efficiency)

Typical defects that are easier and/or cheaper to find through static testing include:

- Defects in requirements (e.g., inconsistencies, ambiguities, contradictions, omissions, inaccuracies, duplications)
- Design defects (e.g., inefficient database structures, poor modularization)
- Certain types of coding defects (e.g., variables with undefined values, undeclared variables, unreachable or duplicated code, excessive code complexity)
- Deviations from standards (e.g., lack of adherence to naming conventions in coding standards)
- Incorrect interface specifications (e.g., mismatched number, type or order of parameters)
- Specific types of security vulnerabilities (e.g., buffer overflows)
- Gaps or inaccuracies in test basis coverage (e.g., missing tests for an acceptance criterion)

> Các hoạt động kiểm thử tĩnh và kiểm thử động bổ khuyết cho nhau. Chúng có các mục tiêu tương tự nhau, chẳng hạn như hỗ trợ phát hiện các khuyết tật (defects) trong các sản phẩm công việc (xem mục 1.1.1), nhưng cũng có một số điểm khác biệt như:
>
> - Kiểm thử tĩnh và kiểm thử động (bằng cách phân tích các lỗi hỏng / failures) đều có thể dẫn đến việc phát hiện khuyết tật, tuy nhiên có một số loại khuyết tật chỉ có thể được tìm thấy bằng kiểm thử tĩnh hoặc chỉ bằng kiểm thử động.
> - Kiểm thử tĩnh tìm ra trực tiếp các khuyết tật, trong khi kiểm thử động làm xuất hiện các lỗi hỏng, từ đó các khuyết tật liên quan mới được xác định thông qua việc phân tích sau đó.
> - Kiểm thử tĩnh có thể dễ dàng phát hiện hơn các khuyết tật nằm trên các đường dẫn mã nguồn (code paths) hiếm khi được thực thi hoặc khó tiếp cận nếu sử dụng kiểm thử động.
> - Kiểm thử tĩnh có thể được áp dụng cho các sản phẩm công việc không thể thực thi, trong khi kiểm thử động chỉ có thể áp dụng cho các sản phẩm công việc có thể thực thi.
> - Kiểm thử tĩnh có thể được sử dụng để đo lường các đặc tính chất lượng không phụ thuộc vào việc thực thi mã nguồn (ví dụ: tính khả bảo trì / maintainability), trong khi kiểm thử động có thể được sử dụng để đo lường các đặc tính chất lượng phụ thuộc vào việc thực thi mã nguồn (ví dụ: hiệu quả năng suất / performance efficiency).
>
> Các khuyết tật điển hình dễ tìm thấy hơn và/hoặc tiết kiệm chi phí hơn khi tìm qua kiểm thử tĩnh bao gồm:
>
> - Các khuyết tật trong yêu cầu (ví dụ: tính không nhất quán, tính mơ hồ, tính mâu thuẫn, tính thiếu sót, tính không chính xác, tính trùng lặp).
> - Các khuyết tật thiết kế (ví dụ: cấu trúc cơ sở dữ liệu kém hiệu quả, phân mô-đun tồi).
> - Một số loại khuyết tật lập trình nhất định (ví dụ: các biến có giá trị chưa xác định, các biến chưa được khai báo, mã nguồn không bao giờ được thực thi hoặc bị trùng lặp, độ phức tạp của mã nguồn quá mức).
> - Các sai lệch so với tiêu chuẩn (ví dụ: thiếu tuân thủ các quy ước đặt tên trong tiêu chuẩn lập trình).
> - Các đặc tả giao diện không chính xác (ví dụ: sai lệch về số lượng, kiểu dữ liệu hoặc thứ tự của các tham số).
> - Các loại lỗ hổng bảo mật đặc thù (ví dụ: tràn bộ đệm / buffer overflows).
> - Các lỗ hổng hoặc sự không chính xác trong phạm vi bao phủ của cơ sở kiểm thử (ví dụ: thiếu các bài kiểm thử cho một tiêu chí chấp nhận).
