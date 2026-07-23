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
- Thay vì sử dụng mẫu Open MV trong Link thì truy cập: https://github.com/SuGiugi/CCVA-HSRL-B6-03/tree/main/OpenMV và cài đặt giống hướng dẫn 

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
                    └── sensor/
                    
```

Nếu hệ thống hiển thị thông báo ghi đè tệp, chọn **Replace** để thay thế tệp hiện có.

---

## Hoàn tất

Sau khi hoàn thành các bước trên, môi trường phát triển đã được thiết lập đầy đủ và sẵn sàng để:

- Biên dịch chương trình trên Arduino IDE.
- Nạp chương trình cho MATRIX Mini R4.
- Lập trình và sử dụng camera OpenMV.

## Bộ dụng cụ và hướng dẫn lắp ráp

Robot được phát triển trên nền tảng **MATRIX WRO Future Innovators Set V2**, cung cấp đầy đủ các chi tiết cơ khí, bộ điều khiển và phụ kiện cần thiết để xây dựng một robot phục vụ cho các cuộc thi WRO. Việc sử dụng bộ dụng cụ này giúp đảm bảo tính tương thích giữa các linh kiện, đồng thời thuận tiện cho quá trình lắp ráp, bảo trì và nâng cấp trong quá trình phát triển dự án.

Toàn bộ robot được lắp ráp dựa trên hướng dẫn chính thức của MATRIX Robotics. Người dùng nên thực hiện theo đúng trình tự các bước trong tài liệu để đảm bảo kết cấu cơ khí chính xác và các bộ phận được lắp đặt đúng vị trí. Sau khi hoàn thành việc lắp ráp, cần kiểm tra lại độ chắc chắn của các mối ghép, khả năng chuyển động của các cơ cấu và vị trí lắp đặt của các thiết bị trước khi tiến hành cài đặt phần mềm và nạp chương trình cho robot.

Hướng dẫn lắp ráp chi tiết được cung cấp tại liên kết dưới đây:https://github.com/SuGiugi/CCVA-HSRL-B6-03/blob/main/Instruction/CCVA-HSRL-B6-03.pdf

## Hệ thống cảm biến
- Hai laser sensor V2
- Color senser V3
- M-vision camera
- Động cơ DC
- Servo
## 🚗 Chức năng chính

## Các hàm chính

Bảng dưới đây mô tả các hàm chính được sử dụng trong chương trình điều khiển robot.

| Hàm | Chức năng |
|------|-----------|
| `ChieuBenTrai()` | Robot thực hiện vòng mở theo hướng bên trái. |
| `ChieuBenPhai()` | Robot thực hiện vòng mở theo hướng bên phải. |
| `DoTuongPhai_TocDo_n_Khoangcach_mm_n_kp_n_kd_n(float tocdo, float mm, float kp, float kd)` | Robot di chuyển bám tường bên phải với tốc độ, khoảng cách mục tiêu và các hệ số điều khiển PID được chỉ định. |
| `DoTuongTrai_TocDo_n_Khoangcach_mm_n_kp_n_kd_n(float tocdo, float mm, float kp, float kd)` | Robot di chuyển bám tường bên trái với tốc độ, khoảng cách mục tiêu và các hệ số điều khiển PID được chỉ định. |
| `DoDuong_Trai_Cm_n_TocDo_n_KhoangCach_Mm_n_kp_n_kd_n(float cm, float tocdo, float mm, float kp, float kd)` | Robot di chuyển một quãng đường xác định (cm) đồng thời bám tường bên trái bằng điều khiển PID. |
| `DoDuongPhai_Cm_n_TocDo_n_KC_MM_n_kp_n_kd_n(float cm, float tocdo, float mm, float kp, float kd)` | Robot di chuyển một quãng đường xác định (cm) đồng thời bám tường bên phải bằng điều khiển PID. |
| `camera()` | Nhận và xử lý dữ liệu từ camera để phục vụ việc nhận diện đối tượng và hỗ trợ điều khiển robot. |
| `TranhKhoi_Do()` | Thực hiện thuật toán tránh khối màu đỏ. |
| `TranhKhoi_Xanh()` | Thực hiện thuật toán tránh khối màu xanh. |
## Chạy chương trình

Mã nguồn chương trình Arduino được cung cấp tại:

- **Arduino IDE:** https://github.com/minhkt1/Cu-c-thi-wro-B6-2026/blob/main/doduongv2_ban_arduino.ino

### Chuẩn bị trước khi chạy

Trước khi nạp và thực thi chương trình, cần đặt robot đúng vị trí xuất phát để đảm bảo thuật toán hoạt động chính xác.

- **Vòng Thử thách Mở (Open Challenge):** Đặt robot trong khu vực xuất phát theo quy định của sân thi và căn chỉnh sao cho robot **song song với thành tường**.

- **Vòng Thử thách Chướng ngại vật (Obstacle Challenge):** Đặt robot **trong khu vực đỗ xe** theo quy định của sân thi và căn chỉnh để robot **song song với thành tường** trước khi bắt đầu chạy.

> **Lưu ý:** Việc căn chỉnh robot song song với thành tường trước khi xuất phát giúp các thuật toán bám tường và định hướng ban đầu hoạt động ổn định, từ đó giảm sai số trong quá trình di chuyển.
## Hướng dẫn xử lý lỗi
- Robot khi bám tường bị lắc, không ổn định ==> cần điều chỉnh chỉ số kp, kd
- Robot không đọc được vạch màu, cần giảm tốc độ để kiểm tra color sensor V3 có hoạt động không. Nếu không thì cần điều chỉnh lại chỉ số RBG hoặc kiểm tra cảm biến có hoạt động hay không
- Trong trường hợp robot không đọc được khối. Cần kiểm tra robot có nhìn thấy khối không, thì cần điều chỉnh sao cho robot nhìn được khối. Nếu nhìn được nhưng robot không nhận thì cần cheking lại camera sao cho nhìn được
- Robot đang đi mà dừng không đi nữa hoặc phải đẩy mới đi được, cần kiểm tra lại cổng cắm pin, phần trăm pin





## Cấu trúc thư mục

Repository được tổ chức theo các thư mục chức năng nhằm thuận tiện cho việc cài đặt, phát triển và tham khảo tài liệu của dự án.

```text
CCVA-HSRL-B6-03
│
├── Adurino libaries/      # Thư viện sử dụng cho Arduino IDE
├── CCVA-HSRL-B6-03/       # Mã nguồn chương trình điều khiển robot
├── Instruction/           # Hướng dẫn cài đặt và sử dụng
├── OpenMV/                # Chương trình xử lý ảnh cho OpenMV
├── Pictures/              # Hình ảnh robot và các thành phần
├── Videos/                # Video minh họa quá trình hoạt động
└── README.md              # Tài liệu giới thiệu dự án
```

### Mô tả các thư mục

#### `Adurino libaries/`

Chứa các thư viện cần thiết để biên dịch và chạy chương trình trên **Arduino IDE**. Người dùng nên cài đặt các thư viện này trước khi nạp chương trình cho robot.

#### `CCVA-HSRL-B6-03/`

Chứa mã nguồn chính của robot, bao gồm các thuật toán điều khiển, xử lý cảm biến và các hàm phục vụ quá trình thi đấu.

#### `Instruction/`

Chứa các tài liệu hướng dẫn cài đặt môi trường phát triển, lắp ráp robot và các hướng dẫn cần thiết để sử dụng dự án.

#### `OpenMV/`

Chứa chương trình chạy trên camera **OpenMV**, phục vụ việc xử lý ảnh và nhận diện đối tượng trong quá trình robot hoạt động.

#### `Pictures/`

Lưu trữ hình ảnh của robot, các bộ phận, mô hình lắp ráp và hình ảnh minh họa phục vụ tài liệu dự án.

#### `Videos/`

Chứa các video trình diễn robot, quá trình thử nghiệm và hoạt động của hệ thống.
