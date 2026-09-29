# Kế hoạch review từ lỗi quan sát được

Từ \indings.csv\ và \zone_table.md\, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở %_sampling_plan.csv\.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| Edge zone | Nhiều ca MISSING và WRONG_CLASS do méo | Đây là vùng điểm mù dễ xảy ra tai nạn nhất | Ảnh so sánh L và R, chỉ ra tỷ lệ biến dạng |
| Ignore region | Lỗi IGNORE_SCOPE do lẹm mui xe | Dễ gây nhiễu cho AI nếu học vào phần xe của mình | Cắt ảnh chứa vùng lẹm |

Giới hạn của kết luận từ ba frame ADASIND: Ba frame chỉ là số lượng quá nhỏ, không đại diện cho tất cả các tình huống thời tiết, ánh sáng và bối cảnh giao thông khác.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở %_sampling_plan.csv\ (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh
như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: Cần đảm bảo phân bổ ngẫu nhiên dựa trên các tag khó (mưa, đêm, ngược sáng). Không đếm frame kề nhau vì chúng mang cùng lượng thông tin. Kế hoạch này chỉ khoanh vùng rủi ro, còn tỷ lệ lỗi thực tế phải đo trên toàn tập dữ liệu lớn hơn.
