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
  - [2.2. Test Levels and Test Types](#22-test-levels-and-test-types)
    - [2.2.1 Test Levels](#221-test-levels)
    - [2.2.2. Test Types](#222-test-types)
    - [2.2.3. Confirmation Testing and Regression Testing](#223-confirmation-testing-and-regression-testing)
  - [2.3. Maintenance Testing](#23-maintenance-testing)

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
>
> [Tham khảo thêm về SDLC](/01-manual-testing/02-testing-throughout-SDLC/SDLC/README.md)

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

## 2.2. Test Levels and Test Types

Test levels are groups of test activities that are organized and managed together. Each test level is an instance of the test process, performed in relation to software at a given phase of development, from individual components to complete systems or, where applicable, systems of systems.

Test levels are related to other activities within the SDLC. In sequential SDLC models, the test levels are often defined such that the exit criteria of one level are part of the entry criteria for the next level. In some iterative models, this may not apply. Development activities may span through multiple test levels. Test levels may overlap in time.

Test types are groups of test activities related to specific quality characteristics and most of those test activities can be performed at every test level.

> Cấp độ kiểm thử (Test levels) là các nhóm hoạt động kiểm thử được tổ chức và quản lý cùng nhau. Mỗi cấp độ kiểm thử là một thể hiện (instance) của quy trình kiểm thử, được thực hiện đối với phần mềm ở một giai đoạn phát triển nhất định, từ các thành phần riêng lẻ cho đến các hệ thống hoàn chỉnh hoặc các hệ thống của hệ thống (systems of systems) nếu có.
>
> Các cấp độ kiểm thử có mối quan hệ với các hoạt động khác trong vòng đời phát triển phần mềm (SDLC). Trong các mô hình SDLC tuần tự, các cấp độ kiểm thử thường được định nghĩa sao cho tiêu chí thoát (exit criteria) của một cấp độ sẽ là một phần của tiêu chí vào (entry criteria) cho cấp độ kế tiếp. Trong một số mô hình lặp (iterative models), điều này có thể không áp dụng. Các hoạt động phát triển có thể kéo dài qua nhiều cấp độ kiểm thử. Các cấp độ kiểm thử có thể trùng lặp nhau về mặt thời gian.
>
> Loại kiểm thử (Test types) là các nhóm hoạt động kiểm thử liên quan đến các đặc tính chất lượng cụ thể, và hầu hết các hoạt động kiểm thử đó đều có thể được thực hiện ở mọi cấp độ kiểm thử.

### 2.2.1 Test Levels

> Các cấp độ kiểm thử

In this syllabus, the following five test levels are described:

- **Component testing (also known as unit testing)** focuses on testing components in isolation. It often requires specific support, such as test harnesses or unit test frameworks. Component testing is normally performed by developers in their development environments.

- **Component integration testing (also known as unit integration testing)** focuses on testing the interfaces and interactions between components. Component integration testing is heavily dependent on the integration strategy like bottom-up, top-down or big-bang.

- **System testing** focuses on the overall behavior and capabilities of an entire system or product, often including functional testing of end-to-end tasks and the non-functional testing of quality characteristics. For some non-functional quality characteristics, it is preferable to test them on a complete system in a representative test environment (e.g., usability). Using simulations of subsystems is also possible. System testing may be performed by an independent test team, and is related to specifications for the system.

- **System integration testing** focuses on testing the interfaces of the system under test and other systems and external services. System integration testing requires suitable test environments preferably similar to the operational environment.

- **Acceptance testing** focuses on validation and on demonstrating readiness for deployment, which means that the system fulfills the user’s business needs. Ideally, acceptance testing should be performed by the intended users. The main forms of acceptance testing are: user acceptance testing (UAT), operational acceptance testing, contractual acceptance testing and regulatory acceptance testing, alpha testing and beta testing.

Test levels are distinguished by the following non-exhaustive list of attributes, to avoid overlapping of test activities:

- Test object
- Test objectives
- Test basis
- Defects and failures
- Approach and responsibilities

> Trong giáo trình này, năm cấp độ kiểm thử sau đây được mô tả:
>
> **Kiểm thử thành phần (Component testing - còn gọi là kiểm thử đơn vị / unit testing)**: Tập trung vào việc kiểm thử các thành phần một cách cô lập. Hoạt động này thường đòi hỏi sự hỗ trợ đặc biệt, chẳng hạn như các khung kiểm thử đơn vị (unit test frameworks) hoặc công cụ điều khiển kiểm thử (test harnesses). Kiểm thử thành phần thường do các lập trình viên thực hiện trong môi trường phát triển của họ.
>
> **Kiểm thử tích hợp thành phần (Component integration testing - còn gọi là kiểm thử tích hợp đơn vị / unit integration testing)**: Tập trung vào việc kiểm thử các giao diện và sự tương tác giữa các thành phần. Kiểm thử tích hợp thành phần phụ thuộc rất nhiều vào chiến lược tích hợp, chẳng hạn như từ dưới lên (bottom-up), từ trên xuống (top-down) hoặc tích hợp tổng thể (big-bang).
>
> **Kiểm thử hệ thống (System testing)**: Tập trung vào hành vi và khả năng tổng thể của toàn bộ hệ thống hoặc sản phẩm, thường bao gồm kiểm thử chức năng cho các tác vụ đầu-cuối (end-to-end) và kiểm thử phi chức năng cho các đặc tính chất lượng. Đối với một số đặc tính chất lượng phi chức năng, việc kiểm thử chúng trên một hệ thống hoàn chỉnh trong một môi trường kiểm thử mô phỏng thực tế (ví dụ: kiểm thử độ khả dụng / usability) sẽ tốt hơn. Việc sử dụng các mô phỏng của các hệ thống con cũng có thể được áp dụng. Kiểm thử hệ thống có thể được thực hiện bởi một đội ngũ kiểm thử độc lập và gắn liền với các tài liệu tả đặc tả của hệ thống.
>
> **Kiểm thử tích hợp hệ thống (System integration testing)**: Tập trung vào việc kiểm thử các giao diện giữa hệ thống đang được kiểm thử với các hệ thống khác và các dịch vụ bên ngoài. Kiểm thử tích hợp hệ thống đòi hỏi các môi trường kiểm thử phù hợp, tốt nhất là tương tự như môi trường vận hành thực tế.
>
> **Kiểm thử chấp nhận (Acceptance testing)**: Tập trung vào việc xác nhận (validation) và chứng minh sự sẵn sàng cho việc triển khai, điều này có nghĩa là hệ thống đáp ứng được các nhu cầu kinh doanh của người dùng. Lý tưởng nhất, kiểm thử chấp nhận nên được thực hiện bởi những người dùng mục tiêu. Các hình thức chính của kiểm thử chấp nhận bao gồm: kiểm thử chấp nhận người dùng (UAT), kiểm thử chấp nhận vận hành, kiểm thử chấp nhận theo hợp đồng, kiểm thử chấp nhận theo quy định pháp lý, kiểm thử alpha (alpha testing) và kiểm thử beta (beta testing).
>
> Các cấp độ kiểm thử được phân biệt bởi danh sách các thuộc tính (không giới hạn) sau đây nhằm tránh sự trùng lặp giữa các hoạt động kiểm thử:
>
> - Đối tượng kiểm thử (Test object)
> - Mục tiêu kiểm thử (Test objectives)
> - Cơ sở kiểm thử (Test basis)
> - Khuyết tật và lỗi hỏng (Defects and failures)
> - Cách tiếp cận và trách nhiệm (Approach and responsibilities)

### 2.2.2. Test Types

> Các loại kiểm thử

A lot of test types exist and can be applied in projects. In this syllabus, the following four test types are addressed:

**Functional testing** evaluates the functions that a component or system should perform. The functions are “what” the test object should do. The main objective of functional testing is checking the functional completeness, functional correctness and functional appropriateness.

**Non-functional testing** evaluates attributes other than functional characteristics of a component or system. Non-functional testing is the testing of “how well the system behaves”. The main objective of nonfunctional testing is checking the non-functional quality characteristics. The ISO/IEC 25010 standard provides the following classification of the non-functional quality characteristics:

- Performance efficiency
- Compatibility
- Usability (also known as interaction capability)
- Reliability
- Security
- Maintainability
- Portability (also known as flexibility)
- Safety

It is sometimes appropriate for non-functional testing to start early in the SDLC (e.g., as part of reviews or component testing). Many non-functional tests are derived from functional tests as they use the same functional tests, but check that while performing the function, a non-functional constraint is satisfied (e.g., checking that a function performs within a specified time, or a function can be ported to a new platform). The late discovery of non-functional defects can pose a serious threat to the success of a project. Nonfunctional testing sometimes needs a very specific test environment, such as a usability lab for usability testing.

**Black-box testing** (see section 4.2) is specification-based and derives tests from documentation not related to the internal structure of the test object. The main objective of black-box testing is checking the system's behavior against its specifications.

**White-box testing** (see section 4.3) is structure-based and derives tests from the system's implementation or internal structure (e.g., code, architecture, work flows, and data flows). The main objective of white-box testing is to cover the underlying structure by the tests to an acceptable level.

All the four above mentioned test types can be applied to all test levels, although the focus will be different at each level. Different test techniques can be used to derive test conditions and test cases for all the mentioned test types.

> Có rất nhiều loại kiểm thử tồn tại và có thể được áp dụng vào các dự án. Trong giáo trình này, bốn loại kiểm thử sau đây sẽ được đề cập:
>
> **Kiểm thử chức năng (Functional testing)**: Đánh giá các chức năng mà một thành phần hoặc hệ thống phải thực hiện. Các chức năng này chính là những gì ("what") mà đối tượng kiểm thử nên làm. Mục tiêu chính của kiểm thử chức năng là kiểm tra tính đầy đủ của chức năng (functional completeness), tính chính xác của chức năng (functional correctness) và tính phù hợp của chức năng (functional appropriateness).
>
> **Kiểm thử phi chức năng (Non-functional testing)**: Đánh giá các thuộc tính khác ngoài các đặc tính chức năng của một thành phần hoặc hệ thống. Kiểm thử phi chức năng là việc kiểm thử xem "hệ thống vận hành tốt đến mức nào" ("how well the system behaves"). Mục tiêu chính của kiểm thử phi chức năng là kiểm tra các đặc tính chất lượng phi chức năng. Tiêu chuẩn ISO/IEC 25010 cung cấp phân loại các đặc tính chất lượng phi chức năng như sau:
>
> - Hiệu quả năng suất (Performance efficiency)
> - Tính tương thích (Compatibility)
> - Tính khả dụng (Usability - còn gọi là năng lực tương tác / interaction capability)
> - Tính đáng tin cậy (Reliability)
> - Tính bảo mật (Security)
> - Tính khả bảo trì (Maintainability)
> - Tính khả chuyển (Portability - còn gọi là tính linh hoạt / flexibility)
> - Tính an toàn (Safety)
>
> Trong một số trường hợp, việc bắt đầu kiểm thử phi chức năng sớm trong vòng đời phát triển phần mềm (SDLC) là rất phù hợp (ví dụ: như một phần của hoạt động duyệt tài liệu / reviews hoặc kiểm thử thành phần). Nhiều kiểm thử phi chức năng được dẫn xuất từ các kiểm thử chức năng vì chúng sử dụng cùng các bài kiểm thử chức năng đó, nhưng nhằm mục đích kiểm tra xem trong khi thực hiện chức năng, một ràng buộc phi chức năng có được thỏa mãn hay không (ví dụ: kiểm tra xem một chức năng có thực hiện trong khoảng thời gian quy định hay không, hoặc một chức năng có thể chuyển sang một nền tảng mới hay không).
>
> Việc phát hiện muộn các khuyết tật phi chức năng có thể gây ra mối đe dọa nghiêm trọng cho sự thành công của dự án. Kiểm thử phi chức năng đôi khi cần một môi trường kiểm thử rất đặc thù, chẳng hạn như một phòng thí nghiệm khả dụng (usability lab) dành cho việc kiểm thử độ khả dụng.
>
> **Kiểm thử hộp đen (Black-box testing** - xem mục 4.2): Là phương pháp dựa trên đặc tả (specification-based) và dẫn xuất các bài kiểm thử từ tài liệu không liên quan đến cấu trúc bên trong của đối tượng kiểm thử. Mục tiêu chính của kiểm thừ hộp đen là kiểm tra hành vi của hệ thống so với các tài liệu đặc tả của nó.
>
> **Kiểm thử hộp trắng (White-box testing** - xem mục 4.3): Là phương pháp dựa trên cấu trúc (structure-based) và dẫn xuất các bài kiểm thử từ việc triển khai hoặc cấu trúc bên trong của hệ thống (ví dụ: mã nguồn, kiến trúc, luồng công việc / work flows và luồng dữ liệu / data flows). Mục tiêu chính của kiểm thử hộp trắng là bao phủ cấu trúc nền tảng bằng các bài kiểm thử đạt đến một mức độ chấp nhận được
>
> Tất cả bốn loại kiểm thử nêu trên đều có thể được áp dụng cho mọi cấp độ kiểm thử (test levels), mặc dù trọng tâm ở mỗi cấp độ sẽ khác nhau. Các kỹ thuật kiểm thử khác nhau có thể được sử dụng để dẫn xuất ra các điều kiện kiểm thử (test conditions) và kịch bản kiểm thử (test cases) cho tất cả các loại kiểm thử đã đề cập.

### 2.2.3. Confirmation Testing and Regression Testing

> Kiểm thử xác nhận và Kiểm thử hồi quy

Changes are typically made to a component or system to either enhance it by adding a new feature or to fix it by removing a defect. Testing should then also include confirmation testing and regression testing.

C**onfirmation testing** confirms that an original defect has been successfully fixed. Depending on the risk, one can test the fixed version of the software in several ways, including:

- executing all tests that previously have failed due to the defect, or, also by
- adding new tests to cover any changes that were needed to fix the defect

However, when time or money is short when fixing defects, confirmation testing might be restricted to simply exercising the test steps that should reproduce the failure caused by the defect and checking that the failure does not occur.

**Regression testing** confirms that no adverse consequences have been caused by a change, including a fix that has already been confirmation tested. These adverse consequences could affect the same component where the change was made, other components in the same system or even other connected systems. Regression testing may not be restricted to the test object itself but can also be related to the environment. It is advisable first to perform an impact analysis to recognize the extent of the regression testing. Impact analysis shows which parts of the software could be affected.

Regression test suites are run many times and generally the number of regression test cases will increase with each iteration or release, so regression testing is a strong candidate for automation. Test automation should start early in the project. Where CI is used, such as in DevOps (see section 2.1.4), it is good practice to also include automated regression tests. Depending on the situation, this may include regression tests on different test levels.

Confirmation testing and/or regression testing for the test object are needed on all test levels if defects are fixed and/or changes are made on these test levels.

> Các thay đổi thường được thực hiện đối với một thành phần hoặc hệ thống để cải tiến nó bằng cách thêm tính năng mới hoặc để sửa lỗi bằng cách loại bỏ một khuyết tật. Khi đó, việc kiểm thử cũng phải bao gồm cả kiểm thử xác nhận và kiểm thử hồi quy.
>
> **Kiểm thử xác nhận (Confirmation testing - còn gọi là re-testing)**: Xác nhận rằng khuyết tật ban đầu đã được sửa thành công. Tùy thuộc vào mức độ rủi ro, người ta có thể kiểm thử phiên bản phần mềm đã sửa lỗi theo nhiều cách, bao gồm:
>
> - Thực hiện lại tất cả các bài kiểm thử từng bị thất bại (failed) trước đó do khuyết tật gây ra, hoặc bằng cách:
> - Thêm các bài kiểm thử mới để bao phủ bất kỳ thay đổi nào cần thiết cho việc sửa khuyết tật đó.
>
> Tuy nhiên, khi thời gian hoặc ngân sách bị hạn chế trong quá trình sửa lỗi, việc kiểm thử xác nhận có thể bị giới hạn ở việc chỉ thực hiện đơn giản các bước kiểm thử vốn dĩ sẽ tái hiện lại lỗi hỏng (failure) do khuyết tật gây ra và kiểm tra xem lỗi hỏng đó còn xuất hiện nữa hay không.
>
> **Kiểm thử hồi quy (Regression testing)**: Xác nhận rằng không có hệ quả tiêu cực nào gây ra bởi một sự thay đổi, bao gồm cả một bản sửa lỗi đã được kiểm thử xác nhận trước đó. Những hệ quả tiêu cực này có thể ảnh hưởng đến chính thành phần nơi thay đổi được thực hiện, các thành phần khác trong cùng một hệ thống, hoặc thậm chí là các hệ thống kết nối khác. Kiểm thử hồi quy có thể không chỉ giới hạn ở chính đối tượng kiểm thử mà còn có thể liên quan đến môi trường. Việc thực hiện một phân tích tác động (impact analysis) trước tiên là rất nên làm để nhận diện phạm vi của việc kiểm thử hồi quy. Phân tích tác động sẽ chỉ ra những phần nào của phần mềm có thể bị ảnh hưởng.
>
> Các bộ kịch bản kiểm thử hồi quy (regression test suites) được chạy rất nhiều lần và nhìn chung số lượng kịch bản kiểm thử hồi quy (regression test cases) sẽ tăng lên sau mỗi vòng lặp hoặc mỗi phiên bản phát hành, vì vậy kiểm thử hồi quy là một ứng cử viên sáng giá cho việc tự động hóa (automation). Tự động hóa kiểm thử nên được bắt đầu sớm trong dự án. Ở những nơi sử dụng tích hợp liên tục (CI), chẳng hạn như trong DevOps (xem mục 2.1.4), việc đưa các bài kiểm thử hồi quy tự động vào quy trình cũng là một thực hành tốt. Tùy thuộc vào tình huống, điều này có thể bao gồm các bài kiểm thử hồi quy ở các cấp độ kiểm thử khác nhau.
>
> Kiểm thử xác nhận và/hoặc kiểm thử hồi quy cho đối tượng kiểm thử là cần thiết ở tất cả các cấp độ kiểm thử nếu các khuyết tật được sửa và/hoặc các thay đổi được thực hiện ở các cấp độ kiểm thử đó.

## 2.3. Maintenance Testing

> Kiểm thử bảo trì

There are different categories of maintenance, it can be corrective, adaptive to changes in the environment or improve performance or maintainability (see ISO/IEC 14764 for details), so maintenance can involve planned releases/deployments and unplanned releases/deployments (hot fixes). Impact analysis may be done before a change is made, to help decide if the change should be made, based on the potential consequences in other areas of the system. Testing the changes to an operational system includes both evaluating the success of the implementation of the change and the checking for possible regressions in parts of the system that remain unchanged (which is usually most of the system).

The scope of maintenance testing typically depends on:

- The degree of risk of the change
- The size of the existing system
- The size of the change

The triggers for maintenance and maintenance testing can be classified as follows:

- Modifications, such as planned enhancements (i.e., release-based), corrective changes or hot fixes.

- Upgrades or migrations of the operational environment, such as from one platform to another, which can require tests associated with the new environment as well as of the changed software, or tests of data conversion when data from another application is migrated into the system being maintained.

- Retirement, such as when an application reaches the end of its life. When a system is retired, this can require testing of data archiving if long data retention periods are required. Testing of restore and retrieval procedures after archiving may also be needed in the event that certain data is required during the archiving period.

> Có nhiều danh mục bảo trì khác nhau, nó có thể là bảo trì sửa lỗi (corrective), bảo trì thích ứng (adaptive) với các thay đổi của môi trường, hoặc bảo trì để cải tiến hiệu năng hoặc tính khả bảo trì (xem tiêu chuẩn ISO/IEC 14764 để biết thêm chi tiết). Do đó, bảo trì có thể bao gồm các phiên bản phát hành/triển khai theo kế hoạch và các phiên bản phát hành/triển khai không theo kế hoạch (hot fixes). Phân tích tác động (impact analysis) có thể được thực hiện trước khi đưa ra thay đổi, nhằm giúp quyết định xem có nên thực hiện thay đổi đó hay không dựa trên các hệ quả tiềm ẩn đối với các vùng khác của hệ thống. Việc kiểm thử các thay đổi đối với một hệ thống đang vận hành bao gồm cả việc đánh giá sự thành công của việc triển khai thay đổi đó và việc kiểm tra các lỗi hồi quy có thể xảy ra ở những phần hệ thống không thay đổi (vốn thường là phần lớn của hệ thống).
>
> Phạm vi của kiểm thử bảo trì thông thường phụ thuộc vào:
>
> - Mức độ rủi ro của sự thay đổi
> - Quy mô của hệ thống hiện tại
> - Quy mô của sự thay đổi
>
> Các tác nhân kích hoạt (triggers) cho việc bảo trì và kiểm thử bảo trì có thể được phân loại như sau:
>
> - Các sửa đổi (Modifications): Chẳng hạn như các cải tiến theo kế hoạch (tức là theo từng phiên bản phát hành), các thay đổi sửa lỗi hoặc các bản sửa lỗi khẩn cấp (hot fixes).
> - Nâng cấp hoặc chuyển dịch (Upgrades or migrations): Của môi trường vận hành, chẳng hạn như chuyển từ nền tảng này sang nền tảng khác; việc này có thể đòi hỏi các bài kiểm thử liên quan đến môi trường mới cũng như phần mềm đã thay đổi, hoặc kiểm thử chuyển đổi dữ liệu (data conversion) khi dữ liệu từ một ứng dụng khác được chuyển dịch vào hệ thống đang được bảo trì.
> - Ngừng hoạt động (Retirement): Chẳng hạn như khi một ứng dụng hết vòng đời sử dụng. Khi một hệ thống ngừng hoạt động, điều này có thể đòi hỏi việc kiểm thử lưu trữ dữ liệu (data archiving) nếu có yêu cầu về thời gian lưu trữ dữ liệu dài hạn. Việc kiểm thử các quy trình khôi phục (restore) và truy xuất (retrieval) sau khi lưu trữ cũng có thể cần thiết trong trường hợp một số dữ liệu nhất định được yêu cầu trong suốt giai đoạn lưu trữ.
