# Exit ticket

Đọc \docs/10-svm360-reading-vi.md\ trước khi trả lời câu 1–2. Các câu về zone, \why\, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đó là lỗi \DUPLICATE\ hay cần một quy
   tắc riêng? Vì sao? 
   -> Cần một quy tắc riêng (Cross-camera tracking policy) vì về mặt vật lý đó là 1 vật thể, nhưng trên hình ảnh lại nằm ở 2 tọa độ ảnh độc lập. Nếu không xử lý, hệ thống sẽ đếm thành 2 vật gây sai lệch.
2. Một vật đi qua nhiều frame trên cùng camera: khi nào giữ cùng track ID, khi nào thêm keyframe hoặc trạng thái
   Outside? Nêu bằng chứng sẽ cần trước khi nối track qua hai camera.
   -> Giữ track ID khi vật di chuyển liên tục, thêm keyframe khi có thay đổi hướng/kích thước lớn. Trạng thái Outside dùng khi vật ra khỏi khung hình hoàn toàn. Bằng chứng nối track: trùng timestamp và khớp vị trí vật lý.
3. Nhìn lại cả buổi: một chỗ bạn tin nhãn mình đúng nhưng reference hoặc người soát nghĩ khác (dẫn frame/\object_ref\),
   bạn đã xử lý thế nào, và nếu làm lại slice này bạn sẽ đổi gì trong cách làm?
   -> Tại adasind_271039.jpg (L2), tôi vẽ Car nhưng reference là ThreeWheeler. Tôi đã chọn action=keep_with_reason vì hình ảnh quá dẹt. Lần sau, tôi sẽ dùng công cụ zoom sát hơn và tham khảo các vật thể tương tự quanh đó trước khi chốt nhãn.
