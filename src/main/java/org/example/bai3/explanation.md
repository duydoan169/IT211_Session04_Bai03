@PathVariable đọc giá trị từ trong URL, ví dụ /movies/M001 thì M001
là một phần của đường dẫn. Nó dùng để định danh một tài nguyên cụ thể,
tức là khi mình biết chính xác muốn lấy cái gì.
@RequestParam đọc giá trị từ query string phía sau dấu ?, ví dụ /movies?genre=Sci-Fi.
Nó dùng để lọc, tìm kiếm hoặc phân trang, tức là khi mình muốn thu hẹp 
một tập dữ liệu theo điều kiện nào đó.
Không thể hoán đổi cho nhau vì bản chất của hai loại tham số này khác nhau hoàn toàn.
Nếu dùng @RequestParam cho ID thì URL trở thành /movies?id=M001, 
điều này sai ngữ nghĩa REST vì M001 là định danh của một tài nguyên
cụ thể chứ không phải điều kiện lọc. Ngược lại nếu nhét genre vào path 
thành /movies/Sci-Fi thì server sẽ hiểu Sci-Fi là ID của một bộ phim, không phải thể loại.
Về chuẩn RESTful, /movies/M001 chuẩn hơn cho việc lấy chi tiết vì nó thể 
hiện rõ đang truy cập vào một tài nguyên xác định. /movies?genre=Sci-Fi 
chuẩn hơn cho việc lọc vì query string sinh ra để phục vụ đúng mục đích đó.