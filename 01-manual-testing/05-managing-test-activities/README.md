# 5. Managing the Test Activitie

### Table of contents

- [5. Managing the Test Activitie](#5-managing-the-test-activitie)
  - [Table of contents](#table-of-contents)
  - [Keywords](#keywords)
  - [5.1. Test Planning](#51-test-planning)
    - [5.1.1. Purpose and Content of a Test Plan](#511-purpose-and-content-of-a-test-plan)
    - [5.1.2. Tester's Contribution to Iteration and Release Planning](#512-testers-contribution-to-iteration-and-release-planning)
    - [5.1.3. Entry Criteria and Exit Criteria](#513-entry-criteria-and-exit-criteria)
    - [5.1.4. Estimation Techniques](#514-estimation-techniques)

## Keywords

| Keyword                | Translate                 |
| ---------------------- | :------------------------ |
| defect management      | Quản lý lỗi               |
| defect report          | Báo cáo lỗi / Bug report  |
| entry criteria         | Tiêu chí bắt đầu          |
| exit criteria          | Tiêu chí kết thúc         |
| product risk           | Rủi ro sản phẩm           |
| project risk           | Rủi ro dự án              |
| risk                   | Rủi ro                    |
| risk analysis          | Phân tích rủi ro          |
| risk assessment        | Đánh giá rủi ro           |
| risk control           | Kiểm soát rủi ro          |
| risk identification    | Nhận diện rủi ro          |
| risk level             | Mức độ rủi ro             |
| risk management        | Quản lý rủi ro            |
| risk mitigation        | Giảm thiểu rủi ro         |
| risk monitoring        | Giám sát rủi ro           |
| risk-based testing     | Kiểm thử dựa trên rủi ro  |
| test approach          | Tiếp cận kiểm thử         |
| test completion report | Báo cáo kết thúc kiểm thử |
| test control           | Điều khiển kiểm thử       |
| test monitoring        | Giám sát kiểm thử         |
| test plan              | Kế hoạch kiểm thử         |
| test planning          | Lập kế hoạch kiểm thử     |
| test progress report   | Báo cáo tiến độ kiểm thử  |
| test pyramid           | Kim tự tháp kiểm thử      |
| test strategy          | Chiến lược kiểm thử       |
| testing quadrants      | Các phân hạn kiểm thử     |

## 5.1. Test Planning

> Lập kế hoạch kiểm thử

### 5.1.1. Purpose and Content of a Test Plan

> Mục đích và nội dung của Test Plan

A test plan describes the test objectives, resources and processes for a test project. A test plan:

- Documents the means and schedule for achieving test objectives
- Helps to ensure that the performed test activities will meet the established criteria
- Serves as a means of communication with team members and other stakeholders
- Demonstrates that testing will adhere to the existing test policy and test strategy (or explains why the testing will deviate from them)

Test planning guides the testers’ thinking and forces the testers to confront the future challenges related to risks, schedules, people, tools, costs, effort, etc. The process of preparing a test plan is a useful way to think through the efforts needed to achieve the test objectives.

The typical content of a test plan includes:

- Context of testing (e.g., test scope, test objectives, test basis)
- Assumptions and constraints of the test project
- Stakeholders (e.g., roles, responsibilities, relevance to testing, hiring and training needs)
- Communication (e.g., forms and frequency of communication, documentation templates)
- Risk register (e.g., product risks, project risks)
- Test approach (e.g., test levels, test types, test techniques, test deliverables, entry criteria and exit criteria, independence of testing, metrics to be collected, test data requirements, test environment requirements, deviations from the test policy and test strategy)
- Budget and schedule

More details about the test plan and its content can be found in the ISO/IEC/IEEE 29119-3 standard.

> Một kế hoạch kiểm thử (test plan) mô tả các mục tiêu, nguồn lực và quy trình kiểm thử cho một dự án kiểm thử. Một kế hoạch kiểm thử giúp:
>
> - Ghi lại bằng văn bản các phương tiện và lịch trình để đạt được các mục tiêu kiểm thử.
> - Giúp đảm bảo rằng các hoạt động kiểm thử được thực hiện sẽ đáp ứng các tiêu chí đã đề ra.
> - Đóng vai trò như một phương tiện giao tiếp với các thành viên trong đội ngũ và các bên liên quan khác.
> - Chứng minh rằng việc kiểm thử sẽ tuân thủ chính sách kiểm thử (test policy) và chiến lược kiểm thử (test strategy) hiện có (hoặc giải thích lý do tại sao việc kiểm thử lại có sự khác biệt so với chúng).
>
> Hoạt động lập kế hoạch kiểm thử (test planning) định hướng tư duy của kiểm thử viên và buộc họ phải đối mặt với những thách thức trong tương lai liên quan đến rủi ro, lịch trình, con người, công cụ, chi phí, công sức, v.v. Quá trình chuẩn bị một kế hoạch kiểm thử là một cách hữu ích để suy nghĩ thấu đáo về những nỗ lực cần thiết nhằm đạt được các mục tiêu kiểm thử.
>
> Nội dung điển hình của một kế hoạch kiểm thử bao gồm:
>
> - Bối cảnh kiểm thử (Ví dụ: phạm vi kiểm thử, mục tiêu kiểm thử, cơ sở kiểm thử - test basis).
> - Các giả định và ràng buộc của dự án kiểm thử.
> - Các bên liên quan (Ví dụ: vai trò, trách nhiệm, mức độ liên quan đến kiểm thử, nhu cầu tuyển dụng và đào tạo).
> - Giao tiếp (Ví dụ: các hình thức và tần suất giao tiếp, các biểu mẫu tài liệu).
> - Danh mục rủi ro (Ví dụ: rủi ro sản phẩm, rủi ro dự án).
> - Tiếp cận kiểm thử (Ví dụ: các mức độ kiểm thử, loại kiểm thử, kỹ thuật kiểm thử, các sản phẩm bàn giao kiểm thử, tiêu chí bắt đầu và tiêu chí kết thúc, tính độc lập của kiểm thử, các chỉ số cần thu thập, yêu cầu về dữ liệu kiểm thử, yêu cầu về môi trường kiểm thử, các điểm khác biệt so với chính sách và chiến lược kiểm thử).
> - Ngân sách và lịch trình.
>
> Thông tin chi tiết hơn về kế hoạch kiểm thử và nội dung của nó có thể được tìm thấy trong tiêu chuẩn ISO/IEC/IEEE 29119-3.

### 5.1.2. Tester's Contribution to Iteration and Release Planning

> Đóng góp của kiểm thử viên vào việc lập kế hoạch cho Phiên bản phát hành và Vòng lặp

In iterative SDLCs, typically two kinds of planning occur: release planning and iteration planning.

Release planning looks ahead to the release of a product, defines and re-defines the product backlog, and may involve refining larger user stories into a set of smaller user stories. It also serves as the basis for the test approach and test plan across all iterations. Testers involved in release planning participate in writing testable user stories and acceptance criteria (see section 4.5), participate in project and quality risk analyses (see section 5.2), estimate test effort associated with user stories (see section 5.1.4), determine the test approach, and plan the testing for the release.

Iteration planning looks ahead to the end of a single iteration and is concerned with the iteration backlog. Testers involved in iteration planning participate in the detailed risk analysis of user stories, determine the testability of user stories, break down user stories into tasks (particularly testing tasks), estimate test effort for all testing tasks, and identify and refine functional and non-functional aspects of the test object.

> Trong các mô hình vòng đời phát triển phần mềm (SDLC) theo cụm/lặp (iterative SDLCs), thông thường sẽ có hai loại hình lập kế hoạch diễn ra: lập kế hoạch phát hành (release planning) và lập kế hoạch phân đoạn (iteration planning).
>
> **Lập kế hoạch phát hành (Release planning)** hướng tầm nhìn đến việc phát hành của một sản phẩm, định nghĩa và định nghĩa lại danh sách yêu cầu tồn đọng của sản phẩm (product backlog), và có thể bao gồm việc làm mịn các câu chuyện người dùng (user stories) lớn thành một tập hợp các câu chuyện người dùng nhỏ hơn. Nó cũng phục vụ như một cơ sở cho tiếp cận kiểm thử (test approach) và kế hoạch kiểm thử (test plan) xuyên suốt tất cả các phân đoạn. Các kiểm thử viên tham gia vào việc lập kế hoạch phát hành sẽ tham gia vào việc viết các câu chuyện người dùng và tiêu chí nghiệm thu có thể kiểm thử được (see section 4.5), tham gia vào các hoạt động phân tích rủi ro dự án và rủi ro chất lượng (see section 5.2), ước lượng công sức kiểm thử liên quan đến các câu chuyện người dùng (see section 5.1.4), xác định tiếp cận kiểm thử, và lập kế hoạch kiểm thử cho đợt phát hành đó.
>
> **Lập kế hoạch phân đoạn (Iteration planning)** hướng tầm nhìn đến thời điểm kết thúc của một phân đoạn đơn lẻ và liên quan trực tiếp đến danh sách yêu cầu tồn đọng của phân đoạn đó (iteration backlog). Các kiểm thử viên tham gia vào việc lập kế hoạch phân đoạn sẽ tham gia vào việc phân tích rủi ro chi tiết của các câu chuyện người dùng, xác định tính có thể kiểm thử (testability) của các câu chuyện người dùng, chia nhỏ các câu chuyện người dùng thành các tác vụ (đặc biệt là các tác vụ kiểm thử), ước lượng công sức kiểm thử cho tất cả các tác vụ kiểm thử, cũng như nhận diện và làm mịn các khía cạnh chức năng và phi chức năng của đối tượng kiểm thử.

### 5.1.3. Entry Criteria and Exit Criteria

> Tiêu chí đầu vào và tiêu chí đầu ra

Entry criteria define the preconditions for undertaking a given activity. If entry criteria are not met, it is likely that the activity will prove to be more difficult, time-consuming, costly, and riskier. Exit criteria define what must be achieved to declare an activity completed. Entry criteria and exit criteria should be defined for each test level, and will differ based on the test objectives.

Typical entry criteria include: availability of resources (e.g., people, tools, environments, test data, budget, time), availability of testware (e.g., test basis, testable requirements, user stories, test cases), and initial quality level of a test object (e.g., all smoke tests have passed).

Typical exit criteria include: measures of thoroughness (e.g., achieved level of coverage, number of unresolved defects, defect density, number of failed test cases), and binary “yes/no” criteria (e.g., planned tests have been executed, static testing has been performed, all defects found are reported, all regression tests are automated).

Running out of time or budget can also be viewed as valid exit criteria. Even without other exit criteria being satisfied, it can be acceptable to end testing under such circumstances, if the stakeholders have reviewed and accepted the risk to go live without further testing.

In Agile software development, exit criteria are often called Definition of Done, defining the team’s objective metrics for a releasable item. Entry criteria that a user story must fulfill to start the development and/or testing activities are called Definition of Ready.

> Tiêu chí bắt đầu (entry criteria) định nghĩa các điều kiện tiên quyết để thực hiện một hoạt động cụ thể. Nếu các tiêu chí bắt đầu không được đáp ứng, hoạt động đó có khả năng sẽ trở nên khó khăn hơn, tốn thời gian hơn, tốn kém hơn và rủi ro hơn. Tiêu chí kết thúc (exit criteria) định nghĩa những gì phải đạt được để tuyên bố một hoạt động đã hoàn thành. Tiêu chí bắt đầu và tiêu chí kết thúc nên được định nghĩa cho từng mức độ kiểm thử (test level), và sẽ khác nhau dựa trên các mục tiêu kiểm thử.
>
> Các tiêu chí bắt đầu điển hình bao gồm:
>
> - Sự sẵn sàng của các nguồn lực: (Ví dụ: con người, công cụ, môi trường, dữ liệu kiểm thử, ngân sách, thời gian).
> - Sự sẵn sàng của các sản phẩm kiểm thử (testware): (Ví dụ: cơ sở kiểm thử - test basis, các yêu cầu có thể kiểm thử được, các câu chuyện người dùng, các kịch bản kiểm thử).
> - Mức độ chất lượng ban đầu của đối tượng kiểm thử: (Ví dụ: tất cả các bài kiểm thử khói - smoke tests đã vượt qua).
>
> Các tiêu chí kết thúc điển hình bao gồm:
>
> - Các phép đo về độ triệt để: (Ví dụ: mức độ bao phủ đã đạt được, số lượng khuyết tật chưa được giải quyết, mật độ khuyết tật - defect density, số lượng kịch bản kiểm thử bị thất bại).
> - Các tiêu chí nhị phân "đúng/sai" (yes/no criteria): (Ví dụ: các bài kiểm thử theo kế hoạch đã được thực thi, kiểm thử tĩnh đã được thực hiện, tất cả các khuyết tật tìm thấy đã được báo cáo, tất cả các bài kiểm thử hồi quy đã được tự động hóa).
>
> Việc hết thời gian hoặc cạn kiệt ngân sách cũng có thể được xem là các tiêu chí kết thúc hợp lệ. Ngay cả khi các tiêu chí kết thúc khác chưa được thỏa mãn, việc kết thúc kiểm thử trong các hoàn cảnh như vậy vẫn có thể được chấp nhận, nếu các bên liên quan đã xem xét và chấp nhận rủi ro để đưa sản phẩm lên môi trường vận hành (go live) mà không cần kiểm thử thêm.
>
> Trong phát triển phần mềm theo phương pháp Agile, tiêu chí kết thúc thường được gọi là Định nghĩa về sự hoàn thành (Definition of Done - DoD), định nghĩa các chỉ số khách quan của đội ngũ đối với một hạng mục có thể phát hành. Các tiêu chí bắt đầu mà một câu chuyện người dùng phải đáp ứng để bắt đầu các hoạt động phát triển và/hoặc kiểm thử được gọi là Định nghĩa về sự sẵn sàng (Definition of Ready - DoR).

### 5.1.4. Estimation Techniques

> Các kỹ thuật ước lượng

Test effort estimation involves predicting the amount of test-related work needed to meet the test objectives of a test project. It is important to make it clear to the stakeholders that the estimate is based on a number of assumptions and is always subject to estimation error. Estimation for small tasks is usually more accurate than for the large ones. Therefore, when estimating a large task, it can be decomposed into a set of smaller tasks which then in turn can be estimated.

In this syllabus, the following four estimation techniques are described.

Estimation based on ratios. In this metrics-based technique, figures are collected from previous projects within the organization, which makes it possible to derive “standard” ratios for similar projects. The ratios of an organization’s own projects (e.g., taken from historical data) are generally the best source to use in the estimation process. These standard ratios can then be used to estimate the test effort for the new project. For example, if in the previous project the development-to-test effort ratio was 3:2, and in the current project the development effort is expected to be 600 person-days, the test effort can be estimated to be 400 person-days

Extrapolation. In this metrics-based technique, measurements are made as early as possible in the current project to gather the data. Having enough observations, the effort required for the remaining work can be approximated by extrapolating this data (usually by applying a mathematical model). This method is very suitable in iterative SDLCs. For example, the team may extrapolate the test effort in the forthcoming iteration as the averaged effort from the last three iterations.

Wideband Delphi. In this iterative, expert-based technique, experts make experience-based estimations. Each expert, in isolation, estimates the effort. The results are collected and if there are deviations of an expert’s estimate that are out of range of the agreed upon boundaries, the experts discuss their current estimates. Each expert is then asked to make a new estimation based on that feedback, again in isolation. This process is repeated until a consensus is reached. Planning Poker is a variant of Wideband Delphi, commonly used in Agile software development. In Planning Poker, estimates are usually made using cards with numbers that represent the effort size.

Three-point estimation. In this expert-based technique, three estimations are made by the experts: the most optimistic estimation (a), the most likely estimation (m) and the most pessimistic estimation (b). The final estimate (E) is their weighted arithmetic mean. In the most popular version of this technique, the estimate is calculated as E = (a + 4*m + b) / 6. The advantage of this technique is that it allows the experts to calculate the measurement error: SD = (b – a) / 6. For example, if the estimates (in personhours) are: a=6, m=9 and b=18, then the final estimation is 10±2 person-hours (i.e., between 8 and 12 person-hours), because E = (6 + 4*9 + 18) / 6 = 10 and SD = (18 – 6) / 6 = 2.

See (Kan 2003, Koomen 2006, Westfall 2009) for these and many other test estimation techniques.

> Ước lượng công sức kiểm thử (test effort estimation) bao gồm việc dự đoán khối lượng công việc liên quan đến kiểm thử cần thiết để đáp ứng các mục tiêu kiểm thử của một dự án. Điều quan trọng là phải làm rõ với các bên liên quan rằng con số ước lượng dựa trên một số giả định và luôn có sai số ước lượng. Việc ước lượng cho các tác vụ nhỏ thường chính xác hơn so với các tác vụ lớn. Do đó, khi ước lượng một tác vụ lớn, nó có thể được chia nhỏ thành một tập hợp các tác vụ nhỏ hơn để lần lượt ước lượng.
>
> Trong giáo trình này, bốn kỹ thuật ước lượng sau đây được mô tả:
>
> - **Ước lượng dựa trên tỷ lệ (Estimation based on ratios)**: Trong kỹ thuật dựa trên chỉ số (metrics-based) này, các số liệu được thu thập từ các dự án trước đó trong tổ chức, giúp rút ra các tỷ lệ "tiêu chuẩn" cho các dự án tương tự. Tỷ lệ từ chính các dự án của tổ chức (ví dụ: lấy từ dữ liệu lịch sử) nhìn chung là nguồn tốt nhất để sử dụng trong quá trình ước lượng. Các tỷ lệ tiêu chuẩn này sau đó có thể được sử dụng để ước lượng công sức kiểm thử cho dự án mới. Ví dụ: nếu trong dự án trước, tỷ lệ công sức giữa phát triển và kiểm thử là 3:2, và trong dự án hiện tại, công sức phát triển dự kiến là 600 ngày-người, thì công sức kiểm thử có thể được ước lượng là 400 ngày-người.
> - **Ngoại suy (Extrapolation)**: Trong kỹ thuật dựa trên chỉ số này, các phép đo được thực hiện càng sớm càng tốt trong dự án hiện tại để thu thập dữ liệu. Khi có đủ các dữ liệu quan sát, công sức cần thiết cho phần công việc còn lại có thể được tính xấp xỉ bằng cách ngoại suy dữ liệu này (thường bằng cách áp dụng một mô hình toán học). Phương pháp này rất phù hợp trong các mô hình vòng đời phát triển phần mềm (SDLC) theo cụm/lặp. Ví dụ: đội ngũ có thể ngoại suy công sức kiểm thử trong phân đoạn sắp tới bằng mức công sức trung bình của ba phân đoạn gần nhất.
> - **Wideband Delphi:** Trong kỹ thuật lặp đi lặp lại dựa trên chuyên gia (expert-based) này, các chuyên gia sẽ đưa ra các ước lượng dựa trên kinh nghiệm. Mỗi chuyên gia, một cách độc lập, tự ước lượng công sức. Các kết quả được thu thập và nếu có những sai lệch trong ước lượng của một chuyên gia vượt ra ngoài ranh giới đã thỏa thuận, các chuyên gia sẽ thảo luận về các ước lượng hiện tại của họ. Mỗi chuyên gia sau đó được yêu cầu đưa ra một ước lượng mới dựa trên phản hồi đó, một lần nữa thực hiện một cách độc lập. Quá trình này được lặp lại cho đến khi đạt được sự đồng thuận. Planning Poker là một biến thể của Wideband Delphi, thường được sử dụng trong phát triển phần mềm theo phương pháp Agile. Trong Planning Poker, các ước lượng thường được thực hiện bằng cách sử dụng các thẻ bài có các con số đại diện cho quy mô công sức.
> - **Ước lượng ba điểm (Three-point estimation)**: Trong kỹ thuật dựa trên chuyên gia này, ba mức ước lượng được các chuyên gia đưa ra: ước lượng lạc quan nhất (a), ước lượng có khả năng xảy ra nhất (m) và ước lượng bi quan nhất (b). Ước lượng cuối cùng (E) là trung bình cộng có trọng số của chúng. Trong phiên bản phổ biến nhất của kỹ thuật này, giá trị ước lượng được tính theo công thức $E = \frac{a + 4m + b}{6}$. Ưu điểm của kỹ thuật này là nó cho phép các chuyên gia tính toán được sai số của phép đo: $SD = \frac{b - a}{6}$. Ví dụ: nếu các mức ước lượng (tính theo giờ-người) là: a=6, m=9 và b=18, thì ước lượng cuối cùng là $10 \pm 2$ giờ-người (tức là trong khoảng từ 8 đến 12 giờ-người), vì $E = \frac{6 + 4 \times 9 + 18}{6} = 10$ và $SD = \frac{18 - 6}{6} = 2$.
>
> Xem (Kan 2003, Koomen 2006, Westfall 2009) để biết thêm về các kỹ thuật này và nhiều kỹ thuật ước lượng kiểm thử khác.
