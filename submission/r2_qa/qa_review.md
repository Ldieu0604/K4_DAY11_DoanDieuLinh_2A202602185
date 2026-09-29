# Báo cáo QA Độc Lập

- Người QA (B): Lã Việt Quang (2A202602289)
- Người vẽ nhãn (A): Hoàng Công Chứ (2A202602187)
- Slice: B4-center
- Mã khóa kiểm tra: 0F8C-A774

## Các nhận xét (Findings)

1. Frame `adasind_270517.jpg` → Đối tượng `L1` → Quy tắc `R01`: Box vẽ cho chiếc xe máy ở xa trông có vẻ nhỏ hơn 40px, cần A kiểm tra lại kích thước gốc.
2. Frame `adasind_271039.jpg` → Đối tượng `L3` → Quy tắc `R15`: Trạng thái `truncated` chưa được bật dù xe chạm sát mép viền đen (lens_border).
3. Frame `adasind_295948.jpg` → Đối tượng `L5` → Quy tắc `R09`: Box hơi lẹm quá nhiều (>50%) vào vùng `ignore_region`, cần cân nhắc bỏ.

*Lưu ý: B chỉ ghi nhận xét, chưa mở reference/model để xem đáp án chuẩn.*
