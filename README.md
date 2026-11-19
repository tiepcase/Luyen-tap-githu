# Dự án Nghiên cứu Tái lập: Mô phỏng Lưới điện Phân phối IEEE 33 Nút (Replication Study)

## 1. Giới thiệu tổng quan
Dự án này là một **nghiên cứu tái lập (Replication / Reproduction Study)** nhằm kiểm chứng, mô phỏng lại và đánh giá độ chính xác các kết quả tính toán từ bài báo khoa học tham chiếu trên hệ thống lưới điện phân phối chuẩn IEEE 33 nút.

* **Tài liệu tham chiếu gốc:** `PEJARD_2026.01.26.pdf`
* **Công cụ mô phỏng:** OpenDSS (EPRI Open Distribution System Simulator)
* **Đối tượng lưới điện:** Lưới phân phối hình tia IEEE 33 nút (12.66 kV, công suất cơ sở ~3.715 MW và 2.3 MVAR).

---

## 2. Mục tiêu nghiên cứu
1. **Tái lập mô hình phụ tải 24 giờ:**
   - Phụ tải cơ sở phân theo khu vực (Thương mại - Commercial, Công nghiệp - Industrial, Dân cư - Residential).
2. **Mô phỏng tích hợp các thành phần hiện đại:**
   - **EVCS (Electric Vehicle Charging Station):** Tích hợp trạm sạc xe điện với các đặc tuyến sạc theo khung giờ.
   - **WTDG (Wind Turbine Distributed Generation):** Nguồn điện phân tán từ turbine gió theo biểu đồ phát công suất 24h.
   - **BESS (Battery Energy Storage System):** Hệ thống pin lưu trữ năng lượng vận hành nạp/xả theo các kịch bản tối ưu.
3. **Đánh giá chỉ tiêu kỹ thuật:**
   - Tổn thất công suất và năng lượng trên lưới (Power & Energy Losses: kW, kvar, kWh, kvarh).
   - Hồ sơ điện áp (Voltage Profile) tại các nút trong chu kỳ 24 giờ.

---

## 3. Cấu trúc thư mục & Dữ liệu
* `Test31-10.dss`: File mã nguồn mô phỏng chính trên OpenDSS định nghĩa đường dây, phụ tải, trạm sạc EV, turbine gió và lưu trữ pin BESS.
* `IEEE33_EMout.Txt`: Kết quả xuất từ bộ đo năng lượng (EnergyMeter) tổng hợp sau mô phỏng 24h.
* `IEEE33_EXP_METERS.CSV`: Bảng số liệu chi tiết các thanh ghi đo đếm (registers) xuất ra định dạng CSV để vẽ biểu đồ và phân tích.
* `PEJARD_2026.01.26.pdf`: Bài báo nghiên cứu / tài liệu gốc dùng làm đối chuẩn đối chiếu.
* `README.md`: Tài liệu mô tả và hướng dẫn dự án.

---

## 4. Quy trình làm việc chuẩn (Standard Workflow)
Chu trình lặp 3 bước:
1. **Giao việc cho Antigravity:** Yêu cầu AI điều chỉnh mã OpenDSS (`.dss`), cập nhật kịch bản hoặc phân tích kết quả.
2. **Kiểm tra thay đổi (Diff):** Xem lại các dòng màu xanh (thêm mới) / màu đỏ (xóa) trong tab **Source Control** 🌿.
3. **Lưu mốc (Commit & Push):** Đặt thông điệp commit rõ ràng và đẩy mã nguồn lên GitHub để lưu trữ lịch sử nghiên cứu.
