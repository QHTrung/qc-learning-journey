b# 6. Test tools

### Table of contents

- [Keywords](#keywords)
- [6.1. Tool Support for Testing](#61-tool-support-for-testing)

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
