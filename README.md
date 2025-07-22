# MECOptimalOffloading

## 🚀 Giới thiệu

**MECOptimalOffloading** là một dự án mô phỏng và tối ưu hóa quá trình offloading trong hệ thống tính toán biên di động (Mobile Edge Computing - MEC). Dự án cung cấp ba thuật toán chính để giải quyết bài toán tối ưu hóa: **Naive Search**, **Local Search**, và **Bi-Search**.

---

## 📂 Cấu trúc thư mục

- `mecoptimaloffloading/algorithms/`
  - `naive_search.py`: Thuật toán tìm kiếm vét cạn (Naive Search)
  - `local_search.py`: Thuật toán tìm kiếm cục bộ (Local Search)
  - `bi_search.py`: Thuật toán tìm kiếm hai phía (Bi-Search)
- `mecoptimaloffloading/results/`: Kết quả và hình ảnh minh họa
- `mecoptimaloffloading/tests/`: Bộ test cho từng thuật toán

---

## ⚙️ Hướng dẫn cài đặt

Chạy từng cell trong jupyter notebook

---

## 🧩 Hướng dẫn chạy các thuật toán

### 1. Naive Search (`naive_search.py`)
- **Mục đích:**
  - Tìm kiếm vét cạn toàn bộ không gian nghiệm để tìm ra optimal offloading decisions.
- **Khi sử dụng:**
  - Khi muốn kiểm tra nghiệm tối ưu thực sự (benchmark cho các thuật toán khác).
  - Khi không gian nghiệm nhỏ (vì độ phức tạp cao).
- **Chạy thử:**
  Thay ```bash
  test_file_path
  ```

### 2. Local Search (`local_search.py`)
- **Mục đích:**
  - Tìm kiếm nghiệm tốt bằng cách xuất phát từ một nghiệm ban đầu và cải thiện dần qua các bước lân cận.
- **Khi sử dụng:**
  - Khi cần giải pháp nhanh, chấp nhận nghiệm gần tối ưu.
  - Khi không gian nghiệm lớn, vét cạn không khả thi.
- **Chạy thử:**
  ```bash
  python -m mecoptimaloffloading.algorithms.local_search
  ```

### 3. Bi-Search (`bi_search.py`)
- **Mục đích:**
  - Kết hợp hai hướng tìm kiếm (thường là từ hai phía hoặc hai tập nghiệm) để tăng tốc độ hội tụ và khả năng tìm nghiệm tốt.
- **Khi sử dụng:**
  - Khi muốn cân bằng giữa tốc độ và chất lượng nghiệm.
  - Khi cần so sánh hiệu quả với local search và naive search.
- **Chạy thử:**
  ```bash
  python -m mecoptimaloffloading.algorithms.bi_search
  ```

---

## 🧪 Kiểm tra & Đánh giá

- **So sánh kết quả:**
  - Chạy cả 3 thuật toán trên cùng một bộ dữ liệu để so sánh chất lượng nghiệm và thời gian chạy.
- **Kiểm thử tự động:**
  ```bash
  python -m mecoptimaloffloading.tests.test_naive_search
  python -m mecoptimaloffloading.tests.test_local_search
  python -m mecoptimaloffloading.tests.test_bi_search
  ```
- **Kết quả:**
  - Kết quả và hình ảnh minh họa được lưu trong thư mục `mecoptimaloffloading/results/`

---

## 📊 Khi nào nên dùng từng thuật toán?

| Thuật toán      | Ưu điểm                 | Nhược điểm                | Khi nên dùng                |
|-----------------|-------------------------|---------------------------|-----------------------------|
| Naive Search    | Đảm bảo tối ưu tuyệt đối| Rất chậm với bài toán lớn | Benchmark, không gian nhỏ   |
| Local Search    | Nhanh, dễ mở rộng       | Có thể kẹt local optimum  | Không gian lớn, cần nghiệm tốt nhanh |
| Bi-Search       | Cân bằng tốc độ & chất lượng | Cần thiết kế tốt, phức tạp hơn | So sánh, tối ưu nâng cao    |

---

## 📞 Liên hệ & Đóng góp

- Nếu bạn có ý tưởng cải tiến hoặc phát hiện lỗi, hãy tạo issue hoặc pull request.
- Mọi đóng góp đều được hoan nghênh!

---

**Chúc bạn tối ưu hóa thành công!**
