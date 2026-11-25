# Clone và chuẩn bị môi trường MedHealth

Phụ trách: Trần Đức Hoàng Hải. Ticket: [SCRUM-17](https://medhealth-app.atlassian.net/browse/SCRUM-17).

## 1. Trạng thái hiện tại

Repository chứa tài liệu chuẩn bị. Chưa có ứng dụng, dependency manifest, migration hoặc lệnh khởi động được nhóm kiểm chứng. Chỉ phần clone và làm việc với tài liệu áp dụng ngay.

## 2. Clone trên Windows

1. Cài [Git](https://git-scm.com/downloads) và [VS Code](https://code.visualstudio.com/).
2. Đăng nhập GitHub, nhận lời mời vào repository nếu repository yêu cầu quyền truy cập.
3. Mở PowerShell tại thư mục muốn lưu bài, kiểm tra `git --version`.
4. Chạy:

   ```powershell
   git clone https://github.com/dphatdontlie/CNPM.git
   cd CNPM
   ```

5. Mở VS Code > File > Open Folder > chọn thư mục CNPM.
6. Chạy `git status`, kiểm tra đang ở đúng repository. Nếu đã có bản clone, dùng bản đó, không clone lồng bên trong.
7. Thực hiện quy trình nhánh và PR trong [CONTRIBUTING](../CONTRIBUTING.md).

## 3. Chuẩn bị project mẫu sau khi chốt công nghệ

Hải và Huy cập nhật bảng này trước khi yêu cầu các thành viên cài framework/CSDL:

| Nội dung | Trạng thái |
| --- | --- |
| Mã nguồn cũ có thể kế thừa | Chưa xác nhận |
| Công nghệ frontend và phiên bản | Chờ nhóm quyết định |
| Công nghệ backend và phiên bản | Chờ nhóm quyết định |
| Hệ quản trị CSDL và phiên bản | Chờ nhóm quyết định |
| Lệnh cài dependency | Bổ sung sau khi có project |
| File cấu hình và biến môi trường | Bổ sung theo stack, không ghi secret thật |
| Lệnh migration/seed dữ liệu demo | Bổ sung nếu có CSDL |
| Lệnh khởi động | Chưa có |
| URL mở trong trình duyệt | Chưa có |
| Lệnh build/kiểm thử | Bổ sung theo stack |

Khi có mã nguồn, tạo `.env.example` nếu cần, bổ sung hướng dẫn từ bản clone sạch và thêm ảnh/log chạy thành công vào ticket. Lệnh trong README phải khớp file cấu hình thực tế. Chưa chạy thử thì ghi “chưa kiểm chứng”.

## 4. Kiểm tra 5 máy

| Thành viên | Clone | Chạy project mẫu | Máy/phiên bản công cụ | Bằng chứng hoặc lỗi |
| --- | --- | --- | --- | --- |
| Phát Đăng Nguyễn | Đã có bản clone trên máy đang làm việc, kiểm tra 25/11/2026 | Chưa có ứng dụng để thử | Chưa ghi nhận đầy đủ | Cần tự ghi bằng chứng setup sau khi có project |
| Thái Trương | Chưa ghi nhận | Chưa thực hiện | Chưa ghi nhận | Chờ cập nhật |
| Nguyễn Hữu Huy | Chưa ghi nhận | Chưa thực hiện | Chưa ghi nhận | Chờ cập nhật |
| Trần Đức Hoàng Hải | Chưa ghi nhận | Chưa thực hiện | Chưa ghi nhận | Chờ cập nhật |
| Diễm Hương Hoàng Thị | Chưa ghi nhận | Chưa thực hiện | Chưa ghi nhận | Chờ cập nhật |

## 5. Xử lý lỗi thường gặp

| Hiện tượng | Cách kiểm tra |
| --- | --- |
| Không nhận lệnh `git` | Đóng/mở PowerShell sau khi cài Git, kiểm tra cài đặt và PATH |
| Repository not found hoặc thiếu quyền | Kiểm tra URL, tài khoản đang đăng nhập và lời mời cộng tác |
| Thư mục CNPM đã tồn tại | Mở thư mục đó và kiểm tra `git status`; không ghi đè hoặc xóa để clone lại |
| Không push được | Kiểm tra quyền, đăng nhập và nhánh đang làm; gửi nguyên thông báo lỗi cho Hải |
| `git pull --ff-only` báo không thể fast-forward | Dừng lại, nhờ Hải/Đăng kiểm tra lịch sử nhánh, không force push |
| Lệnh cài/chạy không tồn tại | Kiểm tra project đã được thêm và README đã cập nhật; không đoán lệnh |
