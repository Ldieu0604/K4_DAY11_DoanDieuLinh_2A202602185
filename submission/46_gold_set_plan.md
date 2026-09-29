# Đề xuất gold set theo camera — tình huống giả lập

**Đầu bài:** 50.000 frame từ bốn camera SVM, ngân sách chọn 200 frame để review/gold. Đây là tình huống trên slide,
**không phải** 50.000 frame có trong repo. Phân bổ đúng 200 ở `45_sampling_plan.csv` cho bốn camera, mỗi camera có
normal và hard slice. “Gold set” ở đây là **kế hoạch tạo** reference sau kiểm chứng, không phải teaching reference
ADASIND hoặc nhãn bạn vừa vẽ. Nếu cần, dùng `notebooks/day11-svm360-colab.ipynb` để thử tổng phân bổ; notebook
không làm thay phần lý do.

| camera_id | Hard case cần chọn | Vì sao dễ sai | Annotation space / calibration cần giữ | Cách review trước khi gọi là gold |
|---|---|---|---|---|
| front | Xe bị ngược sáng, xe ở xa bị méo | Góc nhìn trực diện dễ bị chói, khoảng cách làm xe bị thu nhỏ | Giữ nguyên ảnh fisheye, lấy mốc H=40px | QA chéo 2 người, ưu tiên xem xét vật ở rìa |
| rear | Xe đi sát phía sau đuôi | Xe quá sát dễ bị lẹm vào ego_body hoặc biến dạng mạnh | Che ego_body cẩn thận, đo kích thước phần hiển thị | Review kỹ các box có nguy cơ bị `truncated` |
| left | Xe máy đi chen vào điểm mù bên hông | Tốc độ lướt qua nhanh, hình ảnh bị dẹt dọc | Giữ nguyên độ dẹt, không đoán hình dáng thực | So sánh cẩn thận giữa Car và ThreeWheeler |
| right | Tương tự left, nhưng chú ý vỉa hè/người đi bộ | Người đi bộ và xe máy dễ lẫn vào các vật thể bên đường | Áp dụng chặt rule `ignore_region` cho lens border | B bắt buộc soi kỹ các góc để không bỏ sót |

- Khi nào cần refresh gold set (đổi camera, calibration hoặc rule): Khi đổi loại camera, thay đổi vị trí gắn (góc nghiêng/độ cao), hoặc khi dự án cập nhật rule gán nhãn mới làm thay đổi định nghĩa class.
- Một ca seam/cross-camera cần policy và evidence trước khi ghép hai box: Cần chính sách nối ID (Tracking) và bằng chứng là vật thể xuất hiện đồng thời trên cả 2 camera (trùng mốc thời gian và có tính logic về không gian).
- Vì sao peer agreement hoặc quality report trên ảnh một camera chưa chứng minh gold set đúng cho cả bốn camera: Vì mỗi góc camera (front/rear/sườn) có độ méo fisheye, điểm mù và loại phương tiện xuất hiện đặc thù khác nhau hoàn toàn. Đánh giá tốt ở cam trước không đồng nghĩa với việc cam hông không bị lỗi.
