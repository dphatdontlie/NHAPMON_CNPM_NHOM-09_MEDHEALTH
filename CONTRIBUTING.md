# Quy trình làm việc nhóm

## Một ticket, một nhánh và một Pull Request

1. Đọc ticket Jira, xác định file cần sửa và người review.
2. Kiểm tra `git status`. Nếu còn thay đổi chưa nộp, hoàn tất hoặc lưu chúng trước khi chuyển nhánh; không dùng lệnh xóa/reset để bỏ thay đổi của người khác.
3. Khi thư mục làm việc sạch, cập nhật nhánh chính rồi tạo nhánh riêng:

   ```powershell
   git switch main
   git pull --ff-only origin main
   git switch -c codex/ten-thanh-vien-cong-viec
   ```

4. Sửa các file thuộc công việc. Đọc lại nội dung, kiểm tra liên kết và tệp đính kèm.
5. Trong VS Code > Source Control, stage đúng các file muốn nộp. Không stage `.env`, token, mật khẩu hoặc dữ liệu cá nhân.
6. Commit với mã Jira, ví dụ `SCRUM-15: bổ sung yêu cầu và use case`.
7. Publish Branch/Push. Trên GitHub, mở Pull Request từ nhánh cá nhân vào `main`.
8. PR ghi việc đã làm, cách kiểm tra và vấn đề còn mở. Gửi người review, dán link PR vào Jira.
9. Sau khi nhận xét được xử lý và nội dung được chấp nhận, người có quyền merge thực hiện merge. Thành viên còn lại cập nhật `main` trước lượt làm việc tiếp theo.

Mỗi người tự đăng nhập GitHub bằng tài khoản của mình. Khi Git yêu cầu danh tính, dùng tên và email của bản thân, không dùng thông tin của nhóm trưởng.

## Review tài liệu

- Nhóm trưởng kiểm tra phạm vi và phân công; Thái đối chiếu nghiệp vụ; Huy kiểm tra kiến trúc/dữ liệu; Hải kiểm tra khả năng setup; Hương kiểm tra giao diện và ca kiểm thử.
- Tài liệu soạn sẵn phải được người phụ trách đọc, điều chỉnh và giải thích được trước khi nộp.
- Chỉ ghi “đã họp”, “đã chạy”, “đã kiểm thử” khi có hoạt động và bằng chứng thực tế.
- Nếu có xung đột, trao đổi với người đang sửa cùng file; giữ cả nội dung cần thiết, không ghi đè toàn bộ một cách tự động.

## Kết thúc ticket

Dán vào Jira: link PR, sản phẩm, cách đã kiểm tra, người review và vấn đề còn mở. Test case chưa chạy giữ `Not run`. Không tự chuyển ticket sang hoàn thành chỉ vì tài liệu nháp đã được tạo.
