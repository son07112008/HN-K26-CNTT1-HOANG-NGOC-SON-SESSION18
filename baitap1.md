Phần 1: Phân tích tiến trình DNS

Input / Output: tên miền mà Nam đang gõ truy cập

Lỗi sai của Nam: Nam gõ nhầm thành grenlog.vn thiếu chữ 'e'. Trong "cuốn danh bạ Internet" (DNS), tên miền này không tồn tại, khiến trình duyệt trả về lỗi DNS_PROBE_FINISHED_NXDOMAIN. Máy chủ công ty hoàn toàn không bị sập.

Phần 2: Triển khai kiểm tra mạng
Dùng Chrome DevTools (F12) > Tab Network để kiểm tra mã trạng thái HTTP Status Code:

Nếu không có kết nối / lỗi NXDOMAIN: Yêu cầu chưa rời khỏi máy tính .

Nếu xuất hiện mã như 200, 404, 500: Xác nhận yêu cầu đã chạm thành công tới máy chủ.

Phần 3: Kiểm thử lỗi 404 Not Found
Nếu Nam sửa đúng tên miền nhưng vẫn nhận mã 404 Not Found, điều đó chứng minh kết nối mạng bình thường và đã đến được máy chủ, nhưng đường dẫn URL hoặc tài nguyên truy cập không tồn tại trên hệ thống.