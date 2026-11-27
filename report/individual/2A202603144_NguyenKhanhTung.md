# Báo cáo Day 14 — Nguyễn Khánh Tùng — 2A202603144

- Mã học viên dùng với `--student`: `2A202603144`
- `seed_tag` trong `frames_A.txt`: `393590736f`

## 1. Dự đoán trước sweep (bước 5b)

Ghi **trước** khi chạy `scripts/pp_sweep.py`, rồi commit và push ngay (lịch sử commit là bằng chứng thời điểm viết). Không sửa phần này sau khi có kết quả.

- Tham số tôi nghĩ giảm công sửa nhiều nhất: tăng `score_thr` (khoảng `0.3–0.4`), có thể kết hợp `min_points` nhỏ (`5`) để lọc nhiễu ở vùng ngoài.
- Vì sao (nhìn ảnh BEV tập A: box thừa nhiều hay box sót nhiều?): Quan sát 3 ảnh tập A và kết quả sửa tay thấy các vùng ngoài cùng không có vật thể bị model gán box thừa rất nhiều (tổng 46 box phải xóa, chiếm 13,8/17,8 điểm chi phí gốc), trong khi số box bị sót rất ít (chỉ 1–2 box mỗi frame, tổng 4 box thêm) và gần như không có box bị đánh sai class (0 box sửa). Vì box thừa chiếm đa số chi phí và chủ yếu tập trung ở vùng rìa/điểm thưa, tăng `score_thr` (và lọc nhẹ `min_points`) được kỳ vọng sẽ cắt mạnh lượng box cần xóa mà không làm mất nhiều box thật.

## 2. Tập A: sửa tay và tune

| Cấu hình | Xóa | Thêm | Sửa | Chi phí |
|---|---:|---:|---:|---:|
| Gốc | 46 | 4 | 0 | 17.8 |
| `best_config.json` | [BẠN TỰ ĐIỀN] | | | |

- Tham số đã đổi trong `best_config.json`: [BẠN TỰ ĐIỀN]
- Kết quả leave-one-out (dán các dòng `scripts/pp_sweep.py` in ra): [BẠN TỰ ĐIỀN]
- Cấu hình có ổn định trên từng frame không? Vì sao tôi vẫn chọn (hoặc không chọn) nó: [BẠN TỰ ĐIỀN]

## 3. Trước/sau (bước 8)

![so sánh](../../d14_2A202603144/compare/<frame>.jpg)

- `scripts/pp_compare.py` báo giảm (hoặc tăng) [BẠN TỰ ĐIỀN]% công sửa trên tập A.
- Dự đoán ở mục 1 đúng hay sai? Giải thích bằng số box xóa/thêm/sửa: [BẠN TỰ ĐIỀN]

## 4. Tập B

Số đo từ `scripts/pp_prelabel.py --frames d14_2A202603144/frames_B.txt --config d14_2A202603144/best_config.json --gt d14_2A202603144/ref_B.json`:

| Xóa | Thêm | Sửa | Chi phí |
|---:|---:|---:|---:|
| [BẠN TỰ ĐIỀN] | | | |

- Loại box tốn công sửa nhất ở tập B: [BẠN TỰ ĐIỀN]

## 5. Giới hạn

- [BẠN TỰ ĐIỀN — Nêu ít nhất 2 giới hạn (ví dụ: chỉ 3 frame tune; model KITTI không có Truck/Bus; chi phí là công thức, chưa phải thời gian sửa thật)]
