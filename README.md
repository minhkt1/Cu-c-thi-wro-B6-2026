# Cuoc-thi-WRO-B6-2026
Chương trình điều khiển robot tự hành sử dụng **Matrix Mini R4**, bộ công cụ **MATRIX WRO Future Innovators Set V2**. Robot thực hiện nhiệm vụ di chuyển theo luật thi đấu bằng cảm biến khoảng cách, cảm biến màu và camera AI.

## Hướng dẫn tải arduino
- Đầu tiên cần truy cập vào link
- https://www.matrixrobotics.com/adv-program-resources để tải
- Hướng dẫn tải [https://username.github.io/repository](https://www.matrixrobotics.com/file-share/aa511d46-f96a-416a-ae97-c4abf8c9614a) tìm mục MATRIX_R4_Guidebook_EN_V3.0.pdf sau khi vào thì tìm 2.11.2.Arduino Programming & Library Overview
- sau đó tải open Mv, Hướng dẫn tải https://wro-learn.org/en_us/wiki/m-vision-camera
- để có thể sử dụng camera bạn cần tải file 





- 📏 Bám tường trái/phải bằng cảm biến Laser
- 🎯 Điều khiển lái bằng thuật toán PD
- 🎨 Nhận diện màu để xác định điểm chuyển hướng
- 👁️ Hỗ trợ camera AI
- 🟥🟦 Né vật cản theo màu
- 🔄 Di chuyển theo hai chiều (Left / Right)

---

## 🛠️ Phần cứng sử dụng

- Matrix Mini R4
- Servo lái
- Động cơ DC
- 2 × Matrix Laser V2 Distance Sensor
- Matrix Color Sensor V3
- Matrix AI Vision Camera

---

## 📁 Cấu trúc dự án

```
.
├── doduongv2_ban_arduino.ino   # Source code chính
└── README.md
```

---

## 📚 Thư viện

Chương trình sử dụng thư viện chính:

```cpp
#include "MatrixMiniR4.h"
```

Có thể tải bộ thư viện và tài nguyên lập trình tại:

https://www.matrixrobotics.com/adv-program-resources

---

## ⚙️ Thuật toán

Robot sử dụng điều khiển **PD (Proportional - Derivative)** để giữ khoảng cách với tường.

```
Correction = KP × Error + KD × (Error - LastError)
```

Trong đó:

- **KP = 0.5**
- **KD = 0.5**

Sai số được tính từ khoảng cách thực tế của cảm biến Laser.

---

## 🚗 Chức năng chính

| Hàm | Chức năng |
|------|-----------|
| `ChieuBenTrai()` | Chạy theo hướng trái |
| `ChieuBenPhai()` | Chạy theo hướng phải |
| `DoTuongTrai()` | Bám tường trái |
| `BamTuongPhai()` | Bám tường phải |
| `DoDuong_Trai()` | Di chuyển theo quãng đường bên trái |
| `DoDuongPhai()` | Di chuyển theo quãng đường bên phải |
| `camera()` | Xử lý dữ liệu camera |
| `TranhKhoi_Do()` | Né khối màu đỏ |
| `TranhKhoi_Xanh()` | Né khối màu xanh |

---

## 🚀 Cài đặt

1. Tải và cài đặt thư viện Matrix Robotics.
2. Mở file `doduongv2_ban_arduino.ino` bằng Arduino IDE.
3. Chọn đúng Board và cổng COM.
4. Upload chương trình vào Matrix Mini R4.

---

## 📖 Tài liệu

Matrix Robotics Advanced Programming Resources:

https://www.matrixrobotics.com/adv-program-resources

---

## 📷 Hệ thống cảm biến

- Laser trái
- Laser phải
- Cảm biến màu
- Camera AI
- Encoder động cơ
- Servo lái

---

## 📌 Ghi chú

- Chương trình được viết cho nền tảng **Matrix Mini R4**.
- Cần cài đúng phiên bản thư viện trước khi biên dịch.
- Có thể cần hiệu chỉnh các thông số **KP**, **KD** và khoảng cách cảm biến để phù hợp với từng robot.
