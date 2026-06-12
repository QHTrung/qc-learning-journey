# 6. Test tools

### Table of contents

- [6. Test tools](#6-test-tools)
  - [Table of contents](#table-of-contents)
  - [Keywords](#keywords)
  - [6.1. Tool Support for Testing](#61-tool-support-for-testing)
  - [6.2. Benefits and Risks of Test Automation](#62-benefits-and-risks-of-test-automation)

## Keywords

| Keyword         | Translate               |
| --------------- | :---------------------- |
| test automation | tự động hóa kiểm nghiệm |

## 6.1. Tool Support for Testing

> Công cụ hỗ trợ kiểm thử

Test tools support and facilitate many test activities. Examples include, but are not limited to:

- Test management tools – increase the test process efficiency by facilitating management of the SDLC, requirements, tests, defects, configuration
- Static testing tools – support the tester in performing reviews and static analysis
- Test design and test implementation tools – facilitate generation of test cases, test data and test procedures
- Test execution and test coverage tools – facilitate automated test execution and coverage measurement
- Non-functional testing tools – allow the tester to perform non-functional testing that is difficult or impossible to perform manually
- DevOps tools – support the DevOps delivery pipeline, workflow tracking, automated build process(es), CI/CD
- Collaboration tools – facilitate communication
- Tools supporting scalability and deployment standardization (e.g., virtual machines, containerization tools)
- Any other tool that assists in testing (e.g., a spreadsheet is a test tool in the context of testing)

> Các công cụ kiểm thử hỗ trợ và tạo điều kiện thuận lợi cho nhiều hoạt động kiểm thử. Các ví dụ bao gồm, nhưng không giới hạn ở:
>
> - Công cụ quản lý kiểm thử (Test management tools): Tăng hiệu suất của quy trình kiểm thử bằng cách hỗ trợ quản lý SDLC (vòng đời phát triển phần mềm), yêu cầu (requirements), kiểm thử, lỗi (defects) và cấu hình.
> - Công cụ kiểm thử tĩnh (Static testing tools): Hỗ trợ kiểm thử viên trong việc thực hiện đánh giá (reviews) và phân tích tĩnh (static analysis).
> - Công cụ thiết kế và triển khai kiểm thử (Test design and test implementation tools): Hỗ trợ tạo các kịch bản kiểm thử (test cases), dữ liệu kiểm thử (test data) và quy trình kiểm thử (test procedures).
> - Công cụ thực thi và đo độ bao phủ kiểm thử (Test execution and test coverage tools): Hỗ trợ tự động hóa thực thi kiểm thử và đo lường độ bao phủ (coverage).
> - Công cụ kiểm thử phi chức năng (Non-functional testing tools): Cho phép kiểm thử viên thực hiện các loại kiểm thử phi chức năng mà nếu làm thủ công sẽ rất khó hoặc không thể.
> - Công cụ DevOps (DevOps tools): Hỗ trợ đường ống bàn giao DevOps (DevOps delivery pipeline), theo dõi tiến độ công việc (workflow tracking), các quy trình đóng gói tự động (automated build), và CI/CD.
> - Công cụ cộng tác (Collaboration tools): Hỗ trợ việc giao tiếp và tương tác.
> - Công cụ hỗ trợ mở rộng và chuẩn hóa triển khai (Tools supporting scalability and deployment standardization): Ví dụ như máy ảo (virtual machines), công cụ đóng gói container (containerization tools).
> - Bất kỳ công cụ nào khác giúp ích cho việc kiểm thử: Ví dụ, một bảng tính (spreadsheet/Excel) cũng được coi là một công cụ kiểm thử trong ngữ cảnh của hoạt động kiểm thử.

| Nhóm công cụ                                    | Tool                                                                                                                                 |
| ----------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------- |
| Quản lý kiểm thử (Test management)              | Jira (kèm plugin Xray/Zephyr), TestRail, Azure DevOps, HP ALM (Quality Center).                                                      |
| Kiểm thử tĩnh (Static testing)                  | SonarQube (quét code tự động), Checkstyle, ESLint, hoặc chính các công cụ Review Code như GitHub, GitLab.                            |
| Thiết kế & triển khai (Design & Implementation) | Postman (thiết kế request API), Mockaroo (tạo dữ liệu giả - test data), các công cụ vẽ Mindmap (XMind, Miro) để brainstorm kịch bản. |
| Thực thi & đo độ bao phủ (Execution & Coverage) | Automation: Selenium, Playwright, Cypress, Katalon Studio. <br/> Coverage: JaCoCo (cho Java), Istanbul (cho JavaScript).             |
| Kiểm thử phi chức năng (Non-functional)         | Hiệu năng (Performance): JMeter, LoadRunner, K6.<br/> Bảo mật (Security): OWASP ZAP, Burp Suite.                                     |
| Công cụ DevOps (DevOps tools)                   | Jenkins, GitLab CI/CD, GitHub Actions, Bamboo.                                                                                       |
| Công cụ cộng tác (Collaboration)                | Slack, Microsoft Teams, Confluence (lưu tài liệu nội bộ).                                                                            |
| Mở rộng & Chuẩn hóa (Scalability & Deployment)  | Docker (đóng gói container môi trường test), Kubernetes (K8s), VMware, VirtualBox.                                                   |
| Công cụ hỗ trợ khác                             | Google Sheets / MS Excel (dùng viết test case, checklist nhanh), Notepad++, Snipping Tool (chụp màn hình lỗi).                       |

## 6.2. Benefits and Risks of Test Automation

> Lợi ích và rủi ro của tự động hóa kiểm thử:

Simply acquiring a tool does not guarantee success. Each new tool will require effort to achieve real and lasting benefits (e.g., for tool introduction, maintenance and training). There are also some risks, which need analysis and mitigation.

Potential benefits of using test automation include:

- Time saved by reducing repetitive manual work (e.g., execute regression tests, re-enter the same test data, compare expected results vs actual results, and check against coding standards)
- Prevention of simple human errors through greater consistency and repeatability (e.g., tests are consistently derived from requirements, test data is created in a systematic manner, and tests are executed by a tool in the same order with the same frequency)
- More objective assessment (e.g., coverage) and providing measures that are too complicated for humans to determine
- Easier access to information about testing to support test management and test reporting (e.g., statistics, graphs, and aggregated data about test progress, failure rates, and test execution duration)
- Reduced test execution times to provide earlier defect detection, faster feedback and faster time to market
- More time for testers to design new, deeper and more effective tests

Potential risks of using test automation include:

- Unrealistic expectations about the benefits of a tool (including functionality and ease of use).
- Inaccurate estimations of time, costs, effort required to introduce a tool, maintain test scripts and change the existing manual test process.
- Using a test tool when manual testing is more appropriate.
- Relying on a tool too much, e.g., ignoring the need of human critical thinking.
- The dependency on the tool vendor which may go out of business, retire the tool, sell the tool to a different vendor or provide poor support (e.g., responses to queries, upgrades, and defect fixes).
- Using an open-source software which may be abandoned, meaning that no further updates are available, or its internal components may require quite frequent updates as a further development.
- The automation tool is not compatible with the development platform.
- Choosing an unsuitable tool that did not comply with the regulatory requirements and/or safety standards

> Việc đơn thuần sở hữu một công cụ không đảm bảo cho sự thành công. Mỗi công cụ mới đều đòi hỏi nỗ lực để đạt được những lợi ích thực tế và lâu dài (ví dụ: chi phí cho việc áp dụng công cụ, bảo trì và đào tạo). Bên cạnh đó cũng có những rủi ro cần phải được phân tích và giảm thiểu.

> Các lợi ích tiềm năng của tự động hóa kiểm thử:
>
> - Tiết kiệm thời gian: Giảm thiểu các công việc thủ công lặp đi lặp lại (ví dụ: thực thi kiểm thử hồi quy (regression tests), nhập lại cùng một dữ liệu kiểm thử, so sánh kết quả thực tế với kết quả mong đợi, và kiểm tra các tiêu chuẩn viết code).
> - Tránh các lỗi sơ đẳng của con người: Nhờ vào tính nhất quán và khả năng lặp lại cao hơn (ví dụ: các bài kiểm thử luôn được xây dựng bám sát theo yêu cầu, dữ liệu kiểm thử được tạo một cách có hệ thống, và các bài kiểm thử được công cụ thực thi theo cùng một thứ tự và tần suất).
> - Đánh giá khách quan hơn: Đưa ra các chỉ số đo lường (ví dụ: độ bao phủ - coverage) mà con người quá khó hoặc không thể tự xác định một cách chính xác.
> - Tiếp cận thông tin kiểm thử dễ dàng hơn: Hỗ trợ đắc lực cho quản lý và báo cáo kiểm thử (ví dụ: các số liệu thống kê, biểu đồ, dữ liệu tổng hợp về tiến độ kiểm thử, tỷ lệ lỗi (failure rates), và thời gian thực thi).
> - Rút ngắn thời gian thực thi kiểm thử: Giúp phát hiện lỗi sớm hơn, phản hồi nhanh hơn và đẩy nhanh tốc độ đưa sản phẩm ra thị trường (time to market).
> - Tối ưu hóa nguồn lực: Kiểm thử viên có nhiều thời gian hơn để thiết kế các kịch bản kiểm thử mới, sâu hơn và hiệu quả hơn.

> Các rủi ro tiềm năng của tự động hóa kiểm thử:
>
> - Kỳ vọng không thực tế: Lầm tưởng về lợi ích của công cụ (bao gồm cả tính năng và độ dễ sử dụng).
> - Ước lượng sai lệch: Đánh giá không chính xác về thời gian, chi phí và nỗ lực cần thiết để triển khai công cụ, bảo trì kịch bản kiểm thử (test scripts) và thay đổi quy trình kiểm thử thủ công hiện tại.
> - Áp dụng sai ngữ cảnh: Sử dụng công cụ tự động hóa khi việc kiểm thử thủ công (manual testing) mang lại hiệu quả cao hơn.
> - Quá phụ thuộc vào công cụ: Quên đi tầm quan trọng của tư duy phản biện (critical thinking) từ con người.
> - Phụ thuộc vào nhà cung cấp công cụ: Rủi ro khi họ ngừng hoạt động, khai tử công cụ, bán lại cho bên khác hoặc hỗ trợ kém (ví dụ: chậm phản hồi, không cập nhật hoặc không sửa lỗi công cụ).
> - Rủi ro từ phần mềm mã nguồn mở (open-source): Dự án có thể bị bỏ rơi (không còn bản cập nhật), hoặc các thành phần nội bộ của nó yêu cầu cập nhật quá thường xuyên để chạy theo các hướng phát triển mới.
> - Không tương thích: Công cụ tự động hóa không tương thích với nền tảng phát triển phần mềm (development platform).
> - Chọn sai công cụ: Lựa chọn công cụ không tuân thủ các yêu cầu pháp lý (regulatory requirements) và/hoặc các tiêu chuẩn an toàn (safety standards).
