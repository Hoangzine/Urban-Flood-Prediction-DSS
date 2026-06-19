# Dự báo Ngập lụt Đô thị & Hệ thống Hỗ trợ Ra quyết định (DSS)

## 📌 Tổng quan dự án
Dự án ứng dụng kỹ thuật Kho dữ liệu và Học máy nâng cao nhằm phân tích, dự báo chính xác độ sâu ngập lụt đô thị. Giải quyết triệt để các bài toán phi tuyến tính phức tạp của hệ thống thoát nước và xây dựng công cụ tự động hỗ trợ ra quyết định (Decision Engine) điều phối nguồn lực chống ngập theo thời gian thực.

## 🛠 Tech Stack
* **Ngôn ngữ:** Python
* **Kỹ thuật dữ liệu:** Data Warehouse (Star Schema), OLAP Cube Operations
* **Thuật toán & Mô hình:** Regularized Random Forest, Ordinary Least Squares (OLS) Regression
* **Định khung quy trình:** CRISP-DM Framework
* **Giải thích AI:** SHAP (Explainable AI - XAI)

## 🚀 Quy trình thực hiện & Kết quả cốt lõi

### 1. Kiến trúc dữ liệu & Feature Engineering
* Xây dựng mô hình Star Schema tích hợp đồng bộ dữ liệu đo đạc thực tế và dữ liệu vệ tinh quốc tế (NASA, Open-Meteo). Thực thi 6 phép toán OLAP để khai phá tương quan đa chiều.
* Kiến tạo các đặc trưng thủy lực chuyên sâu: *Rain Intensity* (Cường độ mưa) và *Drainage Stress Index* (Chỉ số áp lực thoát nước) nhằm mô phỏng chính xác áp lực lên hệ thống cống ngầm.

### 2. Mô hình hóa nâng cao (Advanced Predictive Modeling)
* Huấn luyện mô hình **Regularized Random Forest** kết hợp kỹ thuật 5-fold Cross-validation để kiểm soát chặt chẽ hiện tượng overfitting, thay thế hoàn toàn cho mô hình Baseline OLS tuyến tính truyền thống.
* **Kết quả:** Xử lý thành công các biến động hỗn loạn của thiên tai, nâng năng lực giải thích mô hình ($R^2$ Score) lên **16 lần** và tối ưu hóa sai số RMSE xuống ngưỡng an toàn **14.66 cm**.

### 3. Giải thích AI & Hệ thống Ra quyết định (DSS)
* Ứng dụng lý thuyết trò chơi **SHAP** để bóc tách định lượng cơ chế tác động của từng biến số (Cường độ mưa, cao độ địa hình) đến kết quả dự báo, loại bỏ tính chất "hộp đen" của AI.
* Tích hợp thuật toán vào hệ thống hỗ trợ ra quyết định tự động, kích hoạt chính xác 3 cấp độ kịch bản thực chiến (Cảnh báo thông minh -> Điều phối xe bơm di động -> Phong tỏa lộ trình & Kích hoạt cửa ngăn lụt tòa nhà).
