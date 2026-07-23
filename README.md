# Cuoc-thi-WRO-B6-2026
Chương trình điều khiển robot tự hành sử dụng **Matrix Mini R4**, bộ công cụ **MATRIX WRO Future Innovators Set V2**. Robot thực hiện nhiệm vụ di chuyển theo luật thi đấu bằng cảm biến khoảng cách, cảm biến màu và camera AI.

# Cài đặt môi trường phát triển

Để lập trình và vận hành robot, cần cài đặt các phần mềm và thư viện theo các bước sau.

## 1. Cài đặt Arduino IDE

Truy cập trang tài nguyên của MATRIX Robotics:

> https://www.matrixrobotics.com/adv-program-resources

Tải và cài đặt **Arduino IDE** theo hướng dẫn.

Để biết chi tiết cách cài đặt và sử dụng thư viện MATRIX Mini R4, tham khảo tài liệu:

> https://username.github.io/repository

Mở tài liệu **MATRIX_R4_Guidebook_EN_V3.0.pdf**, sau đó đến **Mục 2.11.2 – Arduino Programming & Library Overview (Trang 45)** và thực hiện theo hướng dẫn.

---

## 2. Cài đặt OpenMV IDE

Sau khi cài đặt Arduino IDE, tiếp tục cài đặt **OpenMV IDE** để lập trình cho camera OpenMV.

Hướng dẫn cài đặt:

> https://wro-learn.org/en_us/wiki/m-vision-camera

---

## 3. Cài đặt thư viện giao tiếp với camera

Để MATRIX Mini R4 có thể giao tiếp với camera OpenMV, tải tệp sau:

> https://github.com/minhkt1/Cu-c-thi-wro-B6-2026/blob/main/MiniR4SmartCamReader.h

Sau khi tải về, sao chép tệp **MiniR4SmartCamReader.h** vào thư mục:

```text
Documents/
└── Arduino/
    └── libraries/
        └── Matrix Mini R4/
            └── src/
                └── module/
```

Nếu hệ thống hiển thị thông báo ghi đè tệp, chọn **Replace** để thay thế tệp hiện có.

---

## Hoàn tất

Sau khi hoàn thành các bước trên, môi trường phát triển đã được thiết lập đầy đủ và sẵn sàng để:

- Biên dịch chương trình trên Arduino IDE.
- Nạp chương trình cho MATRIX Mini R4.
- Lập trình và sử dụng camera OpenMV.

## Hướng dẫn lắp robot
- Sử dụng bộ dụng cụ **MATRIX WRO Future Innovators Set V2**
- Hướng dẫn lắp
## Hệ thống cảm biến
- Hai laser sensor V2
- Color senser V3
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
- Code arduino IDE https://github.com/minhkt1/Cu-c-thi-wro-B6-2026/blob/main/doduongv2_ban_arduino.ino
- Trước khi chạy cần để robot song song với thành tường, trong vực quy định đối với vòng thử thách mở và trong khu vực đỗ xe đối vòng thử thách chướng ngại vật
## Hướng dẫn xử lý lỗi
- Robot khi bám tường bị lắc, không ổn định ==> cần điều chỉnh chỉ số kp, kd
- Robot không đọc được vạch màu, cần giảm tốc độ để kiểm tra color sensor V3 có hoạt động không. Nếu không thì cần điều chỉnh lại chỉ số RBG hoặc kiểm tra cảm biến có hoạt động hay không
- Trong trường hợp robot không đọc được khối. Cần kiểm tra robot có nhìn thấy khối không, thì cần điều chỉnh sao cho robot nhìn được khối. Nếu nhìn được nhưng robot không nhận thì cần cheking lại camera sao cho nhìn được
- Robot đang đi mà dừng không đi nữa hoặc phải đẩy mới đi được, cần kiểm tra lại cổng cắm pin, phần trăm pin





