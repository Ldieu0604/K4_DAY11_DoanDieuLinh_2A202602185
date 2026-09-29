# Quan sát vạch ô đỗ

- Hai vạch `parking_line` đã vẽ (mô tả vị trí trong ảnh): Các vạch kẻ sơn trắng phân chia ô đỗ xe ở khu vực trung tâm và hai bên bãi đỗ.
- Một vạch/dấu sơn hoặc biên **không** vẽ, và vì sao: Không vẽ các vạch lề đường (curb) vì chúng không dùng để chia ô đỗ xe (chỉ lấy vạch đỗ).
- Polygon `free_space` dừng ở đâu; có phần bị che nào không: Dừng ở rìa các xe đang đỗ và vật cản; có bị che khuất một phần bởi bóng râm và đầu xe.
- Ca chưa chắc cần hỏi người soát (nếu không có, ghi “không có”): Các vạch sơn bị mờ hoặc bị xe đè lên gần hết.
