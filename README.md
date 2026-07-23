# Cuoc-thi-WRO-B6-2026
Chương trình điều khiển robot tự hành sử dụng **Matrix Mini R4**, bộ công cụ **MATRIX WRO Future Innovators Set V2**. Robot thực hiện nhiệm vụ di chuyển theo luật thi đấu bằng cảm biến khoảng cách, cảm biến màu và camera AI.

## Hướng dẫn tải arduino
- Đầu tiên cần truy cập vào link
- https://www.matrixrobotics.com/adv-program-resources
- Kéo cho đến khi nhìn thấy chữ download arduino IDE như ảnh dưới đây, sau đó bấm download
- <img width="648" height="171" alt="image" src="https://github.com/user-attachments/assets/72b0a768-fade-4eb1-ac12-deabcfcb3846" />
- Sau khi tải xong, ta cần mở thư mục lên vào phần download, tìm arduino IDE và mở nó lên. Sau khi mở lên nó sẽ hiện như sau
- <img width="373" height="288" alt="Screenshot 2026-07-23 151909" src="https://github.com/user-attachments/assets/825dd7c0-7065-41e9-ac37-b9f35f13208e" />
- Bấm i angree, nó sẽ hiện
- <img width="374" height="287" alt="Screenshot 2026-07-23 152145" src="https://github.com/user-attachments/assets/11093e3f-0c69-4035-a33e-a21da1d2f9ba" />
- Tiếp theo sẽ bấm next
- <img width="374" height="287" alt="Screenshot 2026-07-23 152145" src="https://github.com/user-attachments/assets/f11c214b-8f74-4ca6-94e2-7f40d19c3175" />
- Bấm install
- <img width="371" height="289" alt="Screenshot 2026-07-23 152205" src="https://github.com/user-attachments/assets/38110437-aedf-4b02-ba51-0f083db7d115" />
- Sau khi tải thành công, mở arduino lên và vào phần BOARDS MANAGE, sau đấy gõ chữ **R4** trên thanh tìm kiếm
- <img width="464" height="300" alt="image" src="https://github.com/user-attachments/assets/f5318ab5-a008-416e-9ac5-bc30a28d347c" />
- Bấm install






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
