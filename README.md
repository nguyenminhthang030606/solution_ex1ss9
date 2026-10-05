1. Phân tích lỗi & Bảng Test Cases (README.md)
Phân tích nguyên nhân lỗi:
Lỗi nằm ở dòng khai báo const basePrice = bookingReservation.priceKey;.
Trong JavaScript, khi sử dụng cú pháp dấu chấm (Dot Notation), trình duyệt/engine sẽ tìm kiếm một thuộc tính có tên chính xác là chuỗi "priceKey" bên trong đối tượng bookingReservation. Vì đối tượng này không có thuộc tính nào tên là "priceKey", nó sẽ trả về undefined.
Hệ quả là các phép tính toán học phía sau (undefined * 0.3 và undefined + surcharge) đều trả về NaN (Not a Number), làm hỏng toàn bộ dữ liệu hóa đơn thanh toán.
Cách khắc phục: Cần sử dụng cú pháp dấu ngoặc vuông (Bracket Notation) bookingReservation[priceKey] để JavaScript có thể đọc được giá trị của biến priceKey (tức là chuỗi "roomPrice") và lấy ra đúng số tiền là 1500000.
