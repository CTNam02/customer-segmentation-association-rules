# 📊 Mini Project: Phân cụm khách hàng dựa trên luật kết hợp

## 👤 Thông tin chung
- **Môn học:** Data Mining
- **Tên dự án:** Phân cụm khách hàng dựa trên luật kết hợp
- **Phương pháp chính:** Association Rules (Apriori, FP-Growth) + K-Means Clustering
- **Hình thức học:** Mini Project / FIT-DNU CONQUER

---

## 🎯 Mục tiêu dự án
Dự án nhằm mục tiêu phân nhóm khách hàng dựa trên **hành vi mua sắm**, thông qua:
- Khai phá **luật kết hợp** (association rules) từ dữ liệu giao dịch
- Biến các luật này thành **đặc trưng hành vi**
- Áp dụng **thuật toán phân cụm không giám sát (K-Means)**
- Diễn giải kết quả cụm và đề xuất **chiến lược marketing phù hợp**

Khác với cách tiếp cận truyền thống (RFM thuần), dự án tập trung vào **mối quan hệ mua kèm giữa các sản phẩm**, giúp hiểu sâu hơn về cấu trúc giỏ hàng và hành vi khách hàng.

---

## 🧩 Pipeline thực hiện

1. **Tiền xử lý dữ liệu**
   - Làm sạch dữ liệu giao dịch
   - Loại bỏ hóa đơn hủy, khách hàng không hợp lệ
   - Chuẩn hóa định dạng dữ liệu

2. **Tạo ma trận giỏ hàng (Basket Matrix)**
   - Biểu diễn dữ liệu dạng Customer × Product
   - One-hot encoding (0/1)

3. **Khai phá luật kết hợp**
   - Áp dụng thuật toán **Apriori** và **FP-Growth**
   - Lọc luật theo các tiêu chí:
     - Support
     - Confidence
     - Lift
   - Lựa chọn Top-K luật mạnh để làm đặc trưng

4. **Trích xuất đặc trưng từ luật**
   - Mỗi luật tương ứng với một feature
   - Khách hàng “kích hoạt” luật nếu thỏa tiền đề của luật đó
   - (Có thể mở rộng: rule-weighted, rule + RFM)

5. **Phân cụm khách hàng**
   - Chuẩn hóa dữ liệu
   - Chọn số cụm K bằng **Silhouette Score**
   - Huấn luyện mô hình **K-Means**
   - Gán nhãn cụm cho từng khách hàng

6. **Trực quan hóa & đánh giá**
   - Giảm chiều bằng **PCA**
   - Vẽ biểu đồ phân bố cụm 2D
   - Phân tích đặc trưng nổi bật của từng cụm

7. **Dashboard Streamlit**
   - Hiển thị kết quả phân cụm
   - Lọc theo cụm khách hàng
   - Xem các luật mua sắm nổi bật theo cụm

---

## 📁 Cấu trúc thư mục
mini_project_customer_clustering/
│
├── miniproject.ipynb # Notebook xử lý dữ liệu & phân cụm
├── app.py # Dashboard Streamlit
├── README.md # Mô tả dự án
│
├── OnlineRetail.xls # Dữ liệu giao dịch gốc
├── rules_apriori_filtered.csv # Luật Apriori đã lọc
├── rules_fpgrowth_filtered.csv # Luật FP-Growth đã lọc
├── Ket_qua_Phan_cum.csv # Kết quả phân cụm khách hàng
│
├── .gitignore

