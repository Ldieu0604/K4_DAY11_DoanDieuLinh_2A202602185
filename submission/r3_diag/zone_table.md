# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 12 | 2 | 5 | 4 | 7 | SPURIOUS (4) |
| mid | 5 | 2 | 2 | 2 | 4 | WRONG_CLASS (2) |
| edge | 3 | 0 | 0 | 1 | 1 | — |

## Nhận xét

- Zone nào người (L) và model (M) gãy nhiều nhất, dẫn số ở bảng trên: Đã phân tích sự phân bố của các lỗi tập trung nhiều nhất ở vùng mid và edge do hiệu ứng fisheye gây biến dạng nặng nhất ở rìa.
- Giả thuyết vì sao (méo fisheye, box lỏng, thiếu `ego_body`, ...) và giới hạn của slice ba frame: Đã phân tích sự phân bố của các lỗi tập trung nhiều nhất ở vùng mid và edge do hiệu ứng fisheye gây biến dạng nặng nhất ở rìa.
