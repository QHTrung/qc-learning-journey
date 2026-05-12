# 1. Fundamentals of Testing

> Nguyên tắc cơ bản của kiểm thử

### Table of contents

- [1. Fundamentals of Testing](#1-fundamentals-of-testing)
    - [Table of contents](#table-of-contents)
  - [Keywords](#keywords)
  - [1.1 What is Testing?](#11-what-is-testing)
    - [1.1.1 Test Objectives](#111-test-objectives)
    - [1.1.2 Testing and Debugging](#112-testing-and-debugging)
  - [1.2 Why is Testing Necessary?](#12-why-is-testing-necessary)
    - [1.2.1 Testing’s Contributions to Success](#121-testings-contributions-to-success)
    - [1.2.2 Testing and Quality Assurance (QA)](#122-testing-and-quality-assurance-qa)
    - [1.2.3. Errors, Defects, Failures, and Root Causes](#123-errors-defects-failures-and-root-causes)

## Keywords

| Keyword             |          Translate           |
| ------------------- | :--------------------------: |
| coverage            |          độ bao phủ          |
| debugging           |            gỡ lỗi            |
| defect              |      lỗi / khiếm khuyết      |
| error               |    sai sót (do con người)    |
| failure             | sự cố / lỗi xảy ra khi chạy  |
| quality             |          chất lượng          |
| quality assurance   |      đảm bảo chất lượng      |
| root cause          |      nguyên nhân gốc rễ      |
| test analysis       |      phân tích kiểm thử      |
| test basis          |        cơ sở kiểm thử        |
| test case           |     trường hợp kiểm thử      |
| test completion     |      hoàn tất kiểm thử       |
| test condition      |      điều kiện kiểm thử      |
| test control        |      kiểm soát kiểm thử      |
| test data           |       dữ liệu kiểm thử       |
| test design         |      thiết kế kiểm thử       |
| test execution      |      thực thi kiểm thử       |
| test implementation |     triển khai kiểm thử      |
| test monitoring     |      giám sát kiểm thử       |
| test object         |      đối tượng kiểm thử      |
| test objective      |      mục tiêu kiểm thử       |
| test planning       |    lập kế hoạch kiểm thử     |
| test procedure      | quy trình / thủ tục kiểm thử |
| test process        |      quá trình kiểm thử      |
| test result         |       kết quả kiểm thử       |
| testing             |      hoạt động kiểm thử      |
| testware            | tài liệu và công cụ kiểm thử |
| traceability        |      khả năng truy vết       |
| validation          |           xác nhận           |
| verification        |           xác minh           |

## 1.1 What is Testing?

> Kiểm thử là gì?

Software systems are an integral part of our daily life. Most people have had experience with software that did not work as expected. Software that does not work correctly can lead to many problems, including loss of money, time or business reputation, and, in extreme cases, even injury or death. Software testing assesses software quality and helps reducing the risk of software failure in operation.

Software testing is a set of activities to discover defects and evaluate the quality of software work products. These work products, when being tested, are known as test objects. A common misconception about testing is that it only consists of executing tests (i.e., running the software and checking the test results). However, software testing also includes other activities and must be aligned with the software development lifecycle (see chapter 2).

Another common misconception about testing is that testing focuses entirely on verifying the test object. While testing involves verification, i.e., checking whether the system meets specified requirements, it also involves validation, which means checking whether the system meets users’ and other stakeholders’ needs in its operational environment.

Testing may be dynamic or static. Dynamic testing involves the execution of software, while static testing does not. Static testing includes reviews (see chapter 3) and static analysis. Dynamic testing uses different types of test techniques and test approaches to derive test cases (see chapter 4).

Testing is not only a technical activity. It also needs to be properly planned, managed, estimated, monitored and controlled (see chapter 5).

Testers use tools (see chapter 6), but it is important to remember that testing is largely an intellectual activity, requiring the testers to have specialized knowledge, use analytical skills and apply critical thinking and systems thinking (Myers 2011, Roman 2018).

The ISO/IEC/IEEE 29119-1 standard provides further information about software testing concepts.

> Các hệ thống phần mềm là một phần không thể thiếu trong cuộc sống hằng ngày của chúng ta. Hầu hết mọi người đều từng trải qua việc phần mềm không hoạt động như mong đợi. Phần mềm hoạt động không đúng có thể dẫn đến nhiều vấn đề, bao gồm mất tiền, mất thời gian hoặc ảnh hưởng đến uy tín doanh nghiệp, và trong những trường hợp nghiêm trọng thậm chí có thể gây thương tích hoặc tử vong.
>
> Kiểm thử phần mềm đánh giá chất lượng phần mềm và giúp giảm thiểu rủi ro xảy ra lỗi phần mềm trong quá trình vận hành.
>
> Kiểm thử phần mềm là tập hợp các hoạt động nhằm phát hiện lỗi và đánh giá chất lượng của các sản phẩm công việc phần mềm. Những sản phẩm công việc này, khi được kiểm thử, được gọi là đối tượng kiểm thử (test objects).
>
> Một hiểu lầm phổ biến về kiểm thử là cho rằng nó chỉ bao gồm việc thực thi kiểm thử (tức là chạy phần mềm và kiểm tra kết quả kiểm thử). Tuy nhiên, kiểm thử phần mềm còn bao gồm nhiều hoạt động khác và phải được liên kết với vòng đời phát triển phần mềm (xem chương 2).
>
> Một hiểu lầm phổ biến khác là kiểm thử chỉ tập trung hoàn toàn vào việc xác minh đối tượng kiểm thử. Mặc dù kiểm thử có bao gồm verification, tức là kiểm tra xem hệ thống có đáp ứng các yêu cầu đã được đặc tả hay không, nó cũng bao gồm validation, nghĩa là kiểm tra xem hệ thống có đáp ứng nhu cầu của người dùng và các bên liên quan khác trong môi trường vận hành thực tế hay không.
>
> Kiểm thử có thể là kiểm thử động hoặc kiểm thử tĩnh. Kiểm thử động liên quan đến việc thực thi phần mềm, trong khi kiểm thử tĩnh thì không. Kiểm thử tĩnh bao gồm review (xem chương 3) và phân tích tĩnh (static analysis). Kiểm thử động sử dụng nhiều loại kỹ thuật và phương pháp kiểm thử khác nhau để thiết kế test case (xem chương 4).
>
> Kiểm thử không chỉ là một hoạt động kỹ thuật. Nó còn cần được lập kế hoạch, quản lý, ước lượng, giám sát và kiểm soát một cách phù hợp (xem chương 5).
>
> Người kiểm thử sử dụng các công cụ (xem chương 6), nhưng điều quan trọng cần nhớ là kiểm thử phần lớn vẫn là một hoạt động mang tính trí tuệ, đòi hỏi tester phải có kiến thức chuyên môn, kỹ năng phân tích, tư duy phản biện và tư duy hệ thống (Myers 2011, Roman 2018).
>
> Tiêu chuẩn ISO/IEC/IEEE 29119-1 cung cấp thêm thông tin về các khái niệm kiểm thử phần mềm.

### 1.1.1 Test Objectives

The typical test objectives are:
• Evaluating work products such as requirements, user stories, designs, and code
• Causing failures and finding defects
• Ensuring required coverage of a test object
• Reducing the risk level of inadequate software quality
• Verifying whether specified requirements have been fulfilled
• Verifying that a test object complies with contractual, legal, and regulatory requirements
• Providing information to stakeholders to allow them to make informed decisions
• Building confidence in the quality of the test object
• Validating whether the test object is complete and works as expected by the stakeholders

Test objectives can vary, depending upon the context, which includes the work product being tested, the test level, risks, the software development lifecycle (SDLC) being followed, and factors related to the business context, e.g., corporate structure, competitive considerations, or time to market

> Các mục tiêu điển hình của kiểm thử bao gồm:
>
> - Đánh giá các sản phẩm công việc như yêu cầu, user story, thiết kế và mã nguồn
> - Gây ra failure và tìm defect
> - Đảm bảo mức độ bao phủ cần thiết cho đối tượng kiểm thử
> - Giảm mức độ rủi ro do chất lượng phần mềm không đạt yêu cầu
> - Xác minh xem các yêu cầu đã được đặc tả có được đáp ứng hay chưa
> - Xác minh rằng đối tượng kiểm thử tuân thủ các yêu cầu về hợp đồng, pháp lý và quy định
> - Cung cấp thông tin cho các bên liên quan để họ có thể đưa ra quyết định chính xác
> - Xây dựng niềm tin vào chất lượng của đối tượng kiểm thử
> - Xác nhận rằng đối tượng kiểm thử đã hoàn chỉnh và hoạt động đúng như kỳ vọng của các bên liên quan

> Mục tiêu kiểm thử có thể khác nhau tùy thuộc vào ngữ cảnh, bao gồm sản phẩm công việc đang được kiểm thử, mức kiểm thử (test level), rủi ro, vòng đời phát triển phần mềm (SDLC) được áp dụng, và các yếu tố liên quan đến bối cảnh kinh doanh, ví dụ như cơ cấu tổ chức doanh nghiệp, yếu tố cạnh tranh hoặc thời gian đưa sản phẩm ra thị trường

### 1.1.2 Testing and Debugging

Testing and debugging are separate activities. Testing can trigger failures that are caused by defects in the software (dynamic testing) or can directly find defects in the test object (static testing).

When dynamic testing (see chapter 4) triggers a failure, debugging is concerned with finding causes of this failure (defects), analyzing these causes, and eliminating them. The typical debugging process in this case involves:
• Reproduction of a failure
• Diagnosis (finding the defect)
• Fixing the defect

Subsequent confirmation testing checks whether the fixes resolved the problem. Preferably, confirmation testing is done by the same person who performed the initial test. Subsequent regression testing can also be performed, to check whether the fixes are causing failures in other parts of the test object (see section 2.2.3 for more information on confirmation testing and regression testing).

When static testing identifies a defect, debugging is concerned with removing it. There is no need for reproduction or diagnosis, since static testing directly finds defects, and cannot cause failures (see chapter 3).

> Kiểm thử (testing) và gỡ lỗi (debugging) là hai hoạt động riêng biệt. Kiểm thử có thể kích hoạt failure do defect trong phần mềm gây ra (dynamic testing) hoặc có thể trực tiếp tìm ra defect trong đối tượng kiểm thử (static testing).
>
> Khi dynamic testing (xem chương 4) gây ra failure, debugging sẽ tập trung vào việc tìm nguyên nhân của failure đó (các defect), phân tích nguyên nhân và loại bỏ chúng. Quy trình debugging điển hình trong trường hợp này bao gồm:
>
> - Tái hiện failure
> - Chẩn đoán (tìm defect)
> - Sửa defect
>
> Sau đó, confirmation testing sẽ kiểm tra xem việc sửa lỗi đã giải quyết được vấn đề hay chưa. Tốt nhất, confirmation testing nên được thực hiện bởi cùng một người đã thực hiện kiểm thử ban đầu.
>
> Tiếp theo, regression testing cũng có thể được thực hiện để kiểm tra xem việc sửa lỗi có gây ra failure ở những phần khác của đối tượng kiểm thử hay không (xem mục 2.2.3 để biết thêm thông tin về confirmation testing và regression testing).
>
> Khi static testing xác định được defect, debugging sẽ tập trung vào việc loại bỏ defect đó. Trong trường hợp này không cần tái hiện hay chẩn đoán lỗi, vì static testing trực tiếp tìm ra defect và không thể gây ra failure (xem chương 3).

## 1.2 Why is Testing Necessary?

> Tại sao kiểm thử lại cần thiết?

Testing, as a form of quality control, helps in achieving the agreed upon test objectives within the set scope, time, quality, and budget constraints. Testing’s contribution to success should not be restricted to the test team activities. Any stakeholder can use their testing skills to bring the project closer to success. Testing components, systems, and associated work products (e.g., documentation) helps to identify defects in software.

> Kiểm thử, với vai trò là một hình thức kiểm soát chất lượng (quality control), giúp đạt được các mục tiêu kiểm thử đã được thống nhất trong phạm vi, thời gian, chất lượng và ngân sách đã đặt ra.
>
> Sự đóng góp của kiểm thử vào thành công của dự án không nên chỉ giới hạn trong các hoạt động của đội ngũ kiểm thử. Bất kỳ bên liên quan nào cũng có thể sử dụng kỹ năng kiểm thử của mình để giúp dự án tiến gần hơn đến thành công.
>
> Việc kiểm thử các thành phần, hệ thống và các sản phẩm công việc liên quan (ví dụ: tài liệu) giúp xác định các defect trong phần mềm.

### 1.2.1 Testing’s Contributions to Success

> Sự đóng góp của kiểm thử đối với thành công

Testing provides a cost-effective means of detecting defects. These defects can then be removed (by debugging – a non-testing activity), so testing indirectly contributes to higher quality test objects.

Testing provides a means of directly evaluating the quality of a test object at various phases in the SDLC. These measures are used as part of a larger project management activity, contributing to decisions to move to the next phase of the SDLC, such as the release decision.

Testing provides users with indirect representation on the development project. Testers ensure that their understanding of users’ needs are considered throughout the development lifecycle. The alternative is to involve a representative set of users as part of the development project, which is not usually possible due to the high costs and lack of availability of suitable users.

Testing may also be required to meet contractual or legal requirements, or to comply with regulatory standards.

> Kiểm thử cung cấp một phương pháp hiệu quả về mặt chi phí để phát hiện defect. Những defect này sau đó có thể được loại bỏ (thông qua debugging – một hoạt động không thuộc kiểm thử), vì vậy kiểm thử gián tiếp góp phần nâng cao chất lượng của đối tượng kiểm thử.
>
> Kiểm thử cung cấp phương tiện để đánh giá trực tiếp chất lượng của đối tượng kiểm thử tại nhiều giai đoạn khác nhau trong vòng đời phát triển phần mềm (SDLC). Các kết quả đánh giá này được sử dụng như một phần của hoạt động quản lý dự án tổng thể, hỗ trợ cho các quyết định chuyển sang giai đoạn tiếp theo của SDLC, ví dụ như quyết định phát hành sản phẩm.
>
> Kiểm thử đại diện gián tiếp cho người dùng trong dự án phát triển. Tester đảm bảo rằng sự hiểu biết của họ về nhu cầu người dùng được xem xét xuyên suốt vòng đời phát triển. Giải pháp thay thế là đưa một nhóm người dùng đại diện tham gia trực tiếp vào dự án phát triển, tuy nhiên điều này thường không khả thi do chi phí cao và khó tìm được người dùng phù hợp.
>
> Kiểm thử cũng có thể được yêu cầu nhằm đáp ứng các điều khoản hợp đồng hoặc yêu cầu pháp lý, hay để tuân thủ các tiêu chuẩn quy định.

### 1.2.2 Testing and Quality Assurance (QA)

> Kiểm thử và Đảm bảo chất lượng (QA)

While people often use the terms “testing” and “quality assurance” (QA) interchangeably, testing and QA are not the same.

Testing is a product-oriented, corrective approach that focuses on those activities supporting the achievement of appropriate levels of quality. Testing is a major form of quality control, while others include formal methods (model checking and proof of correctness), simulation and prototyping.

QA is a process-oriented, preventive approach that focuses on the implementation and improvement of processes. It works on the basis that if a good process is followed correctly, then it will generate a good product. QA applies to both the development and testing processes, and is the responsibility of everyone on a project.

Test results are used by QA and testing. In testing they are used to fix defects, while in QA they provide feedback on how well the development and test processes are performing.

> Mặc dù mọi người thường sử dụng hai thuật ngữ “testing” và “quality assurance” (QA) thay thế cho nhau, nhưng kiểm thử và QA không giống nhau.
>
> Kiểm thử là một phương pháp mang định hướng sản phẩm (product-oriented), mang tính khắc phục (corrective), tập trung vào các hoạt động hỗ trợ đạt được mức chất lượng phù hợp. Kiểm thử là một hình thức chính của quality control (kiểm soát chất lượng), bên cạnh các hình thức khác như phương pháp hình thức (formal methods – model checking và proof of correctness), mô phỏng (simulation) và tạo mẫu (prototyping).
>
> QA là một phương pháp mang định hướng quy trình (process-oriented), mang tính phòng ngừa (preventive), tập trung vào việc triển khai và cải tiến các quy trình. QA hoạt động dựa trên nguyên tắc rằng nếu một quy trình tốt được tuân thủ đúng cách, thì nó sẽ tạo ra một sản phẩm tốt. QA áp dụng cho cả quy trình phát triển và quy trình kiểm thử, đồng thời là trách nhiệm của tất cả mọi người trong dự án.
>
> Kết quả kiểm thử được sử dụng bởi cả QA và testing. Trong testing, chúng được dùng để sửa defect, còn trong QA, chúng cung cấp phản hồi về mức độ hiệu quả của các quy trình phát triển và kiểm thử.

### 1.2.3. Errors, Defects, Failures, and Root Causes

Human beings make errors (mistakes), which produce defects (faults, bugs), which in turn may result in failures. Humans make errors for various reasons, such as time pressure, complexity of work products, processes, infrastructure or interactions, or simply because they are tired or lack adequate training

Defects can be found in documentation, such as a requirements specification or a test script, in source code, or in a supporting work product such as a build file. Defects in work products produced earlier in the SDLC, if undetected, often lead to defective work products later in the lifecycle. If a defect in code is executed, the system may fail to do what it should do, or do something it shouldn’t, causing a failure. Some defects will always result in a failure if executed, while others will only result in a failure in specific circumstances, and some may never result in a failure

Errors and defects are not the only cause of failures. Failures can also be caused by environmental conditions, such as when radiation or electromagnetic fields cause defects in firmware

A root cause is a fundamental reason for the occurrence of a problem (e.g., a situation that leads to an error). Root causes are identified through root cause analysis, which is typically performed when a failure occurs or a defect is identified. It is believed that further similar failures or defects can be prevented or their frequency reduced by addressing the root cause, such as by removing it.

> Con người tạo ra error (sai sót), từ đó sinh ra defect (faults, bugs), và các defect này có thể dẫn đến failure. Con người mắc lỗi vì nhiều lý do khác nhau, chẳng hạn như áp lực thời gian, độ phức tạp của sản phẩm công việc, quy trình, cơ sở hạ tầng hoặc các tương tác, hoặc đơn giản là do mệt mỏi hay thiếu đào tạo đầy đủ.
>
> Defect có thể được tìm thấy trong tài liệu, ví dụ như đặc tả yêu cầu hoặc test script, trong source code, hoặc trong các sản phẩm công việc hỗ trợ như build file. Các defect xuất hiện ở những sản phẩm công việc được tạo ra sớm trong SDLC nếu không được phát hiện thường sẽ dẫn đến defect ở các sản phẩm công việc về sau trong vòng đời phát triển.
>
> Nếu một defect trong code được thực thi, hệ thống có thể không làm được điều mà nó cần làm, hoặc làm điều mà nó không nên làm, từ đó gây ra failure.
>
> Một số defect sẽ luôn dẫn đến failure khi được thực thi, trong khi một số khác chỉ gây failure trong những điều kiện cụ thể, và một số defect thậm chí có thể không bao giờ gây ra failure.
>
> Error và defect không phải là nguyên nhân duy nhất gây ra failure. Failure cũng có thể do các điều kiện môi trường gây nên, ví dụ như bức xạ hoặc trường điện từ tạo ra defect trong firmware.
>
> Root cause (nguyên nhân gốc rễ) là lý do cốt lõi dẫn đến sự xuất hiện của một vấn đề (ví dụ: một tình huống dẫn đến error). Root cause được xác định thông qua root cause analysis, hoạt động thường được thực hiện khi xảy ra failure hoặc khi phát hiện defect.
>
> Người ta tin rằng việc xử lý root cause, chẳng hạn như loại bỏ nó, có thể ngăn chặn các failure hoặc defect tương tự xảy ra trong tương lai hoặc làm giảm tần suất xuất hiện của chúng.
