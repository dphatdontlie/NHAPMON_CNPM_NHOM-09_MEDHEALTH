# ADR-0001: Đề xuất backend chia module và phân lớp

- Ngày lập: 25/11/2026.
- Người phụ trách đề xuất: Nguyễn Hữu Huy.
- Trạng thái: **Proposed**, chưa được nhóm chấp thuận.
- Ticket: SCRUM-16.

## Bối cảnh

Nhóm có 5 thành viên, đang chuẩn bị môi trường và cần một luồng khám có thể tích hợp, demo và giải thích được. Stack và mã nguồn kế thừa chưa được xác nhận. Đặt lịch cần giao dịch để không vượt sức chứa; ba nền tảng là định hướng cần cân đối.

## Phương án đề xuất

Một backend có các module Identity, Directory, Scheduling, Clinical, Notifications, Administration và Audit; bên trong phân lớp API, service, repository. Dùng CSDL quan hệ để quản lý liên kết và giao dịch. Web là client đầu tiên; client khác chỉ bổ sung khi được nhóm chốt.

## Lý do

Ít thành phần cài đặt hơn microservice, thuận tiện kiểm tra giao dịch đặt lịch và phù hợp việc học theo nhóm nhỏ. Ranh giới module giúp phân chia công việc mà vẫn dùng cùng hợp đồng API.

## Hệ quả

- Cần thống nhất quy ước module, tên dữ liệu và xử lý lỗi trước khi code.
- Backend được triển khai như một đơn vị; thay đổi cần regression phần liên quan.
- Không chọn framework/CSDL cụ thể chỉ bằng ADR này. Kiểm tra code cũ và môi trường 5 máy trước quyết định stack.

## Điều kiện xem lại

Yêu cầu học phần bắt buộc một kiến trúc khác, mã nguồn kế thừa không phù hợp, hoặc nhu cầu triển khai độc lập có bằng chứng rõ.

## Ghi nhận sau họp

| Nội dung | Giá trị |
| --- | --- |
| Người tham dự | Chưa ghi nhận |
| Kết luận | Chờ review |
| Stack và phiên bản | Chưa chốt |
| Ngày xác nhận | Chưa có |
