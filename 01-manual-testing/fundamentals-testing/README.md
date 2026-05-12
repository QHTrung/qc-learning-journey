# 1. Fundamentals of Testing

> Nguyên tắc cơ bản của kiểm thử

### Table of contents

- [Keywords](#keywords)
- [1.1 What is Testing?](#11-what-is-testing)
  - [1.1.1 Test Objectives](#111-test-objectives)
  - [1.1.2 Testing and Debugging](#112-testing-and-debugging)

## **Keywords**

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

> Các hệ thống phần mềm là một phần không thể thiếu trong cuộc sống hằng ngày của chúng ta. Hầu hết mọi người đều từng trải qua việc phần mềm không hoạt động như mong đợi. Phần mềm hoạt động không đúng có thể dẫn đến nhiều vấn đề, bao gồm mất tiền, mất thời gian hoặc ảnh hưởng đến uy tín doanh nghiệp, và trong những trường hợp nghiêm trọng thậm chí có thể gây thương tích hoặc tử vong.<br>
> Kiểm thử phần mềm đánh giá chất lượng phần mềm và giúp giảm thiểu rủi ro xảy ra lỗi phần mềm trong quá trình vận hành. <br>
> Kiểm thử phần mềm là tập hợp các hoạt động nhằm phát hiện lỗi và đánh giá chất lượng của các sản phẩm công việc phần mềm. Những sản phẩm công việc này, khi được kiểm thử, được gọi là đối tượng kiểm thử (test objects). <br>
> Một hiểu lầm phổ biến về kiểm thử là cho rằng nó chỉ bao gồm việc thực thi kiểm thử (tức là chạy phần mềm và kiểm tra kết quả kiểm thử). Tuy nhiên, kiểm thử phần mềm còn bao gồm nhiều hoạt động khác và phải được liên kết với vòng đời phát triển phần mềm (xem chương 2).<br>
> Một hiểu lầm phổ biến khác là kiểm thử chỉ tập trung hoàn toàn vào việc xác minh đối tượng kiểm thử. Mặc dù kiểm thử có bao gồm verification, tức là kiểm tra xem hệ thống có đáp ứng các yêu cầu đã được đặc tả hay không, nó cũng bao gồm validation, nghĩa là kiểm tra xem hệ thống có đáp ứng nhu cầu của người dùng và các bên liên quan khác trong môi trường vận hành thực tế hay không.<br>
> Kiểm thử có thể là kiểm thử động hoặc kiểm thử tĩnh. Kiểm thử động liên quan đến việc thực thi phần mềm, trong khi kiểm thử tĩnh thì không. Kiểm thử tĩnh bao gồm review (xem chương 3) và phân tích tĩnh (static analysis). Kiểm thử động sử dụng nhiều loại kỹ thuật và phương pháp kiểm thử khác nhau để thiết kế test case (xem chương 4).<br>
> Kiểm thử không chỉ là một hoạt động kỹ thuật. Nó còn cần được lập kế hoạch, quản lý, ước lượng, giám sát và kiểm soát một cách phù hợp (xem chương 5).<br>
> Người kiểm thử sử dụng các công cụ (xem chương 6), nhưng điều quan trọng cần nhớ là kiểm thử phần lớn vẫn là một hoạt động mang tính trí tuệ, đòi hỏi tester phải có kiến thức chuyên môn, kỹ năng phân tích, tư duy phản biện và tư duy hệ thống (Myers 2011, Roman 2018).<br>
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
