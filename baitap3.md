Phần 1: Phân tích Box Model (Tab Computer)

![](image-1.png)

Nguyên nhân lỗi: Khung "Thông tin tài xế" đang bị đè lên khung "Danh sách trạm" do thông số margin-bottom (hoặc margin bên phải) đang bị gán giá trị âm (ví dụ: -25px), khiến phần tử bị kéo lệch vị trí và chồng lấn sang khu vực kế cận.

4 lớp Box Model: Gồm Content (nội dung), Padding (12px), Border (1px solid), và Margin (chứa giá trị âm gây lỗi).

Phần 2: Triển khai giải pháp (Tab Styles)
Chỉnh sửa trực tiếp tại bảng Styles trong DevTools:

Đổi giá trị margin âm thành dương
Thêm thuộc tính box-sizing: border-box; để trình duyệt tự động tính toán kích thước chuẩn, giữ cho tổng thể layout không bị vỡ.

Phần 3: Kiểm thử sự cố ghi đè
Nếu thay đổi Margin mà phần tử vẫn không di chuyển, cần kiểm tra:

Cờ !important: Đoạn mã CSS hệ thống có thể đang ghi đè, cần thêm !important vào giá trị mới.

Thuộc tính position: Nếu phần tử đang ở dạng absolute hoặc fixed, các thuộc tính margin sẽ bị vô hiệu hóa hoặc bị chi phối bởi tọa độ (top, left,...).

Mô hình Flexbox/Grid: Nếu thẻ cha dùng Flex/Grid, vị trí sẽ do các thuộc tính căn chỉnh của container điều khiển.