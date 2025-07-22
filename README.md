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

### 1. Local Search (`local_search.py`) - Main
- **Mục đích:**
  - Tìm ra optimal offloading decisions và resource allocation.
  - Kết hợp với thuật toán Bi-search(link đến file test_bi_search.py, hoặc đề mục số 2.Bi-search bên dưới),để tìm optimal energy-time, nhằm allocate resource tốt nhất.
  - Chạy một số vòng lặp, sau mỗi vòng lặp, so sánh energy-time cost để decide best optimal offloading solution và allocate offload-local resources(1-offload, 0-loca) hợp lý.
- **Khi sử dụng:**
  - Khi cần giải pháp nhanh, chấp nhận nghiệm gần tối ưu.
  - Khi không gian nghiệm lớn, vét cạn không khả thi.
- **Chạy thử:**
  Tại file .ipynb, thay `test_file_path = '/content/MECOptimalOffloading/mecoptimaloffloading/tests/test_local_search.py'`
- **Kết quả:**
  - Kết quả chạy xuất ra màn hình gồm có: 1 dictionary: 2 offloading decisions tương ứng cho WD1 và WD2; và energy-time cost của WD1 và WD2.

### 2. Bi-Search (`bi_search.py`)
- **Mục đích:**
  - Tìm ra optimal energy-time.
  - Offloading decision được giả thiết là đã được cho sẵn (given) - bằng cách sinh ngẫu nhiên.
  - Chạy file trong trường hợp muốn thử nghiệm và quan sát sự thay đổi energy-time, khi beta2_t thay đổi.
- **Khi sử dụng:**
  - Khi muốn cân bằng giữa tốc độ và chất lượng nghiệm.
  - Khi cần so sánh hiệu quả với local search và naive search.
- **Chạy thử:**
  Tại file .ipynb, thay `test_file_path = '/content/MECOptimalOffloading/mecoptimaloffloading/tests/test_bi_search.py'`
- **Kết quả:**
  - Kết quả được trực quan hóa bằng matplotlib, thể hiện mối quan hệ giữa energy và time với beta2_t tương ứng của WD1 và WD2.

### 3. Naive Search (`naive_search.py`)
- **Mục đích:**
  - Tìm kiếm vét cạn toàn bộ không gian nghiệm để tìm ra optimal solutions.
  - Duyệt tất cả các optimal decisions khả thi (2^(M+N) choices), từ đó tìm được best offloading decisions/energy-time cost.
- **Khi sử dụng:**
  - Khi muốn kiểm tra nghiệm tối ưu thực sự (benchmark cho các thuật toán khác).
  - Khi không gian nghiệm nhỏ (vì độ phức tạp cao).
- **Chạy thử:**
  Tại file .ipynb, thay `test_file_path = '/content/MECOptimalOffloading/mecoptimaloffloading/tests/test_naive_search.py'`
- **Kết quả:**
  - Kết quả chạy xuất ra màn hình gồm có: 1 dictionary: 2 offloading decisions tương ứng cho WD1 và WD2; và energy-time cost của WD1 và WD2.

---

## 🧪 Kiểm tra & Đánh giá
- **Kết quả:**
  - Kết quả và hình ảnh minh họa của 3 thuật toán được lưu trong thư mục `mecoptimaloffloading/results/tên_thuật_toán_tương_ứng`

---

## 📊 Khi nào nên dùng từng thuật toán?

| Thuật toán      | Ưu điểm                 | Nhược điểm                | Khi nên dùng                |
|-----------------|-------------------------|---------------------------|-----------------------------|
| Naive Search    | Đảm bảo tối ưu tuyệt đối| Rất chậm với bài toán lớn | Benchmark, không gian nhỏ   |
| Local Search    | Nhanh, dễ mở rộng       | Có thể kẹt local optimum  | Không gian lớn, cần nghiệm tốt nhanh |
| Bi-Search       | Cân bằng tốc độ & chất lượng | Cần thiết kế tốt, phức tạp hơn | So sánh, tối ưu nâng cao    |

---

