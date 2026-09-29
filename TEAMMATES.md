# Thành viên và phân vai — Day11 SVM 360 Fisheye

## 1. Thông tin nhóm

- Khóa/lớp: Nhomcuatoi
- Tên nhóm: Nhóm CVAT Fisheye
- Repo Public: [github.com/Ldieu0604/K4_DAY11_Nhomcuatoi.git](https://github.com/Ldieu0604/K4_DAY11_Nhomcuatoi.git)
- Máy giữ hồ sơ chính / người quản lý: Đoàn Diệu Linh
- Slice chung lấy từ mode.json: B4-center
- Tên định danh vai A dùng cho --self: doandieulinh
- Kênh trao đổi nội bộ: Zalo
- Đại diện nộp (vai A): Đoàn Diệu Linh, 2A202602185
- Commit chốt bài: [Cập nhật sau khi push lên Github]

## 2. Ba vai chính

| Vai | Họ và tên | MSSV | Tên định danh trong mode | Trách nhiệm | Bằng chứng đóng góp |
|---|---|---|---|---|---|
| A · Gán nhãn | Đoàn Diệu Linh | 2A202602185 | doandieulinh | Parking/C0/slice, self-QC, lock, rework | Thực hiện r1_craft, lock mã 0F8C-A774, lock rework 1069-08F4 |
| B · QA độc lập | Lã Việt Quang | 2A202602289 | lavietquang | Review trước reference, finding QA, kiểm lại ca sửa | Tạo qa_review.md và 3 lỗi r2_qa trong findings.csv |
| C · Chẩn đoán & điều phối | Hoàng Công Chứ | 2A202602187 | hoangcongchu | Báo cáo, phân xử, kế hoạch, tích hợp, check và nộp | Chạy lệnh compare, chẩn đoán lỗi r3_diag, viết Exit Ticket |

Bảng này xác định vai của nhóm. Vòng QA tự sinh trong team.json thuộc quy trình nhiều hồ sơ của CLI; nhóm dùng một slice chung và quy trình A → B → C đã nêu trong hướng dẫn.

## 3. Bàn giao theo pha

| Mốc | Người giao → nhận | File / commit / mã khóa | Người nhận đã kiểm gì? | Trạng thái / vướng mắc |
|---|---|---|---|---|
| P0 · Chốt môi trường và vai | C → A, B | mode.json, B4-center | Cài đặt Python và CVAT | Thành công |
| P2 · Khóa bản đầu | A → B, C | r1-draft.xml, 0F8C-A774 | Kiểm tra lỗi L5, L9 bằng selfqc | Thành công |
| P3 · Chốt QA mù | B → C, A | qa_review.md, findings.csv | Kiểm tra 3 lỗi QA độc lập không cần reference | Thành công |
| P4 · Quyết định sửa | C → A, B | findings.csv, decision_log | Đối chiếu reference và phân xử lỗi fisheye | Thành công |
| P5 · Kiểm bản sửa | A → B → C | v2, lock 1069-08F4 | So sánh delta.md để xem mức cải thiện | Thành công |
| P6 · Chốt nộp | A, B → C | manifest, check exit 0 | Chạy lab11.py check và zip hồ sơ | Sẵn sàng nộp |

## 4. Bất đồng và phối hợp

- Một ca đã phân xử: Ảnh adasind_271039.jpg đối tượng L2, C quyết định keep_with_reason vì ảnh quá méo để nhận diện rõ Car hay ThreeWheeler.
- Ca còn mở: Không còn ca nào mở, tất cả đã được phân xử và quyết định rework/keep.
- Đóng góp của A/B/C vào kế hoạch và exit ticket: Cả nhóm đã cùng bàn luận để điền phần 46_gold_set_plan (phân tích 4 camera) và 50_exit_ticket.
- Thay đổi phân công nếu có: Không thay đổi phân công.

## 5. Xác nhận trước khi nộp

- [x] A xác nhận nhãn và export đúng phiên bản: Hoàng Công Chứ (Mã lock: 1069-08F4)
- [x] B xác nhận đã QA độc lập trước reference và kiểm lại ca sửa: Lã Việt Quang (File qa_review.md)
- [x] C xác nhận báo cáo đúng bản khóa, các file đầy đủ và check exit 0: Đoàn Diệu Linh (triage pass)
- [x] manifest.json tại commit chốt có failed_gates rỗng.
- [x] Repo nhóm Public, ảnh và các bằng chứng mở được.
- [X] C đã push và gửi link repo nhóm + commit qua kênh lớp công bố.

Chỉ đánh dấu việc đã kiểm thật. Nhóm nộp một hồ sơ chung; check không tự chấm đóng góp từng người. Giữ nguyên header/các cột enum của findings.csv; tên người được ghi trong tài liệu này hoặc phần note thích hợp.
