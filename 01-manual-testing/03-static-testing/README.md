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
  - [3.2. Feedback and Review Process](#32-feedback-and-review-process)
    - [3.2.1. Benefits of Early and Frequent Stakeholder Feedback](#321-benefits-of-early-and-frequent-stakeholder-feedback)
    - [3.2.2. Review Process Activities](#322-review-process-activities)
    - [3.2.3. Roles and Responsibilities in Reviews](#323-roles-and-responsibilities-in-reviews)
    - [3.2.4. Review Types](#324-review-types)
    - [3.2.5. Success Factors for Reviews](#325-success-factors-for-reviews)

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

## 3.2. Feedback and Review Process

> Quy trình phản hồi và đánh giá

### 3.2.1. Benefits of Early and Frequent Stakeholder Feedback

> Lợi ích của phản hồi sớm và thường xuyên từ các bên liên quan

Early and frequent feedback allows for the early communication of potential quality problems. If there is little stakeholder involvement during the SDLC, the product being developed might not meet the stakeholder’s original or current vision. A failure to deliver what the stakeholder wants can result in costly rework, missed deadlines, blame games, and might even lead to complete project failure.

Frequent stakeholder feedback throughout the SDLC can prevent misunderstandings about requirements and ensure that changes to requirements are understood and implemented earlier. This helps the development team to improve their understanding of what they are building. It allows them to focus on those features that deliver the most value to the stakeholders and that have the most positive impact on identified risks.

> Phản hồi sớm và thường xuyên cho phép truyền thông sớm về các vấn đề chất lượng tiềm ẩn. Nếu có quá ít sự tham gia của các bên liên quan (stakeholders) trong suốt vòng đời phát triển phần mềm (SDLC), sản phẩm đang được phát triển có thể sẽ không đáp ứng được tầm nhìn ban đầu hoặc tầm nhìn hiện tại của họ. Việc thất bại trong việc bàn giao những gì bên liên quan mong muốn có thể dẫn đến việc phải làm lại (rework) rất tốn kém, trễ hạn định (missed deadlines), đổ lỗi cho nhau, và thậm chí có thể dẫn đến sự thất bại hoàn toàn của dự án.
>
> Phản hồi thường xuyên từ các bên liên quan xuyên suốt SDLC có thể ngăn ngừa sự hiểu lầm về các yêu cầu, đồng thời đảm bảo rằng các thay đổi đối với yêu cầu được thấu hiểu và triển khai sớm hơn. Điều này giúp đội ngũ phát triển nâng cao sự hiểu biết của họ về những gì họ đang xây dựng. Nó cho phép họ tập trung vào các tính năng mang lại nhiều giá trị nhất cho các bên liên quan và có tác động tích cực nhất đến các rủi ro đã được nhận diện.

### 3.2.2. Review Process Activities

> Các hoạt động của quy trình duyệt tài liệu

The ISO/IEC 20246 standard defines a generic review process that provides a structured but flexible framework from which a specific review process may be tailored to a particular situation. If the required review is more formal, then more of the tasks described for the different activities will be needed.

The size of many work products makes them too large to be covered by a single review. The review process may be invoked multiple times to complete the review for the entire work product.

The activities in the review process are:

- **Planning**. During the planning phase, the scope of the review, which comprises the purpose, the work product to be reviewed, quality characteristics to be evaluated, areas to focus on, exit criteria, supporting information such as standards, effort and the timeframes for the review, shall be defined.

- **Review initiation**. During review initiation, the goal is to make sure that everyone and everything involved is prepared to start the review. This includes making sure that every participant has access to the work product under review, understands their role and responsibilities and receives everything needed to perform the review

- **Individual review**. Every reviewer performs an individual review to assess the quality of the work product under review, and to identify anomalies, recommendations, and questions by applying one or more review techniques (e.g., checklist-based reviewing, scenario-based reviewing). The ISO/IEC 20246 standard provides more depth on different review techniques. The reviewers log all their identified anomalies, recommendations, and questions.

- **Communication and analysis**. Since the anomalies identified during a review are not necessarily defects, all these anomalies need to be analyzed and discussed. For every anomaly, the decision should be made on its status, ownership and required actions. This is typically done in a review meeting, during which the participants also decide what the quality level of reviewed work product is and what follow-up actions are required. A follow-up review may be required to complete actions.

- **Fixing and reporting**. For every defect, a defect report should be created so that corrective actions can be followed up. Once the exit criteria are reached, the work product can be accepted. The review results are reported.

> Tiêu chuẩn ISO/IEC 20246 định nghĩa một quy trình duyệt tài liệu tổng quát, cung cấp một khung làm việc có cấu trúc nhưng linh hoạt, từ đó một quy trình duyệt tài liệu cụ thể có thể được tùy biến cho phù hợp với từng tình huống riêng biệt. Nếu hoạt động duyệt tài liệu yêu cầu tính chính thức cao hơn (formal review), thì sẽ cần thực hiện nhiều nhiệm vụ được mô tả cho các hoạt động khác nhau hơn.
>
> Quy mô của nhiều sản phẩm công việc (work products) khiến chúng quá lớn để có thể bao phủ hết trong một lần duyệt duy nhất. Quy trình duyệt tài liệu có thể được gọi thực hiện nhiều lần để hoàn thành việc duyệt cho toàn bộ sản phẩm công việc đó.
>
> Các hoạt động trong quy trình duyệt tài liệu bao gồm:
>
> - **Lập kế hoạch (Planning)**: Trong giai đoạn lập kế hoạch, phạm vi của buổi duyệt tài liệu phải được xác định, bao gồm: mục đích, sản phẩm công việc cần duyệt, các đặc tính chất lượng cần đánh giá, các vùng cần tập trung, tiêu chí thoát (exit criteria), thông tin hỗ trợ như các tiêu chuẩn, công sức và khung thời gian cho việc duyệt tài liệu.
> - **Khởi động duyệt tài liệu (Review initiation)**: Trong giai đoạn khởi động, mục tiêu là đảm bảo mọi người và mọi thứ liên quan đều đã sẵn sàng để bắt đầu buổi duyệt. Điều này bao gồm việc đảm bảo rằng mỗi thành viên tham gia đều có quyền truy cập vào sản phẩm công việc đang được duyệt, hiểu rõ vai trò cũng như trách nhiệm của mình, và nhận được mọi thứ cần thiết để thực hiện việc duyệt tài liệu.
> - **Duyệt tài liệu cá nhân (Individual review)**: Mỗi người kiểm duyệt thực hiện một buổi duyệt cá nhân để đánh giá chất lượng của sản phẩm công việc đang được xem xét, đồng thời nhận diện các điểm bất thường (anomalies), các khuyến nghị và câu hỏi bằng cách áp dụng một hoặc nhiều kỹ thuật duyệt tài liệu (ví dụ: duyệt dựa trên bảng kiểm/checklist-based reviewing, duyệt dựa trên kịch bản/scenario-based reviewing). Tiêu chuẩn ISO/IEC 20246 cung cấp thông tin chuyên sâu hơn về các kỹ thuật duyệt tài liệu khác nhau. Người kiểm duyệt sẽ ghi nhận (log) lại tất cả các bất thường, khuyến nghị và câu hỏi mà họ đã nhận diện được.
> - **Giao tiếp và phân tích (Communication and analysis)**: Vì các bất thường được nhận diện trong quá trình duyệt tài liệu không nhất thiết đều là khuyết tật (defects), tất cả các bất thường này cần phải được phân tích và thảo luận. Đối với mỗi bất thường, cần đưa ra quyết định về trạng thái, người chịu trách nhiệm và các hành động cần thiết. Việc này thường được thực hiện trong một cuộc họp duyệt tài liệu (review meeting), tại đây các thành viên tham gia cũng sẽ quyết định mức độ chất lượng của sản phẩm công việc đã duyệt là gì và các hành động tiếp theo nào là cần thiết. Một buổi duyệt tiếp theo (follow-up review) có thể được yêu cầu để hoàn thành các hành động này.
> - **Sửa lỗi và báo cáo (Fixing and reporting)**: Đối với mỗi khuyết tật, một báo cáo khuyết tật (defect report) cần được tạo ra để các hành động khắc phục có thể được theo dõi sát sao. Một khi các tiêu chí thoát (exit criteria) được đáp ứng, sản phẩm công việc có thể được chấp nhận. Kết quả duyệt tài liệu sẽ được báo cáo.

### 3.2.3. Roles and Responsibilities in Reviews

> Các vai trò và trách nhiệm trong duyệt tài liệu

Reviews involve various stakeholders, who may take on several roles. The principal roles and their
responsibilities are:

- Manager – decides what is to be reviewed and provides resources, such as staff and time for the review
- Author – creates and fixes the work product under review
- Moderator (also known as the facilitator) – ensures the effective running of review meetings, including mediation, time management, and a safe review environment in which everyone can speak freely
- Scribe (also known as recorder) – collates anomalies from reviewers and records review information, such as decisions and new anomalies found during the review meeting
- Reviewer – performs reviews. A reviewer may be someone working on the project, a subject matter expert, or any other stakeholder
- Review leader – takes overall responsibility for the review such as deciding who will be involved, and organizing when and where the review will take place

Other, more detailed roles are possible, as described in the ISO/IEC 20246 standard.

> Hoạt động duyệt tài liệu có sự tham gia của nhiều bên liên quan khác nhau, những người có thể đảm nhận một số vai trò. Các vai trò chính và trách nhiệm của họ bao gồm:
>
> - **Quản lý (Manager)**: Quyết định những gì cần được duyệt và cung cấp các nguồn lực, chẳng hạn như nhân sự và thời gian cho buổi duyệt tài liệu.
> - **Tác giả (Author)**: Tạo ra và sửa đổi sản phẩm công việc đang được duyệt.
> - **Người điều phối (Moderator - còn gọi là facilitator)**: Đảm bảo các cuộc họp duyệt tài liệu diễn ra hiệu quả, bao gồm việc hòa giải, quản lý thời gian và tạo ra một môi trường duyệt tài liệu an toàn để mọi người có thể tự do phát biểu.
> - **Người ghi chép (Scribe - còn gọi là recorder)**: Thu thập các bất thường từ những người kiểm duyệt và ghi lại thông tin của buổi duyệt, chẳng hạn như các quyết định và các bất thường mới được tìm thấy trong cuộc họp duyệt tài liệu.
> - **Người kiểm duyệt (Reviewer)**: Thực hiện việc duyệt tài liệu. Người kiểm duyệt có thể là một thành viên đang làm việc trong dự án, một chuyên gia trong lĩnh vực chuyên môn (subject matter expert) hoặc bất kỳ bên liên quan nào khác.
> - **Trưởng nhóm duyệt tài liệu (Review leader)**: Chịu trách nhiệm tổng thể cho buổi duyệt tài liệu, chẳng hạn như quyết định ai sẽ tham gia, tổ chức thời gian và địa điểm diễn ra buổi duyệt.
>
> Các vai trò khác chi tiết hơn có thể được áp dụng, như mô tả trong tiêu chuẩn ISO/IEC 20246.

### 3.2.4. Review Types

> Các loại duyệt tài liệu

There exist many review types ranging from informal reviews to formal reviews. The required level of formality depends on factors such as the SDLC being followed, the maturity of the development process, the criticality and complexity of the work product being reviewed, legal or regulatory requirements, and the need for an audit trail. The same work product can be reviewed with different review types, e.g., first an informal one and later a more formal one.

Selecting the right review type is key to achieving the required review objectives (see section 3.2.5). The selection is not only based on the objectives, but also on factors such as the project needs, available resources, work product type and risks, business domain, and company culture.

Some commonly used review types are:

- **Informal review.** Informal reviews do not follow a defined process and do not require a formal documented output. The main objective is detecting anomalies.

- **Walkthrough**. A walkthrough, which is led by the author, can serve many objectives, such as evaluating quality and building confidence in the work product, educating reviewers, gaining consensus, generating new ideas, motivating and enabling authors to improve and detecting anomalies. Reviewers might perform an individual review before the walkthrough, but this is not required.

- **Technical Review.** A technical review is performed by technically qualified reviewers and led by a moderator. The objectives of a technical review are to gain consensus and make decisions regarding a technical problem, but also to detect anomalies, evaluate quality and build confidence in the work product, generate new ideas, and to motivate and enable authors to improve.

- **Inspection**. As inspections are the most formal type of review, they follow the complete generic process (see section 3.2.2). The main objective is to find the maximum number of anomalies. Other objectives are to evaluate quality, build confidence in the work product, and to motivate and enable authors to improve. Metrics are collected and used to improve the SDLC, including the inspection process. In inspections, the author cannot act as the review leader or scribe

> Có rất nhiều loại duyệt tài liệu khác nhau, từ các buổi duyệt tài liệu không chính thức (informal reviews) cho đến các buổi duyệt tài liệu chính thức (formal reviews). Mức độ chính thức được yêu cầu phụ thuộc vào các yếu tố như: mô hình SDLC đang được áp dụng, độ trưởng thành của quy trình phát triển, mức độ quan trọng và tính phức tạp của sản phẩm công việc đang được duyệt, các yêu cầu mang tính pháp lý hoặc quy định, và nhu cầu về việc lưu vết kiểm toán (audit trail). Cùng một sản phẩm công việc có thể được kiểm duyệt bằng nhiều loại duyệt tài liệu khác nhau, ví dụ: đầu tiên là duyệt không chính thức và sau đó là một buổi duyệt chính thức hơn.
>
> Việc lựa chọn đúng loại duyệt tài liệu là chìa khóa để đạt được các mục tiêu kiểm duyệt đề ra (xem mục 3.2.5). Sự lựa chọn này không chỉ dựa trên các mục tiêu, mà còn dựa trên các yếu tố như nhu cầu của dự án, nguồn lực sẵn có, loại sản phẩm công việc và các rủi ro, lĩnh vực kinh doanh (business domain) và văn hóa công ty.
>
> Một số loại duyệt tài liệu được sử dụng phổ biến bao gồm:
>
> - **Duyệt tài liệu không chính thức (Informal review)**: Các buổi duyệt không chính thức không tuân theo một quy trình định sẵn và không yêu cầu một kết quả đầu ra được tài liệu hóa một cách chính thức. Mục tiêu chính là phát hiện các điểm bất thường (anomalies).
> - **Hướng dẫn sơ bộ (Walkthrough)**: Một buổi walkthrough do tác giả (author) chủ trì, có thể phục vụ nhiều mục tiêu như: đánh giá chất lượng và tạo dựng niềm tin vào sản phẩm công việc, đào tạo cho người kiểm duyệt, đạt được sự đồng thuận, tạo ra các ý tưởng mới, thúc đẩy và hỗ trợ tác giả cải tiến sản phẩm, và phát hiện các điểm bất thường. Người kiểm duyệt có thể thực hiện một buổi duyệt cá nhân trước khi tham gia walkthrough, nhưng điều này là không bắt buộc.
> - **Duyệt kỹ thuật (Technical Review)**: Một buổi duyệt kỹ thuật được thực hiện bởi các người kiểm duyệt có trình độ kỹ thuật chuyên môn và được chủ trì bởi một người điều phối (moderator). Mục tiêu của một buổi duyệt kỹ thuật là đạt được sự đồng thuận và đưa ra quyết định đối với một vấn đề kỹ thuật, đồng thời cũng để phát hiện các điểm bất thường, đánh giá chất lượng và tạo dựng niềm tin vào sản phẩm công việc, tạo ra các ý tưởng mới, thúc đẩy và hỗ trợ tác giả cải tiến sản phẩm.
> - **Kiểm tra chuyên sâu (Inspection)**: Vì kiểm tra chuyên sâu là loại duyệt tài liệu chính thức nhất (most formal), chúng tuân theo toàn bộ quy trình tổng quát (xem mục 3.2.2). Mục tiêu chính là tìm ra số lượng các điểm bất thường tối đa. Các mục tiêu khác là đánh giá chất lượng, tạo dựng niềm tin vào sản phẩm công việc, thúc đẩy và hỗ trợ tác giả cải tiến sản phẩm. Các số đo/số liệu (metrics) được thu thập và sử dụng để cải tiến SDLC, bao gồm cả chính quy trình kiểm tra chuyên sâu này. Trong các buổi kiểm tra chuyên sâu, tác giả không được phép đóng vai trò là trưởng nhóm duyệt tài liệu (review leader) hoặc người ghi chép (scribe).

### 3.2.5. Success Factors for Reviews

> Các yếu tố thành công của duyệt tài liệu

There are several factors that determine the success of reviews, which include:

- Defining clear objectives and measurable exit criteria. Evaluation of participants should never be an objective
- Choosing the appropriate review type to achieve the given objectives, and to suit the type of work product, the review participants, the project needs and context
- Performing reviews on small chunks, so that reviewers do not lose concentration during an individual review and/or the review meeting (when held)
- Providing feedback from reviews to stakeholders and authors so they can improve the product and their activities (see section 3.2.1)
- Providing adequate time to participants to prepare for the review
- Support from management for the review process
- Making reviews part of the organization’s culture, to promote learning and process improvement
- Providing adequate training for all participants so they know how to fulfil their role
- Facilitating meetings

> Có một số yếu tố quyết định sự thành công của các buổi duyệt tài liệu, bao gồm:
>
> - Xác định các mục tiêu rõ ràng và các tiêu chí thoát (exit criteria) có thể đo lường được. Việc đánh giá năng lực của những người tham gia tuyệt đối không bao giờ được là một mục tiêu.
> - Lựa chọn loại duyệt tài liệu phù hợp để đạt được các mục tiêu đề ra, đồng thời phù hợp với loại sản phẩm công việc, các thành viên tham gia duyệt, nhu cầu và bối cảnh của dự án.
> - Thực hiện duyệt tài liệu trên các phần nhỏ (small chunks), để người kiểm duyệt không bị mất tập trung trong quá trình duyệt cá nhân và/hoặc trong cuộc họp duyệt tài liệu (nếu có tổ chức).
> - Cung cấp phản hồi từ các buổi duyệt cho các bên liên quan (stakeholders) và tác giả (authors) để họ có thể cải tiến sản phẩm cũng như các hoạt động của mình (xem mục 3.2.1).
> - Cung cấp đủ thời gian cho các thành viên tham gia để chuẩn bị cho buổi duyệt tài liệu.
> - Có sự hỗ trợ từ phía quản lý (management) đối với quy trình duyệt tài liệu.
> - Đưa hoạt động duyệt tài liệu trở thành một phần trong văn hóa của tổ chức, nhằm thúc đẩy việc học hỏi và cải tiến quy trình.
> - Cung cấp các buổi đào tạo đầy đủ cho tất cả các thành viên tham gia để họ biết cách hoàn thành vai trò của mình.
> - Tạo điều kiện thuận lợi và điều phối tốt các cuộc họp (facilitating meetings).
