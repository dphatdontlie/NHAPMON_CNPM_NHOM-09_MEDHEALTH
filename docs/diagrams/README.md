# Sơ đồ MedHealth

Các sơ đồ là bản đề xuất 25/11/2026, chờ nhóm review. File `.drawio` dùng để chỉnh sửa; `.svg` dùng để xem trên GitHub/trình duyệt.

| Sơ đồ | Người phụ trách | Bản chỉnh sửa | Bản xem |
| --- | --- | --- | --- |
| Use case | Thái Trương | [use-case.drawio](use-case.drawio) | [use-case.svg](use-case.svg) |
| Kiến trúc | Nguyễn Hữu Huy | [architecture.drawio](architecture.drawio) | [architecture.svg](architecture.svg) |
| ERD | Nguyễn Hữu Huy | [erd.drawio](erd.drawio) | [erd.svg](erd.svg) |

## Cách sửa

1. Mở [diagrams.net](https://app.diagrams.net/), chọn lưu trên thiết bị nếu được hỏi.
2. Chọn mở file từ thiết bị và chọn `.drawio` tương ứng.
3. Kiểm tra nội dung với `requirements.md` và `architecture.md`, sửa nhãn, quan hệ hoặc bố cục.
4. Lưu lại file `.drawio`, xuất SVG để cập nhật bản xem đi kèm. Giữ cả hai trong cùng PR.

Trong ERD, mũi tên đi từ bảng chứa FK tới bảng chứa PK được tham chiếu. Nhãn N:1 hoặc 1:1 chỉ quan hệ đề xuất; schema vật lý sẽ chốt khi chọn CSDL. Sơ đồ use case chỉ thể hiện nhóm chức năng chính, quy tắc quyền chi tiết đọc trong tài liệu yêu cầu.
