# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600404
**Name:** Nguyễn Thành Đại Khánh
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 10 | Agent trả về kết quả chính xác, đưa ra quyết định hợp lý dựa trên dữ liệu chuẩn. |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Agent hoàn toàn bị đánh lừa bởi dữ liệu rác (chứa giá trị ngoại lai - outlier khủng). |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent đưa ra lựa chọn sai lệch hoàn toàn vì quá trình ra quyết định của nó phụ thuộc trực tiếp vào dữ liệu đầu vào. Khi ta cung cấp dữ liệu rác (Garbage Data) có chứa các giá trị ngoại lai (outliers) phi lý trí như "Nuclear Reactor" với giá $999999, mô hình sẽ tính toán sai. Các vấn đề phổ biến như trùng lặp ID (Duplicate IDs), sai kiểu dữ liệu (wrong data types), hay giá trị trống (null values) đều làm hỏng cấu trúc phân tích nội bộ của AI, khiến mọi suy luận tiếp theo rẽ sang một hướng hoàn toàn sai lệch.

(Hay phan tich cac van de nhu Duplicate IDs, wrong data types, outliers, null values
va giai thich tai sao chung anh huong den ket qua cua Agent.)

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Hoàn toàn đồng ý. Chất lượng dữ liệu (Quality Data) đặc biệt quan trọng hơn câu lệnh (Quality Prompt) vì theo quy tắc "Garbage In - Garbage Out" (Đầu vào là rác thì Đầu ra cũng là rác). Dù bạn có viết prompt xuất sắc đến đâu, nếu AI chỉ có thể học và phân tích trên một tập dữ liệu sai lệch thì mọi đáp án nó tạo ra đều vô giá trị.
