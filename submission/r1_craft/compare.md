# So sánh L với R

Chỉ số L/R là thứ tự box cao ≥ H=40 trong từng frame, theo thứ tự XML; bắt đầu từ 1.
Box L trong ignore_region được báo IGNORE_SCOPE, không tính SPURIOUS.

## adasind_270517.jpg
- L7 mid IGNORE_SCOPE
## adasind_271039.jpg
- L9 center IGNORE_SCOPE
- L2+R7 mid WRONG_CLASS
- L8 center SPURIOUS
- L11 center SPURIOUS
- L12 center SPURIOUS
- R10 center MISSING
## adasind_295948.jpg
- L5 center IGNORE_SCOPE
- L6 mid IGNORE_SCOPE
- L7 mid IGNORE_SCOPE
- L8 mid IGNORE_SCOPE
- L1+R3 mid WRONG_CLASS
- L3+R1 center WRONG_CLASS
- L4 center SPURIOUS

## Theo zone
| zone | n_ref | matched | missing | spurious |
|---|---|---|---|---|
| center | 12 | 10 | 2 | 5 |
| mid | 5 | 3 | 2 | 2 |
| edge | 3 | 3 | 0 | 0 |
