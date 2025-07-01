# 📄 BÁO CÁO KIỂM THỬ HIỆU SUẤT JMETER
## Tên Dự Án: Load Testing API – ReqRes
## Ngày Kiểm Thử: 01/07/2025
## Người Kiểm Thử: Nguyễn Khắc Quang

## 1. 🎯 Mục Tiêu Kiểm Thử
- Sử dụng JMeter để kiểm thử hiệu suất các API RESTful tại trang https://reqres.in, bao gồm các API như GET, POST, DELETE.
## 2. 🧪 Môi Trường Kiểm Thử
- Hệ điều hành: Windows 10 64bit
- Công cụ: Apache JMeter 5.6
- Java: OpenJDK 17
- Internet: Ổn định
## 3. 🧰 Phương Pháp Kiểm Thử
- Tự động hóa kiểm thử bằng JMeter
- Kịch bản được thiết lập để gửi nhiều HTTP Request đến API /api/users
## 4. 📊 Kịch Bản Kiểm Thử
### Kịch Bản Lần 1
- Tên: Kiểm thử API GET danh sách người dùng
- Mục Đích: Kiểm tra khả năng phản hồi của API với lượng nhỏ người dùng
- HTTP Request: https://reqres.in/api/users?page=2
- Phương thức: GET
- Thread (user): 5
- Ramp-up (giây): 2
- Loop-count: 2
- Kết quả mong đợi: Gửi yêu cầu và nhận được phản hồi HTTP 200
- Kết quả thực tế: Thành công, mã trạng thái 200
- Thời gian phản hồi trung bình: 300 ms
- Tỷ lệ thành công: 100%
- Trạng thái: ✅ Thành công
![image](https://github.com/user-attachments/assets/0fd28ca6-bf80-4a20-8dde-d2fcd79f4ff2)

### Kịch Bản Lần 2
- Tên: Kiểm thử API POST tạo người dùng
- Mục Đích: Xác định khả năng xử lý POST request với tải cao hơn
- HTTP Request: https://reqres.in/api/users
- Phương thức: POST

- Payload:
```
{
  "name": "Quang",
  "job": "tester"
}

```
- Thread (user): 20
- Ramp-up (giây): 4
- Loop-count: 5
- Kết quả mong đợi: Nhận mã phản hồi 201 và body trả về đúng định dạng
- Kết quả thực tế: Thành công, mã trạng thái 201
- Thời gian phản hồi trung bình: 800 ms
- Tỷ lệ thành công: 100%
- Trạng thái: ✅ Thành công
### Kịch Bản Lần 3
- Tên: Kiểm thử API DELETE người dùng
- HTTP Request: https://reqres.in/api/users/2
- Phương thức: DELETE
- Thread (user): 10
- Ramp-up (giây): 3
- Loop-count: 3
- Kết quả mong đợi: Nhận mã trạng thái 204
- Kết quả thực tế: Thành công
- Thời gian phản hồi trung bình: 200 ms
- Tỷ lệ thành công: 100%
- Trạng thái: ✅ Thành công
![image](https://github.com/user-attachments/assets/d912554e-c573-471f-ab25-8cd001c251ad)

## 5. ✅ Tổng Kết
- Hệ thống API hoạt động ổn định và phản hồi tốt trong các kịch bản kiểm thử hiệu suất cơ bản đến trung bình. Tất cả yêu cầu được xử lý với tỷ lệ thành công 100%, và thời gian phản hồi dưới 1 giây, kể cả với tải cao.



