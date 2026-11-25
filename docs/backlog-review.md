# Rà soát Product Backlog MedHealth

| Thông tin | Nội dung |
| --- | --- |
| Dự án | MedHealth, phục vụ học phần Nhập môn Công nghệ phần mềm |
| Repository | https://github.com/dphatdontlie/CNPM |
| Jira | https://medhealth-app.atlassian.net/jira/software/projects/SCRUM/boards/1/backlog |
| Nhóm trưởng | Phát Đăng Nguyễn, `sluffy1612@gmail.com` |
| Ngày lập bản nháp | 25/11/2026 |
| Trạng thái | Chờ cả nhóm review và xác nhận |
| Ticket theo dõi | [SCRUM-53](https://medhealth-app.atlassian.net/browse/SCRUM-53) |

> Đây là bản chuẩn bị cho buổi review. Phân công và Story Point đã nhập trên Jira là phương án dự kiến. Tài liệu này chưa xác nhận nhóm đã họp, thành viên đã hoàn thành công việc hoặc các chức năng đã được nghiệm thu.

## 1. Yêu cầu của giảng viên

Trong tuần, nhóm cần:

- Hoàn thiện Product Backlog: xác định ưu tiên, điểm số cho từng User Story (US) và thành viên dự kiến phụ trách.
- Nghiên cứu kiến trúc hệ thống phần mềm.
- Khởi tạo project trên GitHub và clone về máy của các thành viên.
- Dùng Sprint 0 để theo dõi và phân công việc khởi tạo, setup, nghiên cứu.
- Bắt đầu phát triển tính năng từ Sprint 1.

## 2. Mục tiêu và phạm vi đề xuất

MedHealth kế thừa định hướng dự án giai đoạn 2024–2025, hỗ trợ số hóa việc đặt lịch khám, quản lý hồ sơ khám và nhắc nhở chăm sóc sức khỏe.

### 2.1. Phạm vi MVP đưa ra thảo luận

Ưu tiên hoàn thiện một luồng nghiệp vụ trên Website:

1. Bệnh nhân đăng ký, đăng nhập.
2. Bệnh nhân tìm bác sĩ và xem khung giờ còn chỗ.
3. Bệnh nhân đặt, theo dõi, đổi hoặc hủy lịch khám.
4. Nhân viên xác nhận lịch và tiếp nhận bệnh nhân.
5. Bác sĩ xem lịch được phân công, ghi nhận và hoàn tất lượt khám.
6. Bệnh nhân tra cứu hồ sơ và lịch sử khám được công bố.
7. Hệ thống hỗ trợ nhắc lịch và quản trị cơ bản theo phạm vi được nhóm chốt.

Phân quyền và bảo vệ dữ liệu phải được triển khai cùng chức năng liên quan. Dữ liệu dùng để phát triển, kiểm thử và demo là dữ liệu giả lập.

### 2.2. Phạm vi cần xác nhận trước khi cam kết

- Mức độ bắt buộc của Mobile và Desktop trong học phần.
- Có mã nguồn, dữ liệu hoặc tài liệu cũ nào có thể kế thừa.
- Deadline học phần và thời gian thực tế mỗi thành viên có thể tham gia.
- Công nghệ, hệ quản trị cơ sở dữ liệu và môi trường demo.
- Quy tắc đổi/hủy lịch, công bố bệnh án và thời điểm gửi nhắc.
- Kênh nhắc nhở: đề xuất thông báo trong ứng dụng trước; email/push cần đánh giá thêm.

Chưa đưa vào MVP các tích hợp thanh toán, bảo hiểm hoặc hệ thống bệnh viện bên ngoài nếu chưa có yêu cầu được nhóm xác nhận.

## 3. Cấu trúc backlog và cách ưu tiên

### 3.1. Phân biệt loại công việc

| Loại | Cách sử dụng | Ví dụ |
| --- | --- | --- |
| Epic | Nhóm nhiều công việc cùng mục tiêu | Đặt lịch và tiếp nhận khám |
| Story | Một nhu cầu có giá trị cho người dùng | Bệnh nhân theo dõi lịch hẹn của mình |
| Task | Công việc kỹ thuật, chuẩn bị hoặc nghiên cứu | Thiết kế ERD, setup repository |
| Subtask | Phần việc nhỏ thuộc một ticket cha | Chuẩn bị dữ liệu cho một ca kiểm thử |

Một US sử dụng mẫu: **Là [vai trò], tôi muốn [khả năng], để [lợi ích].** Tiêu chí nghiệm thu phải kiểm tra được, bao gồm trường hợp thành công và trường hợp lỗi liên quan.

Ticket [SCRUM-1](https://medhealth-app.atlassian.net/browse/SCRUM-1) hiện là Task nhưng mô tả chức năng đăng ký tài khoản; cần review việc chuyển sang Story. Ticket cũ [SCRUM-4](https://medhealth-app.atlassian.net/browse/SCRUM-4) chưa rõ nội dung, cần xác định mục đích trước khi đưa vào phạm vi thực hiện.

### 3.2. Thứ tự ưu tiên đề xuất

Bảng dưới dùng để thảo luận thứ tự thực hiện; không thay thế mức Priority của từng ticket trên Jira. Khi chốt, nhóm cập nhật cả Priority và thứ tự trên Backlog.

| Thứ tự | Nhóm công việc | Ticket tham chiếu | Lý do |
| --- | --- | --- | --- |
| 1 | Chuẩn bị yêu cầu, kiến trúc và môi trường | SCRUM-53, SCRUM-15, SCRUM-16, SCRUM-17, SCRUM-54 | Làm rõ phạm vi và chuẩn bị nền tảng trước phát triển |
| 2 | Tài khoản và phân quyền | SCRUM-1, SCRUM-5, SCRUM-18 | Điều kiện cho các chức năng có dữ liệu riêng tư |
| 3 | Bác sĩ, ca khám và khung giờ | SCRUM-19, SCRUM-6, SCRUM-7, SCRUM-20, SCRUM-21 | Cung cấp dữ liệu đầu vào cho đặt lịch |
| 4 | Đặt lịch, đổi/hủy và tiếp nhận | SCRUM-23 đến SCRUM-27 | Tạo luồng khám cốt lõi của sản phẩm |
| 5 | Hồ sơ, bệnh án và truy vết | SCRUM-29 đến SCRUM-34 | Hoàn thiện thông tin và kết quả lượt khám |
| 6 | Nhắc nhở và quản trị | SCRUM-35 đến SCRUM-40 | Hỗ trợ theo dõi lịch và vận hành |
| 7 | Mobile và Desktop | SCRUM-41 đến SCRUM-46 | Thực hiện sau khi API ổn định và phạm vi được xác nhận |
| Xuyên suốt | Kiểm thử, tài liệu và kiểm tra quyền | Tiêu chí từng ticket; SCRUM-22, SCRUM-28 và các task kiểm thử | Kiểm tra cùng từng increment, không đợi cuối dự án |
| Trước bàn giao | UAT, triển khai và báo cáo | SCRUM-47 đến SCRUM-52 | Xác nhận sản phẩm đáp ứng phạm vi đã chốt |

## 4. Ước lượng và phân công dự kiến

### 4.1. Cách chốt Story Point

- Dùng thang `1, 2, 3, 5, 8` để so sánh công sức, độ phức tạp và mức độ chưa rõ giữa các US.
- Không mặc định 1 điểm bằng một ngày làm việc.
- Người dự kiến thực hiện giải thích cách hiểu; các thành viên cùng đưa điểm và thảo luận khi chênh lệch lớn.
- US chưa rõ cần bổ sung yêu cầu; US quá lớn cần tách trước khi chọn vào sprint.
- Ghi lại ticket được đổi điểm và lý do sau buổi review.
- Điểm hiện có trên Jira là ước lượng ban đầu, cần cả nhóm xác nhận.

### 4.2. Phân công Sprint 0

| Thành viên | Trách nhiệm chính | Ticket | Kết quả cần bàn giao |
| --- | --- | --- | --- |
| Phát Đăng Nguyễn | Điều phối, chốt backlog và review sản phẩm nhóm | [SCRUM-53](https://medhealth-app.atlassian.net/browse/SCRUM-53) | Bản review backlog, quyết định phạm vi, ưu tiên, điểm và phân công |
| Thái Trương | Phân tích yêu cầu và use case | [SCRUM-15](https://medhealth-app.atlassian.net/browse/SCRUM-15) | Tài liệu yêu cầu, ít nhất 6 US có tiêu chí, sơ đồ use case |
| Nguyễn Hữu Huy | Nghiên cứu kiến trúc và thiết kế dữ liệu | [SCRUM-16](https://medhealth-app.atlassian.net/browse/SCRUM-16) | Sơ đồ kiến trúc, ERD, bảng API dự kiến, đề xuất công nghệ |
| Trần Đức Hoàng Hải | Setup repository và môi trường | [SCRUM-17](https://medhealth-app.atlassian.net/browse/SCRUM-17) | README, cấu hình mẫu, project mẫu sau khi chốt stack, bảng kiểm tra 5 máy |
| Diễm Hương Hoàng Thị | Phác giao diện và chuẩn bị kiểm thử | [SCRUM-54](https://medhealth-app.atlassian.net/browse/SCRUM-54) | 5 màn hình phác thảo, luồng điều hướng, ít nhất 15 test case |

Cả 5 thành viên đều phải clone repository về máy mình, làm việc trên nhánh riêng, tạo Pull Request và cập nhật kết quả vào Jira. Người phụ trách chính phối hợp với các thành viên khác; phân công không đồng nghĩa làm việc độc lập hoàn toàn.

### 4.3. Tổng phân bổ dự kiến trên Jira

Theo lần phân công phục vụ bản review này, 44 Story/Task có tổng 199 điểm ước lượng. Các con số gồm cả Task kỹ thuật và công việc tương lai, không phải số điểm US riêng hoặc năng lực của một sprint.

| Thành viên | Số Story/Task dự kiến | Tổng điểm dự kiến |
| --- | ---: | ---: |
| Phát Đăng Nguyễn | 9 | 40 |
| Thái Trương | 9 | 41 |
| Nguyễn Hữu Huy | 8 | 39 |
| Trần Đức Hoàng Hải | 9 | 40 |
| Diễm Hương Hoàng Thị | 9 | 39 |
| **Tổng** | **44** | **199** |

Đây là cách phân bổ ban đầu để mỗi ticket có đầu mối. Nhóm cần điều chỉnh theo sở trường, thời gian và phụ thuộc thực tế; số điểm gần nhau không bảo đảm khối lượng thực tế bằng nhau. Jira là nơi cập nhật phân công sau khi có thay đổi.

## 5. Điều chỉnh Sprint 0 và chuẩn bị Sprint 1

### 5.1. Sprint 0

Sprint 0 chỉ theo dõi 5 đầu việc chuẩn bị ở mục 4.2. Các công việc nghiên cứu có thể làm song song; phần scaffold project của Hải cần dựa trên phương án công nghệ đã được nhóm thống nhất.

Ba ticket phát triển tính năng đã được chuyển từ Sprint 0 sang Sprint 1:

- [SCRUM-1](https://medhealth-app.atlassian.net/browse/SCRUM-1): Đăng ký tài khoản.
- [SCRUM-5](https://medhealth-app.atlassian.net/browse/SCRUM-5): Đăng nhập, đăng xuất và quản lý phiên.
- [SCRUM-18](https://medhealth-app.atlassian.net/browse/SCRUM-18): Phân quyền theo vai trò và chủ sở hữu.

Ngày Sprint 0 đang cấu hình trên Jira là 12/11/2026 đến 26/11/2026. Nhóm trưởng cần đối chiếu tiến độ và deadline học phần trước khi quyết định kết thúc hoặc điều chỉnh lịch; không coi công việc là hoàn thành chỉ vì đến ngày kết thúc sprint.

### 5.2. Sprint 1

Sprint 1 hiện có khoảng 41 điểm ứng viên sau khi bổ sung ba ticket tài khoản/phân quyền. Đây chưa phải cam kết của nhóm.

Trong Sprint Planning, nhóm cần:

1. Xác nhận số ngày và thời gian mỗi người có thể tham gia.
2. Chọn một Sprint Goal khả thi; đề xuất bắt đầu bằng tài khoản và quyền truy cập cơ bản.
3. Chỉ chọn ticket đã rõ yêu cầu và có phụ thuộc sẵn sàng.
4. Cân đối kiểm thử, tích hợp và tài liệu trong cùng sprint.
5. Đưa phần chưa chọn về Product Backlog hoặc sắp xếp lại sprint phù hợp.

## 6. Tiêu chuẩn sẵn sàng và hoàn thành

### Definition of Ready cho US

- [ ] Nêu rõ người dùng, nhu cầu và lợi ích.
- [ ] Có phạm vi và tiêu chí nghiệm thu kiểm tra được.
- [ ] Quy tắc nghiệp vụ quan trọng đã chốt; câu hỏi còn mở được ghi rõ.
- [ ] Có ưu tiên, Story Point và người dự kiến phụ trách.
- [ ] Biết các phụ thuộc và cách kiểm thử.
- [ ] Đủ nhỏ để có thể hoàn thành trong sprint được chọn.

### Definition of Done cho công việc Sprint 0

- [ ] Có sản phẩm đúng yêu cầu của ticket: tài liệu, sơ đồ, cấu hình hoặc project mẫu.
- [ ] File truy cập được qua repository hoặc liên kết trong Jira.
- [ ] Có người kiểm tra và ghi nhận phản hồi.
- [ ] Pull Request đã được review; thay đổi cần dùng chung đã được merge.
- [ ] Hướng dẫn setup được thử trên máy khác nếu ticket liên quan môi trường.
- [ ] Cập nhật Jira bằng kết quả thực tế, không chỉ ghi “đã xong”.

### Definition of Done cho chức năng từ Sprint 1

- [ ] Đạt các tiêu chí nghiệm thu đã thống nhất.
- [ ] Code được review, build được và kiểm thử liên quan đạt.
- [ ] Tích hợp được với các thành phần liên quan trong môi trường demo.
- [ ] Không còn lỗi chặn luồng nghiệp vụ được nghiệm thu.
- [ ] Tài liệu và bằng chứng kiểm thử đã cập nhật.

Test case mới được viết nhưng chưa thực thi phải để `Not run`; không ghi `Pass` khi chưa chạy kiểm thử.

## 7. Cách phối hợp và lưu bằng chứng

| Thành viên | Nhánh đề xuất | Sản phẩm lưu trong repository |
| --- | --- | --- |
| Đăng | `codex/dang-backlog` | `docs/backlog-review.md` |
| Thái | `codex/thai-yeu-cau` | Tài liệu yêu cầu trong `docs/`; sơ đồ trong `docs/diagrams/` |
| Huy | `codex/huy-kien-truc` | `docs/architecture.md`, `docs/api-plan.md`, ERD và sơ đồ kiến trúc |
| Hải | `codex/hai-setup` | `README.md`, `.gitignore`, cấu hình mẫu và cấu trúc project |
| Hương | `codex/huong-wireframe-test` | `docs/wireframes/`, `docs/test-cases.xlsx` |

Mỗi Pull Request cần ghi mã Jira, nội dung thay đổi và cách kiểm tra. Nhóm trưởng review hoặc phân công một người khác review trước khi merge vào `main`.

Không commit mật khẩu, token, file `.env` thật hoặc dữ liệu sức khỏe cá nhân. File cấu hình mẫu chỉ chứa giá trị minh họa.

Mẫu cập nhật ticket:

```text
Đã làm:
- ...

Sản phẩm / Pull Request:
- ...

Kết quả kiểm tra:
- ...

Vướng mắc / cần hỗ trợ:
- ...

Nhờ review:
- ...
```

## 8. Nội dung buổi review cần ghi nhận

| Nội dung | Quyết định / kết quả | Người xác nhận |
| --- | --- | --- |
| Thời gian họp và người tham dự | Chưa ghi nhận | Chờ cập nhật |
| Phạm vi MVP | Chờ nhóm thống nhất | Cả nhóm |
| Mức độ triển khai Web/Mobile/Desktop | Chờ nhóm thống nhất | Cả nhóm |
| Công nghệ và phương án kế thừa | Chờ đề xuất của Huy, trao đổi với Hải | Cả nhóm |
| Thứ tự ưu tiên các US | Chờ review bảng ưu tiên | Cả nhóm |
| Điểm các US | Chờ nhóm ước lượng lại | Cả nhóm |
| Điều chỉnh người phụ trách | Chờ xác nhận phân công dự kiến | Từng thành viên |
| Mục tiêu và phạm vi Sprint 1 | Chưa cam kết | Cả nhóm |
| Deadline học phần và năng lực tham gia | Chưa xác nhận | Nhóm trưởng và các thành viên |

### Nhật ký thay đổi điểm, ưu tiên và phân công

| Ticket | Thay đổi | Lý do | Người xác nhận | Ngày |
| --- | --- | --- | --- | --- |
| Chờ cập nhật sau review | | | | |

## 9. Checklist trước khi báo cáo giảng viên

- [ ] Các US trong phạm vi đã có mô tả, tiêu chí, ưu tiên, điểm và người phụ trách dự kiến.
- [ ] Có ghi nhận cả nhóm đã thảo luận và các quyết định thực tế.
- [ ] Sprint 0 chỉ chứa khởi tạo, setup, nghiên cứu và chuẩn bị.
- [ ] Có tài liệu yêu cầu, use case, kiến trúc và ERD sơ bộ.
- [ ] Có repository chung và các thành viên có quyền truy cập phù hợp.
- [ ] Cả 5 thành viên đã clone về máy mình.
- [ ] Sau khi có project mẫu, cả 5 máy đã thử theo README và ghi kết quả.
- [ ] Có link Pull Request, tài liệu hoặc ảnh minh chứng trong từng ticket.
- [ ] Đã chọn lại phạm vi Sprint 1 theo năng lực thực tế.
- [ ] Chưa hoàn thành mục nào thì ghi rõ tình trạng, người xử lý và bước tiếp theo.
