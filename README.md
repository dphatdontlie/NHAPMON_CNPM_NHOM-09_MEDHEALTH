# MedHealth

Hệ thống hỗ trợ đặt lịch khám, quản lý hồ sơ khám và nhắc nhở chăm sóc sức khỏe, tiếp tục phát triển từ định hướng MedHealth 2024–2025 để phục vụ học phần Nhập môn Công nghệ phần mềm.

## Trạng thái

Repository đang chuẩn bị tài liệu Sprint 0. Các tài liệu thiết kế là bản đề xuất ngày 25/11/2026, cần nhóm review. Hiện chưa có mã ứng dụng, stack được xác nhận hoặc kết quả kiểm thử chức năng. Sprint 1 bắt đầu phát triển tính năng.

## Nhóm thực hiện

| Thành viên | Đầu việc Sprint 0 | Ticket |
| --- | --- | --- |
| Phát Đăng Nguyễn | Review backlog, chốt phạm vi, điều phối | [SCRUM-53](https://medhealth-app.atlassian.net/browse/SCRUM-53) |
| Thái Trương | Yêu cầu và use case | [SCRUM-15](https://medhealth-app.atlassian.net/browse/SCRUM-15) |
| Nguyễn Hữu Huy | Kiến trúc, dữ liệu, API | [SCRUM-16](https://medhealth-app.atlassian.net/browse/SCRUM-16) |
| Trần Đức Hoàng Hải | GitHub và môi trường | [SCRUM-17](https://medhealth-app.atlassian.net/browse/SCRUM-17) |
| Diễm Hương Hoàng Thị | Wireframe và test case | [SCRUM-54](https://medhealth-app.atlassian.net/browse/SCRUM-54) |

## Tài liệu

- [Bắt đầu và chia file cho từng người](docs/team-handoff.md).
- [Review Product Backlog](docs/backlog-review.md).
- [Yêu cầu và use case](docs/requirements.md).
- [Kiến trúc và dữ liệu](docs/architecture.md).
- [Kế hoạch API](docs/api-plan.md).
- [Quyết định kiến trúc đề xuất](docs/decisions/0001-architecture.md).
- [Hướng dẫn clone và setup](docs/setup.md).
- [Sơ đồ chỉnh sửa được](docs/diagrams/README.md).
- [Phác thảo giao diện](docs/wireframes/README.md).
- [Test case](docs/test-cases.md), [bảng Excel](docs/test-cases.xlsx).
- [Quy trình đóng góp](CONTRIBUTING.md).

## Clone repository

```powershell
git clone https://github.com/dphatdontlie/CNPM.git
cd CNPM
```

Mở thư mục bằng VS Code > File > Open Folder. Nếu đã có bản clone, dùng thư mục đó thay vì clone vào bên trong nó.

## Chạy ứng dụng

Chưa áp dụng vì repository chưa có mã ứng dụng. Sau khi nhóm chốt công nghệ, Hải bổ sung project mẫu và cập nhật [hướng dẫn setup](docs/setup.md) với phiên bản công cụ, lệnh cài, lệnh chạy và địa chỉ truy cập đã kiểm chứng. Không tự dùng lệnh npm khi chưa có project tương ứng.

## Phạm vi đề xuất

Ưu tiên Website với tài khoản, bác sĩ, lịch hẹn và hồ sơ khám. Nhắc nhở, Mobile và Desktop được lên kế hoạch theo năng lực, yêu cầu học phần và kết quả review. Chỉ dùng dữ liệu giả lập khi phát triển và demo.

Theo dõi công việc trên [Jira MedHealth](https://medhealth-app.atlassian.net/jira/software/projects/SCRUM/boards/1/backlog). Jira giữ phân công, điểm và trạng thái công việc sau khi nhóm điều chỉnh.
