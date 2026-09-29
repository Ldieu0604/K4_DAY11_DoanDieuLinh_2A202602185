# Đối chiếu chất lượng cục bộ — rectangle

Teaching reference, không phải gold set đã phê duyệt; không có điểm đạt tự động.
Nguồn: export r1_craft đã khóa SHA256 `0f8ca774b9f63f4e9a1b71706e4d1b8339170cefe4b3eb0bbe665b3362a64383`; slice `B4-center`.
Ghép hình học greedy một-một theo IoU ≥ 0.50, rồi so class; H ≥ 40 px.
Box trái nằm chủ yếu trong ignore_region reference không tính. Polygon, polyline, track không được chấm.
Đây là phép tính offline của lab, không phải báo cáo hay kết quả tương đương CVAT Premium.

Frame được tính: adasind_270517.jpg, adasind_271039.jpg, adasind_295948.jpg. Frame thiếu trong export: không.
TP=16; FP=7; FN=4; số lần đối chiếu=24; mean IoU của TP=0.808.

| Chỉ số | Micro | Macro | Nhãn thấp nhất |
|---|---:|---:|---:|
| accuracy | 0.667 | 0.924 | 0.875 |
| precision | 0.696 | 0.611 | 0.000 |
| recall | 0.800 | 0.687 | 0.000 |
| jaccard | 0.593 | 0.500 | 0.000 |
| dice | 0.744 | 0.622 | 0.000 |

| Nhãn | TP | FP | FN | Accuracy | Precision | Recall | Jaccard | Dice |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Bike | 2 | 0 | 1 | 0.958 | 1.000 | 0.667 | 0.667 | 0.800 |
| Bus | 0 | 1 | 0 | 0.958 | 0.000 | 0.000 | 0.000 | 0.000 |
| Car | 3 | 1 | 2 | 0.875 | 0.750 | 0.600 | 0.500 | 0.667 |
| Pedestrian | 6 | 2 | 1 | 0.875 | 0.750 | 0.857 | 0.667 | 0.800 |
| ThreeWheeler | 4 | 2 | 0 | 0.917 | 0.667 | 1.000 | 0.667 | 0.800 |
| Truck | 1 | 1 | 0 | 0.958 | 0.500 | 1.000 | 0.500 | 0.667 |

| Frame | TP | FP | FN | Accuracy | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| adasind_270517.jpg | 7 | 0 | 0 | 1.000 | 1.000 | 1.000 |
| adasind_271039.jpg | 8 | 4 | 2 | 0.615 | 0.667 | 0.800 |
| adasind_295948.jpg | 1 | 3 | 2 | 0.250 | 0.250 | 0.333 |

Confusion matrix: hàng = teaching reference; cột = export đã khóa.
`<missing>` là thiếu box; `<extra>` là box thừa. Xem `local_quality_confusion.csv`.

| Reference \ Export | Bike | Bus | Car | Pedestrian | ThreeWheeler | Truck | <missing> |
|---|---:|---:|---:|---:|---:|---:|---:|
| Bike | 2 | 0 | 0 | 1 | 0 | 0 | 0 |
| Bus | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| Car | 0 | 0 | 3 | 0 | 1 | 1 | 0 |
| Pedestrian | 0 | 0 | 0 | 6 | 0 | 0 | 1 |
| ThreeWheeler | 0 | 0 | 0 | 0 | 4 | 0 | 0 |
| Truck | 0 | 0 | 0 | 0 | 0 | 1 | 0 |
| <extra> | 0 | 1 | 1 | 1 | 1 | 0 | 0 |

Chi tiết xung đột trong `local_quality_conflicts.csv`; dữ liệu máy đọc trong `local_quality.json`.
Mismatching label đóng góp một FP cho class vẽ và một FN cho class reference; attribute khác được báo riêng.
Micro accuracy đếm mỗi cặp ghép sai class là một lần đối chiếu; Jaccard đếm cả FP và FN.
Macro/worst bỏ nhãn không xuất hiện ở cả hai phía; chỉ số không có mẫu là N/A.
