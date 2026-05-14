# 2. Testing Throughout the Software Development Lifecycle

> Kiểm thử trong suốt vòng đời phát triển phần mềm

### Table of contents

- [2. Testing Throughout the Software Development Lifecycle](#2-testing-throughout-the-software-development-lifecycle)
  - [Table of contents](#table-of-contents)
  - [Keywords](#keywords)
  - [2.1. Testing in the Context of a Software Development Lifecycle (SDLC)](#21-testing-in-the-context-of-a-software-development-lifecycle-sdlc)
    - [2.1.1. Impact of the Software Development Lifecycle on Testing](#211-impact-of-the-software-development-lifecycle-on-testing)
    - [2.1.2. Software Development Lifecycle and Good Testing Practices](#212-software-development-lifecycle-and-good-testing-practices)
    - [2.1.3. Testing as a Driver for Software Development](#213-testing-as-a-driver-for-software-development)
    - [2.1.4. DevOps and Testing](#214-devops-and-testing)
    - [2.1.5. Shift Left](#215-shift-left)
    - [2.1.6. Retrospectives and Process Improvement](#216-retrospectives-and-process-improvement)

## Keywords

| Keyword                       |                        Translate                        |
| ----------------------------- | :-----------------------------------------------------: |
| acceptance testing            |                   kiểm thử chấp nhận                    |
| black-box testing             |                    kiểm thử hộp đen                     |
| component integration testing |              kiểm thử tích hợp thành phần               |
| component testing             |                   kiểm thử thành phần                   |
| confirmation testing          |                    kiểm thử xác nhận                    |
| functional testing            |                   kiểm thử chức năng                    |
| integration testing           |                    kiểm thử tích hợp                    |
| maintenance testing           |                    kiểm thử bảo trì                     |
| non-functional testing        |                 kiểm thử phi chức năng                  |
| regression testing            |                    kiểm thử hồi quy                     |
| shift left                    | dịch chuyển kiểm thử sang phía đầu quy trình phát triển |
| system integration testing    |               kiểm thử tích hợp hệ thống                |
| system testing                |                    kiểm thử hệ thống                    |
| test level                    |                      mức kiểm thử                       |
| test object                   |                   đối tượng kiểm thử                    |
| test type                     |                      loại kiểm thử                      |
| white-box testing             |                   kiểm thử hộp trắng                    |

## 2.1. Testing in the Context of a Software Development Lifecycle (SDLC)

> Kiểm thử trong bối cảnh của Vòng đời phát triển phần mềm (SDLC)

An SDLC model is an abstract, high-level representation of the software development process. An SDLC model defines how different development phases and types of activities performed within this process relate to each other, both logically and chronologically. Examples of SDLC models include: sequential development models (e.g., waterfall model, V-model), iterative development models (e.g., spiral model, prototyping), and incremental development models (e.g., Unified Process).

Some activities within software development processes can also be described by more detailed software development methods and Agile practices. Examples include: acceptance test-driven development (ATDD), behavior-driven development (BDD), domain-driven design (DDD), extreme programming (XP), feature-driven development (FDD), Kanban, Lean IT, Scrum, and test-driven development (TDD).

> Mô hình SDLC là một biểu diễn trừu tượng ở mức cao của quy trình phát triển phần mềm.
>
> Một mô hình SDLC xác định cách các giai đoạn phát triển khác nhau và các loại hoạt động được thực hiện trong quy trình này liên hệ với nhau cả về mặt logic lẫn trình tự thời gian.
>
> Ví dụ về các mô hình SDLC bao gồm:
>
> Các mô hình phát triển tuần tự (sequential development models), chẳng hạn như:
>
> - Waterfall model
> - V-model
>
> Các mô hình phát triển lặp (iterative development models), chẳng hạn như:
>
> - Spiral model
> - Prototyping;
>
> Các mô hình phát triển gia tăng (incremental development models), chẳng hạn như:
>
> - Unified Process.

> Một số hoạt động trong quy trình phát triển phần mềm cũng có thể được mô tả thông qua các phương pháp phát triển phần mềm chi tiết hơn và các thực hành Agile.
>
> Ví dụ bao gồm:
>
> - Acceptance test-driven development (ATDD),
> - Behavior-driven development (BDD),
> - Domain-driven design (DDD),
> - Extreme programming (XP),
> - Feature-driven development (FDD),
> - Kanban,
> - Lean IT,
> - Scrum,
> - Test-driven development (TDD).

### 2.1.1. Impact of the Software Development Lifecycle on Testing

> Ảnh hưởng của Vòng đời phát triển phần mềm đối với kiểm thử

Testing must be adapted to the SDLC to succeed. The choice of the SDLC impacts on the:

- Scope and timing of test activities (e.g., test levels and test types)
- Level of detail of test documentation
- Choice of test techniques and test approach
- Extent of test automation
- Role and responsibilities of a tester

In sequential development models, in the initial phases testers typically participate in requirement reviews, test analysis, and test design. The executable code is usually created in the later phases, so typically dynamic testing cannot be performed early in the SDLC.

In some iterative development models and incremental development models, it is assumed that each iteration delivers a working prototype or product increment. This implies that in each iteration both static testing and dynamic testing may be performed at all test levels. Frequent delivery of increments requires fast feedback and extensive regression testing.

Agile software development assumes that change may occur throughout the project. Therefore,
lightweight work product documentation and extensive test automation to make regression testing easier are favored in agile projects. Also, most of the manual testing tends to be done using experience-based test techniques (see Section 4.4) that do not require extensive prior test analysis and design.

> Để kiểm thử đạt hiệu quả, hoạt động kiểm thử cần được điều chỉnh phù hợp với SDLC. Việc lựa chọn mô hình SDLC sẽ ảnh hưởng đến
>
> - Phạm vi và thời điểm thực hiện các hoạt động kiểm thử, chẳng hạn như các test level và test type.
> - Mức độ chi tiết của tài liệu kiểm thử
> - Việc lựa chọn test technique và test approach
> - Mức độ áp dụng test automation
> - Vvai trò và trách nhiệm của tester.
>
> Trong các mô hình phát triển tuần tự (sequential development models), ở các giai đoạn đầu của dự án, tester thường tham gia vào việc review requirement, thực hiện test analysis và test design. Phần executable code thường chỉ được tạo ra ở các giai đoạn sau, vì vậy dynamic testing thường không thể được thực hiện sớm trong SDLC.
>
> Trong một số mô hình phát triển lặp (iterative development models) và mô hình phát triển gia tăng (incremental development models), mỗi iteration được giả định sẽ cung cấp một prototype hoặc một product increment có thể hoạt động được. Điều này có nghĩa là trong mỗi iteration, cả static testing và dynamic testing đều có thể được thực hiện ở tất cả các test level. Việc phát hành increment thường xuyên đòi hỏi phải có phản hồi nhanh và thực hiện regression testing ở mức độ rộng.
>
> Phát triển phần mềm Agile giả định rằng thay đổi có thể xảy ra trong suốt quá trình thực hiện dự án. Vì vậy, trong các dự án Agile, tài liệu work product thường được giữ ở mức gọn nhẹ và test automation được áp dụng rộng rãi nhằm giúp regression testing trở nên dễ dàng hơn. Ngoài ra, phần lớn manual testing trong Agile thường được thực hiện bằng các experience-based test technique (xem mục 4.4), là những kỹ thuật không yêu cầu quá nhiều hoạt động test analysis và test design trước đó.

### 2.1.2. Software Development Lifecycle and Good Testing Practices

> Vòng đời phát triển phần mềm và các thực hành kiểm thử tốt

Good testing practices, independent of the chosen SDLC model, include the following:

- For every software development activity, there is a corresponding test activity, so that all development activities are subject to quality control
- Different test levels (see chapter 2.2.1) have specific and different test objectives, which allows for testing to be appropriately comprehensive while avoiding redundancy
- Test analysis and design for a given test level begins during the corresponding development phase of the SDLC, so that testing can adhere to the principle of early testing (see section 1.3)
- Testers are involved in reviewing work products as soon as drafts of these work products are available, so that this earlier testing and defect detection can support shift left (see section 2.1.5).

> Các thực hành kiểm thử tốt, không phụ thuộc vào mô hình SDLC được lựa chọn, bao gồm những nội dung sau:
>
> Đối với mỗi hoạt động phát triển phần mềm, sẽ tồn tại một hoạt động kiểm thử tương ứng, nhằm đảm bảo rằng mọi hoạt động phát triển đều được kiểm soát chất lượng.
>
> Các test level khác nhau (xem mục 2.2.1) có những test objective riêng biệt và khác nhau. Điều này giúp hoạt động kiểm thử đạt được mức độ đầy đủ phù hợp mà vẫn tránh được sự trùng lặp không cần thiết.
>
> Hoạt động test analysis và test design cho một test level cụ thể sẽ bắt đầu trong giai đoạn phát triển tương ứng của SDLC, nhằm đảm bảo testing tuân theo nguyên tắc early testing (xem mục 1.3).
>
> Tester cũng tham gia vào việc review các work product ngay khi bản nháp của chúng xuất hiện, để việc kiểm thử và phát hiện defect sớm này có thể hỗ trợ cho shift left (xem mục 2.1.5).

### 2.1.3. Testing as a Driver for Software Development

> Kiểm thử như một động lực cho phát triển phần mềm

TDD, ATDD and BDD are similar development approaches, where tests are defined as a means of directing development. Each of these approaches implements the principle of early testing (see section 1.3) and follows shift left (see section 2.1.5), since the tests are defined before the code is written. They support an iterative development model. These approaches are characterized as follows:

**Test-Driven Development (TDD):**

- Directs the coding through test cases (instead of extensive software design) (Beck 2003)
- Tests are written first, then the code is written to satisfy the tests, and then the tests and code are refactored

**Acceptance Test-Driven Development (ATDD) (see section 4.5.3):**

- Derives tests from acceptance criteria as part of the system design process (Gärtner 2011)
- Tests are written before the part of the application is developed to satisfy the tests

**Behavior-Driven Development (BDD):**

- Expresses the desired behavior of an application with test cases written in a simple form of natural language, which is easy to understand by stakeholders – usually using the
  Given/When/Then format (Chelimsky 2010)
- Test cases should then automatically be translated into executable tests

For all the above approaches, tests may persist as automated tests to ensure the code quality in future adaptions / refactoring.

> TDD, ATDD và BDD là những phương pháp phát triển tương tự nhau, trong đó test được định nghĩa như một phương tiện để định hướng quá trình phát triển phần mềm.
>
> Mỗi phương pháp này đều áp dụng nguyên tắc early testing (xem mục 1.3) và tuân theo tư tưởng shift left (xem mục 2.1.5), bởi vì test được định nghĩa trước khi code được viết.
>
> Các phương pháp này hỗ trợ mô hình phát triển lặp (iterative development model).
>
> Những phương pháp này có các đặc điểm như sau:
>
> **Test-Driven Development (TDD)**
>
> - Định hướng việc coding thông qua test case thay vì dựa vào thiết kế phần mềm quá chi tiết (Beck 2003).
> - Test được viết trước, sau đó code được viết để đáp ứng các test đó, và cuối cùng cả test lẫn code sẽ được refactor.
>
> **Acceptance Test-Driven Development (ATDD)** (xem mục 4.5.3)
>
> - Test được xây dựng từ acceptance criteria như một phần của quá trình thiết kế hệ thống (Gärtner 2011).
> - Test được viết trước khi phần tương ứng của ứng dụng được phát triển để đáp ứng các test đó.
>
> **Behavior-Driven Development (BDD)**
>
> - Mô tả hành vi mong muốn của ứng dụng bằng các test case được viết dưới dạng ngôn ngữ tự nhiên đơn giản, giúp stakeholder dễ hiểu — thường sử dụng định dạng Given/When/Then (Chelimsky 2010).
> - Sau đó, các test case này sẽ được tự động chuyển đổi thành executable test.
>
> Đối với tất cả các phương pháp trên, test có thể tiếp tục được duy trì dưới dạng automated test nhằm đảm bảo chất lượng code trong các lần thay đổi hoặc refactor về sau.

### 2.1.4. DevOps and Testing

> DevOps và Kiểm thử

DevOps is an organizational approach aiming to create synergy by getting development (including testing) and operations to work together to achieve a set of common goals. DevOps requires a cultural shift within an organization to bridge the gaps between development (including testing) and operations while treating their functions with equal value. DevOps promotes team autonomy, fast feedback, integrated toolchains, and technical practices like continuous integration (CI) and continuous delivery (CD). This enables the teams to build, test and release high-quality code faster through a DevOps delivery pipeline (Kim 2016).

From the testing perspective, some of the benefits of DevOps are as follows:

- Fast feedback on the code quality, and whether changes adversely affect existing code
- CI promotes shift left in testing (see section 2.1.5) by encouraging developers to submit high quality code accompanied by component tests and static analysis

- Automated processes are promoted like CI/CD that facilitates establishing stable test environments
- The visibility on non-functional quality characteristics increases (e.g., performance efficiency, reliability)
- Automation through a delivery pipeline reduces the need for repetitive manual testing
- The risk of regression is minimized due to the scale and range of automated regression tests

DevOps is not without its risks and challenges, which include:

- The DevOps delivery pipeline must be defined and established
- CI / CD tools must be introduced and maintained
- Test automation requires additional resources and may be difficult to establish and maintain

Although DevOps comes with a high level of automated testing, manual testing – especially from the user's perspective – will still be needed.

> DevOps là một cách tiếp cận ở cấp độ tổ chức nhằm tạo ra sự cộng hưởng bằng cách giúp bộ phận development (bao gồm cả testing) và operations phối hợp làm việc với nhau để đạt được các mục tiêu chung.
>
> DevOps đòi hỏi một sự thay đổi về văn hóa trong tổ chức nhằm thu hẹp khoảng cách giữa development (bao gồm testing) và operations, đồng thời xem các chức năng của họ có giá trị ngang nhau.
>
> DevOps thúc đẩy:
>
> - Tính tự chủ của team,
> - Phản hồi nhanh,
> - Chuỗi công cụ tích hợp (integrated toolchains),
> - Các thực hành kỹ thuật như continuous integration (CI) và continuous delivery (CD).
>
> Điều này cho phép các team xây dựng, kiểm thử và release code chất lượng cao nhanh hơn thông qua DevOps delivery pipeline (Kim 2016).
>
> Từ góc nhìn kiểm thử, một số lợi ích của DevOps bao gồm:
>
> - Phản hồi nhanh về chất lượng code và việc các thay đổi có ảnh hưởng tiêu cực đến code hiện có hay không.
> - CI thúc đẩy shift left trong testing (xem mục 2.1.5) bằng cách khuyến khích developer submit code chất lượng cao kèm theo component test và static analysis.
> - Các quy trình tự động như CI/CD được thúc đẩy, từ đó hỗ trợ việc thiết lập các test environment ổn định.
> - Khả năng quan sát các đặc tính chất lượng phi chức năng (non-functional quality characteristics) được tăng lên, ví dụ như: performance efficiency, reliability.
> - Automation thông qua delivery pipeline giúp giảm nhu cầu thực hiện các công việc manual testing lặp đi lặp lại.
> - Nguy cơ regression được giảm thiểu nhờ quy mô và phạm vi rộng của automated regression test.
>
> Tuy nhiên, DevOps cũng đi kèm với một số rủi ro và thách thức, bao gồm:
>
> - DevOps delivery pipeline cần được định nghĩa và thiết lập.
> - Các công cụ CI/CD cần được triển khai và bảo trì.
> - Test automation đòi hỏi thêm nguồn lực và có thể khó thiết lập cũng như khó duy trì.
>
> Mặc dù DevOps đi kèm với mức độ automated testing rất cao, manual testing — đặc biệt từ góc nhìn của người dùng — vẫn luôn cần thiết.

### 2.1.5. Shift Left

The principle of early testing (see section 1.3) is sometimes referred to as shift left because it is an approach where testing is performed earlier in the SDLC. Shift left basically suggests that testing should be done earlier (e.g., not waiting for code to be implemented or for components to be integrated), but it does not mean that testing later in the SDLC should be neglected.

There are some good practices that illustrate how to achieve a “shift left” in testing, which include:

- Reviewing the specification from the perspective of testers. These review activities on specifications often find potential defects, such as ambiguities, incompleteness, and inconsistencies
- Writing test cases before the code is written and have the code run in a test harness during code implementation
- Using CI and even better CD as it comes with fast feedback and automated component tests to accompany source code when it is submitted to the code repository
- Completing static analysis of source code prior to dynamic testing, or as part of an automated process
- Performing non-functional testing starting at the component test level, where possible. This is a form of shift left as these non-functional test types tend to be performed later in the SDLC when a complete system and a representative test environment are available

Shift left might result in extra training, effort and/or costs earlier in the process but is expected to save efforts and/or costs later in the process.

For shift left it is important that stakeholders are convinced and bought into this concept.

> Nguyên tắc early testing (xem mục 1.3) đôi khi còn được gọi là shift left vì đây là cách tiếp cận mà trong đó hoạt động testing được thực hiện sớm hơn trong SDLC.
>
> Về cơ bản, shift left đề xuất rằng testing nên được thực hiện sớm hơn (ví dụ: không chờ đến khi code được implement xong hoặc các component được tích hợp hoàn chỉnh mới bắt đầu testing). Tuy nhiên, điều đó không có nghĩa là testing ở các giai đoạn sau của SDLC sẽ bị xem nhẹ hoặc bỏ qua.
>
> Có một số thực hành tốt minh họa cho cách áp dụng shift left trong testing, bao gồm:
>
> - Review specification từ góc nhìn của tester. Các hoạt động review specification này thường giúp phát hiện các defect tiềm ẩn như: ambiguity (mơ hồ), incompleteness (thiếu sót), inconsistency (không nhất quán).
> - Viết test case trước khi code được viết và để code chạy trong test harness trong quá trình implement code.
> - Sử dụng CI và tốt hơn nữa là CD, vì chúng cung cấp phản hồi nhanh cùng với automated component test đi kèm source code khi code được submit vào code repository.
> - Thực hiện static analysis cho source code trước khi dynamic testing diễn ra hoặc như một phần của quy trình tự động hóa.
> - Thực hiện non-functional testing bắt đầu từ component test level khi có thể. Đây cũng là một dạng shift left vì các loại non-functional testing thường chỉ được thực hiện ở giai đoạn muộn hơn của SDLC, khi đã có hệ thống hoàn chỉnh và test environment mang tính đại diện.
>
> Shift left có thể làm tăng: chi phí, công sức hoặc nhu cầu đào tạo ở giai đoạn đầu của quy trình phát triển. Tuy nhiên, cách tiếp cận này được kỳ vọng sẽ giúp tiết kiệm công sức và chi phí ở các giai đoạn sau.
>
> Để áp dụng shift left hiệu quả, điều quan trọng là stakeholder cần được thuyết phục và đồng thuận với khái niệm này.

### 2.1.6. Retrospectives and Process Improvement

> Retrospectives và Cải tiến quy trình (Process Improvement)

Retrospectives are often held at the end of a project or an iteration, at a release milestone, or can be held when needed. The timing and organization of the retrospectives depend on the particular SDLC model being followed. In these meetings the participants (not only testers, but also e.g., developers, architects, product owner, business analysts) discuss:

- What was successful, and should be retained?
- What was not successful and could be improved?
- How to incorporate the improvements and retain the successes in the future?

The results should be recorded and are normally part of the test completion report (see section 5.3.2). Retrospectives are critical for the successful implementation of continuous improvement, and it is important that any recommended improvements are followed up.
Typical benefits for testing include:

- Increased test effectiveness / efficiency (e.g., by implementing suggestions for process improvement)
- Increased quality of testware (e.g., by jointly reviewing the test processes)
- Team bonding and learning (e.g., as a result of the opportunity to raise issues and propose improvement points)
- Improved quality of the test basis (e.g., as deficiencies in the extent and quality of the requirements could be addressed and solved)
- Better cooperation between development and testing (e.g., as collaboration is reviewed and optimized regularly)

> Retrospective thường được tổ chức vào cuối một dự án, cuối một iteration, tại các release milestone hoặc bất cứ khi nào cần thiết.
>
> Thời điểm và cách tổ chức retrospective phụ thuộc vào mô hình SDLC cụ thể đang được áp dụng.
>
> Trong các buổi họp này, những người tham gia (không chỉ tester mà còn có thể bao gồm developer, architect, product owner, business analyst, v.v.) sẽ cùng thảo luận:
>
> - Điều gì đã thành công và nên được duy trì?
> - Điều gì chưa thành công và có thể được cải thiện?
> - Làm thế nào để áp dụng các cải tiến và duy trì những điểm thành công trong tương lai?
>
> Kết quả của retrospective cần được ghi lại và thường là một phần của test completion report (xem mục 5.3.2).
>
> Retrospective đóng vai trò rất quan trọng trong việc triển khai continuous improvement thành công, và điều quan trọng là các cải tiến được đề xuất phải được theo dõi và thực hiện tiếp theo.
>
> Một số lợi ích điển hình đối với testing bao gồm:
>
> - Tăng hiệu quả và hiệu suất kiểm thử (ví dụ: thông qua việc áp dụng các đề xuất cải tiến quy trình).
> - Nâng cao chất lượng của testware (ví dụ: bằng cách cùng nhau review các test process).
> - Tăng sự gắn kết trong team và thúc đẩy học hỏi (ví dụ: nhờ có cơ hội nêu ra vấn đề và đề xuất các điểm cải tiến).
> - Cải thiện chất lượng của test basis (ví dụ: các thiếu sót về phạm vi và chất lượng của requirement có thể được xác định và giải quyết).
> - Tăng cường sự hợp tác giữa development và testing (ví dụ: thông qua việc collaboration được review và tối ưu thường xuyên).
