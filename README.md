# Cuoc-thi-WRO-B6-2026
Chương trình điều khiển robot tự hành sử dụng **Matrix Mini R4**, bộ công cụ **MATRIX WRO Future Innovators Set V2**. Robot thực hiện nhiệm vụ di chuyển theo luật thi đấu bằng cảm biến khoảng cách, cảm biến màu và camera AI.

## Hướng dẫn tải arduino và open mv
- Đầu tiên cần truy cập vào link
- https://www.matrixrobotics.com/adv-program-resources để tải
- Hướng dẫn tải [https://username.github.io/repository](https://www.matrixrobotics.com/file-share/aa511d46-f96a-416a-ae97-c4abf8c9614a) tìm mục MATRIX_R4_Guidebook_EN_V3.0.pdf sau khi vào thì tìm 2.11.2.Arduino Programming & Library Overview ở trang 45
- sau đó tải open Mv, Hướng dẫn tải https://wro-learn.org/en_us/wiki/m-vision-camera
- để có thể sử dụng camera bạn cần tải file code https://github.com/minhkt1/Cu-c-thi-wro-B6-2026/blob/main/MiniR4SmartCamReader.h
- sau đấy mở thư mục lên vào phần document => arduino => libraries => Matrix Mini R4 => src => moudle , dán file vào

## Hướng dẫn lắp robot
- Sử dụng bộ dụng cụ **MATRIX WRO Future Innovators Set V2**
- Hướng dẫn lắp
## Hệ thống cảm biến
- 2 laser sensor V2
- color senser V3
- M-vision camera
- Động cơ DC
- Servo
## 🚗 Chức năng chính

| Hàm | Chức năng |
|------|-----------|
| `ChieuBenTrai()` | chạy vòng mở theo hướng bên trái
| `ChieuBenPhai()` | Chạy vòng mở theo hướng bên phải |
| `DoTuongPhai_TocDo_n_Khoangcach_mm_n_kp_n_kd_n(float tocdo, float mm, float kp, float kd)` | Di chuyển bám tường bên phải |
| `DoTuongTrai_TocDo_n_Khoangcach_mm_n_kp_n_kd_n(float tocdo, float mm, float kp, float kd)` | Di chuyểnn bám tường bên trái |
| `DoDuong_Trai_Cm_n_TocDo_n_KhoangCach_Mm_n_kp_n_kd_n(float cm, float tocdo, float mm, float kp, float kd)` | Di chuyển bám tường bên trái theo cm |
| `DoDuongPhai_Cm_n_TocDo_n_KC_MM_n_kp_n_kd_n(float cm, float tocdo, float mm, float kp, float kd)` | Di chuyển bám tường bên phải theo cm |
| `camera()` | Xử lý dữ liệu camera |
| `TranhKhoi_Do()` | Né khối màu đỏ |
| `TranhKhoi_Xanh()` | Né khối màu xanh |

## Hướng dẫn cài code và chạy
- code arduino https://github.com/minhkt1/Cu-c-thi-wro-B6-2026/blob/main/doduongv2_ban_arduino.ino
- Trước khi chạy cần để robot song song với thành tường, trong vực quy định đối với vòng thử thách mở và trong khu vực đỗ xe đối vòng thử thách chướng ngại vật
## Hướng dẫn xử lý lỗi
- Robot khi bám tường bị lắc, không ổn định ==> cần điều chỉnh chỉ số kp, kd
- Robot không đọc được vạch màu, cần giảm tốc độ để kiểm tra color sensor V3 có hoạt động không. Nếu không thì cần điều chỉnh lại chỉ số RBG hoặc kiểm tra cảm biến có hoạt động hay không
- Trong trường hợp robot không đọc được khối. Cần kiểm tra robot có nhìn thấy khối không, thì cần điều chỉnh sao cho robot nhìn được khối. Nếu nhìn được nhưng robot không nhận thì cần cheking lại camera sao cho nhìn được
- Robot đang đi mà dừng không đi nữa hoặc phải đẩy mới đi được, cần kiểm tra lại cổng cắm pin, phần trăm pin





