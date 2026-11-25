# Hợp đồng API sơ bộ MedHealth

Phụ trách: Nguyễn Hữu Huy. Đây là thiết kế dự kiến để review, không phải API đã triển khai. Prefix đề xuất `/api/v1`; phải kiểm tra code kế thừa trước khi áp dụng. JSON field và status là đề xuất cần đồng bộ với requirements, CSDL và test.

## 1. Quy ước

- Server xác thực và kiểm tra vai trò/chủ tài nguyên cho mỗi thao tác riêng tư.
- Thời gian trao đổi dùng ISO 8601 có UTC offset, lưu UTC; client hiển thị Asia/Bangkok.
- Danh sách dùng `page`, `pageSize`, giới hạn pageSize tại server; response đề xuất `{items, page, pageSize, total}`.
- Request sai dữ liệu: 400; thiếu phiên: 401; thiếu quyền: 403; không tồn tại/không được lộ tài nguyên: 404 theo chính sách chốt; xung đột: 409.
- Với truy cập chéo hồ sơ/lịch, có thể dùng 404 để tránh lộ dữ liệu. Nhóm phải chọn chính sách nhất quán và kiểm thử không trả nội dung tài nguyên dù chọn 403 hay 404.
- Không trả hash, token của người khác, lỗi SQL hay stack trace. Cơ chế cookie/session/token chưa chốt.
- `version` bắt buộc cho thay đổi cần kiểm soát xung đột. Server kiểm tra toàn bộ quy tắc dù client đã kiểm tra.

## 2. Các endpoint đề xuất

| Method | Path | Quyền | Dữ liệu chính | Kết quả đề xuất | Jira |
| --- | --- | --- | --- | --- | --- |
| POST | /auth/register | Khách | fullName, email, password | 201 tạo tài khoản; 409 email trùng | SCRUM-1 |
| POST | /auth/login | Khách | email, password | 200 và phiên theo cơ chế chọn; 401 thông tin sai | SCRUM-5 |
| POST | /auth/logout | Đã đăng nhập | Phiên hiện tại | 204 kết thúc phiên | SCRUM-5 |
| GET | /me | Đã đăng nhập | Không | 200 thông tin tài khoản an toàn | SCRUM-5 |
| GET | /specialties | Công khai theo phạm vi chốt | page, pageSize | 200 danh mục đang hoạt động | SCRUM-19 |
| GET | /doctors | Công khai theo phạm vi chốt | q, specialtyId, facility, page, pageSize | 200 danh sách bác sĩ | SCRUM-6 |
| GET | /doctors/{id} | Công khai theo phạm vi chốt | id | 200 hồ sơ công khai | SCRUM-7 |
| POST | /doctors | Quản trị hoặc vai trò danh mục được cấp | Hồ sơ bác sĩ, specialtyId | 201 bác sĩ mới | SCRUM-19 |
| PATCH | /doctors/{id} | Vai trò danh mục được cấp | Trường được sửa, isActive | 200 dữ liệu cập nhật | SCRUM-19 |
| GET | /doctors/{id}/availability | Công khai theo phạm vi chốt | date | 200 khung giờ và số chỗ còn | SCRUM-21 |
| POST | /availability | Vai trò quản lý lịch được cấp | doctorId, startAt, endAt, capacity | 201 hoặc 409 ca giao nhau | SCRUM-20 |
| PATCH | /availability/{id} | Vai trò quản lý lịch được cấp | Trường được sửa, version | 200 hoặc 409 khi xung đột/ảnh hưởng lịch | SCRUM-20 |
| POST | /appointments | Bệnh nhân | availabilityId, reason; Idempotency-Key header | 201 mã lịch; 409 hết chỗ; retry trả lại kết quả đã lưu | SCRUM-23 |
| GET | /me/appointments | Bệnh nhân | status, from, to, page, pageSize | 200 lịch thuộc mình | SCRUM-24 |
| GET | /appointments/{id} | Chủ lịch hoặc nhân viên đúng quyền | id | 200 chi tiết lịch trong quyền | SCRUM-24 |
| POST | /appointments/{id}/cancel | Chủ lịch trong điều kiện chốt | reason, version | 200 trạng thái mới | SCRUM-25 |
| POST | /appointments/{id}/reschedule | Chủ lịch trong điều kiện chốt | availabilityId, version; Idempotency-Key | 200 lịch mới nhất hoặc 409, giữ lịch gốc | SCRUM-25 |
| GET | /reception/appointments | Tiếp nhận | date, doctorId, status, page, pageSize | 200 danh sách được phép xem | SCRUM-26 |
| POST | /appointments/{id}/confirm | Tiếp nhận | version | 200 Confirmed | SCRUM-26 |
| POST | /appointments/{id}/reject | Tiếp nhận | reason, version | 200 Rejected | SCRUM-26 |
| POST | /appointments/{id}/check-in | Tiếp nhận | version | 200 CheckedIn | SCRUM-26 |
| GET | /doctor/appointments | Bác sĩ | date, status, page, pageSize | 200 lịch được giao | SCRUM-27 |
| POST | /appointments/{id}/start | Bác sĩ được giao | version | 200 InProgress | SCRUM-27 |
| POST | /appointments/{id}/complete | Bác sĩ được giao | version | 200 Completed | SCRUM-27 |
| GET/PATCH | /me/patient-profile | Bệnh nhân | Trường tự khai được phép | 200 hồ sơ thuộc mình | SCRUM-29 |
| PUT | /appointments/{id}/encounter | Bác sĩ được giao | symptoms, findings, assessment, plan, followUpAt, version | 200/201 nháp bệnh án | SCRUM-30 |
| POST | /encounters/{id}/publish | Bác sĩ được giao | version | 200 bản công bố | SCRUM-30 |
| GET | /me/encounters | Bệnh nhân | from, to, page, pageSize | 200 chỉ các lần đã công bố | SCRUM-31 |
| GET | /encounters/{id} | Chủ hồ sơ đã công bố hoặc bác sĩ đúng quyền | id | 200 nội dung được phép xem | SCRUM-31 |
| GET/PATCH | /me/notification-preferences | Bệnh nhân | enabled, leadMinutes | 200 tùy chọn | SCRUM-35 |
| GET | /me/notifications | Bệnh nhân | unreadOnly, page, pageSize | 200 thông báo của mình | SCRUM-37 |
| POST | /me/notifications/{id}/read | Chủ thông báo | id | 200/204, thao tác lặp không đổi sai số đếm | SCRUM-37 |
| PATCH | /admin/users/{id} | Quản trị | isActive hoặc role, reason | 200; bảo vệ quản trị cuối cùng | SCRUM-38 |
| GET | /reports/appointments | Vai trò báo cáo được cấp | from, to, doctorId, facility | 200 số liệu tổng hợp | SCRUM-39 |

Worker tạo/gửi nhắc là thành phần nội bộ, chưa mở endpoint công khai để người dùng tự kích hoạt scheduler.

## 3. Ví dụ đặt lịch

Request minh họa, không dùng ID hoặc tài khoản thật:

```http
POST /api/v1/appointments
Content-Type: application/json
Idempotency-Key: demo-booking-request-001
```

```json
{"availabilityId":"slot-demo-001","reason":"Khám theo lịch hẹn demo"}
```

```json
{"id":"appointment-demo-001","code":"MH-DEMO-001","status":"Pending","version":1}
```

Không nhận `patientId` tùy ý từ bệnh nhân để đặt dưới danh tính người khác; xác định bệnh nhân từ phiên đăng nhập. Idempotency key gắn người gọi, thao tác và payload; key trùng nhưng payload khác cần bị từ chối. Thời hạn giữ key và mã phản hồi retry phải chốt khi triển khai.

## 4. Dạng lỗi đề xuất

```json
{"error":{"code":"SLOT_FULL","message":"Khung giờ vừa hết chỗ. Vui lòng chọn khung khác.","fields":{},"requestId":"demo-request-001"}}
```

Client dùng `code` để xử lý, `message` để hiển thị; `requestId` hỗ trợ tra log đã loại dữ liệu nhạy cảm. `fields` ánh xạ lỗi theo tên trường. Danh sách code, schema chính thức/OpenAPI và chính sách auth sẽ được bổ sung sau review.
