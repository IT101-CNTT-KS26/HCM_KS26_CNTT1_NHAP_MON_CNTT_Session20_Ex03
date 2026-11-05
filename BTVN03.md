# BTVN 03 (SESSION 20)
## ***Báo cáo phân tích (IPO)***

### **1.** Input (Mã dự phòng), Process (Xác thực/Hủy mã cũ/Cấp mã mới), Output (Hệ thống an toàn).
- **Input (Mã dự phòng):** Tên đăng nhập/Mật khẩu AWS và 01 mã Backup Code lưu trữ ngoại tuyến.

- **Process (Xác thực/Hủy mã cũ/Cấp mã mới):** 

   **->Đăng nhập khẩn cấp:** Dùng Username/Password và nhập 1 mã Backup Code để vượt qua bước xác thực 2FA vào AWS Console.

   **->Thu hồi MFA cũ:** Vào IAM Console $\rightarrow$ Security Credentials, bấm hủy kích hoạt (Deactivate) thiết bị MFA trên điện thoại đã mất để chặn truy cập từ thiết bị này.

   **->Cấu hình MFA mới** Đăng ký lại 2FA trên thiết bị mới (điện thoại dự phòng hoặc YubiKey) bằng mã QR Code mới.

   **->Cấp mã mới:** Thu hồi bộ mã dự phòng cũ, tạo bộ Backup Codes mới và lưu trữ an toàn.

- **Output (Đầu ra):** Khôi phục quyền truy cập AWS cho Lead Developer, vô hiệu hóa triệt để thiết bị bị mất; hệ thống AWS an toàn với lớp xác thực 2FA hoàn toàn mới.
### **2.** Giải thích tại sao không được lưu Backup Codes dưới dạng ảnh trong thư viện điện thoại.

- Vì Lỡ làm rớt mất điện thoại thì người nhặt được rồi mở khóa màn hình thì sẽ đọc được ngay bộ ảnh chứa Backup Code mà không phải gặp thêm lớp bảo vệ nào.
- Và nếu lưu ở dạng hình ảnh ở trong thư viện ảnh của trong điện thoại thì khi chúng ta lỡ đăng nhập vào nhầm đường link giả mạo có mã độc thì sẽ bị quét dễ dàng xem được hình ảnh chứa Backup Code mà không có thêm lớp bảo vệ nào hết cả. Biến lớp xác thực 2FA trở nên vô hiệu khi thiết bị hoặc tài khoản bị xâm nhập. 