# Test case ban đầu MedHealth

Phụ trách: Diễm Hương Hoàng Thị. Ticket: [SCRUM-54](https://medhealth-app.atlassian.net/browse/SCRUM-54). Bản đề xuất 25/11/2026.

Có 24 ca, hiện tất cả **Not run**. Kết quả thực tế, người chạy và bằng chứng để trống đến khi thực thi. Ca phụ thuộc chính sách chưa chốt chỉ chạy sau khi nhóm ghi rõ điều kiện. Dữ liệu trong ca là dữ liệu giả lập.

[Bảng Excel](test-cases.xlsx) dùng để thực thi; bản Markdown là bản thiết kế ban đầu, không tự đồng bộ kết quả. Các ID US chính thức và tiêu chí xem trong Jira và [requirements](requirements.md).

## TC-01. Đăng ký hợp lệ

- Jira: SCRUM-1.
- Điều kiện: Email demo chưa tồn tại.
- Bước thực hiện: Mở Đăng ký; nhập đủ trường; gửi một lần.
- Dữ liệu: demo.patient@example.test; mật khẩu theo chính sách sẽ chốt.
- Mong đợi: Tạo đúng một tài khoản bệnh nhân; hướng dẫn đăng nhập.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-02. Thiếu email

- Jira: SCRUM-1.
- Điều kiện: Đang mở Đăng ký.
- Bước thực hiện: Để email trống; điền các trường khác; gửi.
- Dữ liệu: email trống.
- Mong đợi: Báo lỗi tại email; không tạo tài khoản.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-03. Email sai định dạng

- Jira: SCRUM-1.
- Điều kiện: Đang mở Đăng ký.
- Bước thực hiện: Nhập email không hợp lệ; gửi.
- Dữ liệu: email=abc.
- Mong đợi: Báo sai định dạng; không tạo tài khoản.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-04. Email đã tồn tại

- Jira: SCRUM-1.
- Điều kiện: Đã seed tài khoản demo.
- Bước thực hiện: Đăng ký lại cùng email demo.
- Dữ liệu: demo.patient@example.test.
- Mong đợi: Không tạo tài khoản/hồ sơ dư; báo email trùng theo chính sách.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-05. Mật khẩu xác nhận khác

- Jira: SCRUM-1.
- Điều kiện: Đang mở Đăng ký.
- Bước thực hiện: Nhập hai mật khẩu khác nhau; gửi.
- Dữ liệu: Hai giá trị khác nhau.
- Mong đợi: Báo không khớp; không gửi hoặc không chấp nhận request sai.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-06. Đăng nhập đúng

- Jira: SCRUM-5.
- Điều kiện: Tài khoản demo hoạt động.
- Bước thực hiện: Nhập thông tin đúng; đăng nhập.
- Dữ liệu: Tài khoản demo đã seed.
- Mong đợi: Tạo phiên; mở trang phù hợp vai trò.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-07. Sai mật khẩu

- Jira: SCRUM-5.
- Điều kiện: Tài khoản demo hoạt động.
- Bước thực hiện: Nhập email đúng, mật khẩu sai; gửi.
- Dữ liệu: Mật khẩu sai.
- Mong đợi: Lỗi chung; không tạo phiên, không tiết lộ thông tin tài khoản.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-08. Đăng xuất vô hiệu phiên

- Jira: SCRUM-5.
- Điều kiện: Đã đăng nhập.
- Bước thực hiện: Đăng xuất; thử mở tài nguyên riêng bằng phiên cũ.
- Dữ liệu: Phiên trước đăng xuất.
- Mong đợi: Không tiếp tục truy cập tài nguyên bảo vệ.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-09. Tìm tên và chuyên khoa

- Jira: SCRUM-6.
- Điều kiện: Danh mục có bác sĩ demo.
- Bước thực hiện: Nhập tên; chọn chuyên khoa; xem kết quả.
- Dữ liệu: DEMO A; chuyên khoa demo.
- Mong đợi: Chỉ trả kết quả khớp các điều kiện.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-10. Không có kết quả

- Jira: SCRUM-6.
- Điều kiện: Danh mục có dữ liệu.
- Bước thực hiện: Tìm chuỗi không tồn tại.
- Dữ liệu: zz-demo-no-match.
- Mong đợi: Hiện trạng thái rỗng và cách bỏ lọc.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-11. Lỗi tải danh sách

- Jira: SCRUM-6.
- Điều kiện: Có cách mô phỏng lỗi mạng trong môi trường thử.
- Bước thực hiện: Ngắt kết nối; tải danh sách; khôi phục và thử lại.
- Dữ liệu: Lỗi mạng giả lập.
- Mong đợi: Thông báo lỗi; không treo tải; thử lại khôi phục danh sách.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-12. Mở đúng hồ sơ

- Jira: SCRUM-7.
- Điều kiện: Có hai bác sĩ demo.
- Bước thực hiện: Mở kết quả bác sĩ DEMO A.
- Dữ liệu: ID bác sĩ DEMO A.
- Mong đợi: Hiển thị đúng tên, chuyên khoa và cơ sở công khai.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-13. Khung đầy hoặc quá khứ

- Jira: SCRUM-21.
- Điều kiện: Seed khung đầy, còn chỗ và quá khứ.
- Bước thực hiện: Mở ngày; thử chọn khung không hợp lệ.
- Dữ liệu: Các khung demo.
- Mong đợi: Khung đầy/quá khứ không được chọn; khung hợp lệ chọn được.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-14. Đặt lịch thành công

- Jira: SCRUM-23.
- Điều kiện: Bệnh nhân đã đăng nhập; khung còn chỗ.
- Bước thực hiện: Chọn khung; nhập lý do; xác nhận.
- Dữ liệu: ID khung demo còn chỗ.
- Mong đợi: Tạo mã lịch; gắn đúng bệnh nhân; số chỗ còn giảm đúng.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-15. Hai người đặt chỗ cuối

- Jira: SCRUM-23.
- Điều kiện: Khung capacity=1; hai bệnh nhân demo.
- Bước thực hiện: Gửi hai request đồng thời tới cùng khung.
- Dữ liệu: Hai tài khoản, hai idempotency key khác nhau.
- Mong đợi: Chỉ một yêu cầu chiếm chỗ; yêu cầu còn lại báo hết chỗ.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-16. Retry cùng yêu cầu

- Jira: SCRUM-23.
- Điều kiện: Có idempotency key cho một request hợp lệ.
- Bước thực hiện: Gửi lại cùng key và payload bằng cùng tài khoản.
- Dữ liệu: demo-request-001.
- Mong đợi: Trả lại cùng kết quả; DB chỉ có một lịch.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-17. Xem lịch của mình

- Jira: SCRUM-24.
- Điều kiện: Hai bệnh nhân có lịch khác nhau.
- Bước thực hiện: Đăng nhập A; mở danh sách và chi tiết.
- Dữ liệu: Tài khoản A/B giả lập.
- Mong đợi: Chỉ hiển thị lịch của A.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-18. Chặn đổi ID lịch người khác

- Jira: SCRUM-18, SCRUM-24.
- Điều kiện: A và B có lịch; đăng nhập A.
- Bước thực hiện: Gọi chi tiết/sửa lịch B bằng ID B.
- Dữ liệu: ID lịch B.
- Mong đợi: 403 hoặc 404 theo chính sách chốt; không trả dữ liệu lịch B.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-19. Đổi sang khung hết chỗ

- Jira: SCRUM-25.
- Điều kiện: Lịch gốc còn hiệu lực; khung mới đầy; trong hạn đổi được chốt.
- Bước thực hiện: Đổi sang khung đầy; tải lại lịch gốc.
- Dữ liệu: ID lịch gốc và khung mới.
- Mong đợi: Đổi thất bại; lịch gốc và sức chứa không sai lệch.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-20. Hủy lịch hợp lệ

- Jira: SCRUM-25.
- Điều kiện: Lịch thuộc bệnh nhân; còn điều kiện hủy được chốt.
- Bước thực hiện: Mở lịch; hủy và xác nhận; gửi lại thao tác.
- Dữ liệu: Lịch demo hợp lệ.
- Mong đợi: Cancelled; trả đúng một chỗ; thao tác lặp không trả chỗ lần hai.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-21. Không check-in lịch hủy

- Jira: SCRUM-26.
- Điều kiện: Lịch đã Cancelled; nhân viên tiếp nhận đăng nhập.
- Bước thực hiện: Thử check-in qua UI và API.
- Dữ liệu: ID lịch đã hủy.
- Mong đợi: Server từ chối chuyển trạng thái; lịch vẫn Cancelled.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-22. Ẩn bệnh án nháp

- Jira: SCRUM-30, SCRUM-31.
- Điều kiện: Bác sĩ đã lưu nháp; bệnh nhân đăng nhập.
- Bước thực hiện: Bệnh nhân mở lịch sử/chi tiết bệnh án nháp.
- Dữ liệu: Lượt khám demo chưa published_at.
- Mong đợi: Không lộ bản nháp; chỉ bản đã công bố được xem.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-23. Worker chạy lại không nhắc trùng

- Jira: SCRUM-36.
- Điều kiện: Có nhắc đến hạn và fake clock; quy tắc retry đã chốt.
- Bước thực hiện: Chạy worker; chạy lại cùng việc.
- Dữ liệu: Một dedup_key.
- Mong đợi: Chỉ một sự kiện/kênh theo thiết kế; có log trạng thái.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## TC-24. Khóa tài khoản thu hồi phiên

- Jira: SCRUM-38.
- Điều kiện: Tài khoản demo có phiên; quản trị đăng nhập.
- Bước thực hiện: Khóa tài khoản; dùng phiên cũ gọi API.
- Dữ liệu: User demo bị khóa.
- Mong đợi: Không đăng nhập hoặc tiếp tục dùng phiên cũ.
- Kết quả thực tế: chưa ghi nhận.
- Trạng thái: **Not run**.

## Cách ghi kết quả

Sau khi chạy, điền kết quả thực tế, người chạy, môi trường/phiên bản và link bằng chứng ở cột cuối. Dùng Pass khi đạt tất cả mong đợi, Fail khi có sai lệch, Blocked khi chưa thể chạy do phụ thuộc hoặc cấu hình, Not run khi chưa chạy. Nếu phát hiện lỗi, tạo ticket lỗi phù hợp và gắn mã tại cột bằng chứng. Khi đổi thiết kế ca kiểm thử, cập nhật cả Excel và Markdown.
