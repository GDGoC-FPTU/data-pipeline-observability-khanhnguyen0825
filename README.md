[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574025&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** khanh@example.com
**Name:** Khánh Nguyễn

---

## Mo ta

Đây là bài lab minh họa quy trình xây dựng một ETL Pipeline tự động với các bước Extract (Đọc dữ liệu), Validate (Kiểm tra và chuẩn hóa), Transform (Biến đổi), và Load (Lưu trữ). Qua đó, mình đã trực tiếp trải nghiệm và phân tích tác động của Dữ liệu Sạch (Clean Data) so với Dữ liệu Rác (Garbage Data) đến các suy luận và chỉ dẫn của một thành phần AI (Agent Simulation).  

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
Mở terminal và chạy lệnh bên dưới. Script sẽ tuần tự phân tích file gốc `raw_data.json`, tiến hành loại bỏ các dữ liệu rác, xử lý dữ liệu và tạo ra file đầu ra `processed_data.csv`.
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
Lần lượt tạo tập dữ liệu rác và tiến hành chạy mô phỏng AI Agent với dữ liệu tương ứng để xem sự khác biệt về quyết định được xuất ra terminal (Laptop vs Nuclear Reactor).
```bash
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── garbage_data.csv         # Garbage data file
├── generate_garbage.py      # Generate garbage dataset test
├── agent_simulation.py      # Test AI Agent response
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- Tổng số records trích xuất ban đầu: 5
- Số records hợp lệ, được xử lý: 3
- Số records đã bị lọc do lỗi/thiếu trường dữ liệu: 2
- Phân tích thử nghiệm AI Agent: Qua thử nghiệm, mình nhận thấy khi cung cấp dữ liệu sạch (sau quá trình ETL), Agent hoạt động rất chuẩn xác và đề xuất đúng thiết bị. Tuy nhiên, nếu bỏ qua bước tiền xử lý (Dữ liệu rác), Agent chọn phải giá trị rác ngoại lai (Outlier). Quality Data là khâu thiết yếu và quan trọng nhất cho AI.
