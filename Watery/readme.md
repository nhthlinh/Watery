## Watery

Watery is a app sell drink use Django, Postgresql and ReactJS 

## DESCRIPTION

App bán nước gồm các đối tượng Admin của store, User và Product 
Hệ thống áp dụng đăng nhập bằng mail và có gửi otp về mail khi quên mật khẩu.
Admin, Admin store và User có các thông tin chung bao gồm, các thông tin này có thể được chỉnh sửa:

- Họ và tên
- Ngày tháng năm sinh
- Email 
- Sđt
- Địa chỉ
- Ảnh đại diện, giới tính
- Mật khẩu
  
Admin là bên chủ của app chịu trách nhiệm quản lý app lưu thông tin:

- Thêm sửa xóa Điều khoảng 
- Thêm sửa xóa các store, admin của store và xem doanh thu của store theo tháng (lưu nhiều tháng).
- Thêm sửa và xóa các loại thức uống
- Xem sửa và xóa thức uống của cả hệ thống
- Xem sửa và xóa thông tin tài khoảng user 
- Xem các đơn hàng của hệ thống
- Thêm sửa xóa các khuyến mãi toàn hệ thống 
- Xem và xóa bình luận của khách hàng nếu vi phạm tiêu chuẩn đạo đức
- Các quán có thể đăng ký bán thức uống trên hệ thống bằng việc liên hệ trực tiếp để hệ thống thẩm tra và cấp tài khoảng admin quán sau.
  
Admin của store có thêm thông tin về quán mà admin quản lý (mỗi quán 1 admin):

- Sửa xóa tên quán, mô tả 
- Thêm sửa xóa địa chỉ quán
- Thêm sửa xóa các thức uống mà quán bán
- Thay đổi trạng thái các đơn hàng được khách đặt
- Xem kết quả Doanh thu theo ngày, tháng, năm và xem biểu đồ doanh thu
- Thêm sửa xóa các khuyến mãi áp dụng cho quán
- Thêm sửa xóa các tài khoảng nhân viên quán (tài khoảng gồm mail đăng nhập và mật khẩu do admin quán cấp)
- Thêm sửa xóa các tài khoảng shipper (tài khoảng gồm mail đăng nhập và mật khẩu do admin quán cấp)
- Thêm sửa xóa danh sách topping
- Điều chỉnh giờ mở và đóng cửa (không nhận được đơn sau giờ đóng cửa và trước giờ mở cửa)
- Xem và trả lời bình luận cùa khách hàng với quán, thức uống và topping
- Xem số sao được đánh giá cho quán
  
Nhân viên quán là tài khoảng đặt biệt:

- Chỉ được xem các đơn hàng đến quán (và có quyền thay đổi trạng thái đơn) 
- Nhân viên quán còn gán đơn hàng cho 1 trong các shipper của quán
- Xem doanh thu trong ngày
- Xem danh sách các thức uống và topping của quán đang làm việc và có tùy chọn ẩn khi thức uống hết hàng 
- Các thức uống và topping hết hàng sẽ được mở lại vào thời gian mở cửa hôm sau (bao gồm tất cả các sản phẩm của quán)
  
Shipper là tài khoảng đặt biệt:

- Chỉ được xem đơn hàng đang ship và nhấn hoàn thành đơn thì hệ thống tự động cập nhật trạng thái là hoàn thành.
- Có thêm thông tin về số đơn đã giao trong tháng.
  
User có thêm thông tin:

- Xem các đơn hàng của khách đã đặt (kèm theo trạng thái của đơn)
- Thêm sửa xóa Danh sách các thức uống khách yêu thích
- Thêm sửa xóa Phương thức thanh toán 
- Thêm sửa xóa các thức uống trong giỏ hàng chờ thanh toán 
- Trong mỗi đơn hàng khách đã đặt (kể cả hủy) có nút đặt lại, hệ thống lấy thông tin hiện tại của sản phẩm trong đơn và đưa khách đến trang thanh toán
  
Thức uống là product chính gồm các thông tin được admin của quán chỉnh sửa:  

- Tên 
- Giá tùy theo từng loại size do quán quy định
- Mô tả
- Thuộc quán nào
- Thuộc loại thức uống nào (có thể thuộc nhiều loại)
- Danh sách ảnh  
- Danh sách bình luận của khách hàng 
- Số sao của sản phẩm
  
Topping là sản phẩm đặc biệt chỉ bao gồm:

- Tên
- Giá 
- Mô tả
- Ảnh 
- Số sao
- Bình luận đánh giá
  
Giỏ hàng là nơi chứa các thức uống khách chưa thanh toán có lưu sẵn giá tiền tổng:

- Khi thêm thức uống vào giỏ, khách hàng có thêm lựa chọn topping của quán và thêm ghi chú (ví dụ ít đường, nhiều đá, ...)
- Giỏ hàng lưu thông tin thức uống (gắn với size, topping, ghi chú và số lượng)
- Một giỏ hàng gồm nhiều các thức uống như trên, tổng tiền sẽ tính bằng (tiền thức uống theo size + tiền topping) * số lượng cộng lại hết các sản phẩm có trong giỏ hàng.
Khuyến mãi do admin hoặc admin quán tạo ra:
- Áp dụng khi khách hàng có đơn hàng trên số tiền yêu cầu.
- Với khuyến mãi của admin quán thì tính trên thức uống của quán thôi.
- Lưu thêm cả thời gian bắt đầu và hết hạn
- Lưu số lượng áp dụng cho mã (admin và admin quán quyết định) và số mã đã được sử dụng
Với giỏ hàng có nhiều thức uống topping của nhiều quán khác nhau thì:
- Hệ thống sẽ hiện lựa chọn quán nào cần thanh toán trước khi khách nhấn thanh toán
- Giỏ hàng sẽ tách đơn theo quán.
  
Khi thanh toán:

- Phí giao hàng sẽ do hệ thống tính và bằng số km đến khách * 10k 
- Khách hàng sẽ được áp dụng đúng 1 mã giảm giá tự động sao cho tổng thanh toán thấp nhất nếu thỏa điều kiện 
- Khách hàng chọn địa chỉ giao hàng, phương thức thanh toán 
- Sau đó chọn phương thức thanh toán (bằng COD thanh toán khi nhận hàng hoặc ví momo)
- Đơn hàng sẽ chuyển sang trạng thái đang xử lý và khách hàng xem trạng thái trong danh sách đơn đã đặt
- Đơn hàng chỉ được phép hủy khi nhân viên hoặc admin quán chưa nhấn đang pha chế
- Sau khi hoàn thành đơn hàng thì khách hàng có thể đánh giá từng loại thức uống, topping và quán trong đơn hàng. 
- Nhân viên quán sẽ kiểm tra đơn và nhấn tạm dừng thức uống hoặc topping nào đó trong đơn nếu khi thực hiện đơn phát hiện đã hết hàng. Và hệ thống sẽ báo cáo về khách hàng.
  
Hệ thống còn có tìm kiếm theo tên, top rates, giá (khoảng giá hoặc xếp giá từ cao đến thấp hoặc từ thấp đến cao) (lấy giá của size ly bé nhất), loại thức uống, tên quán, có khuyến mãi hoặc không, đang mở cửa gần khách hàng nhất (xét theo địa chỉ khách và địa chỉ quán trên google drive)

Doanh thu có chia theo loại thức uống và chỉ có chi phí hoa hồng ở dưới tổng doanh thu cho admin quán xem => trừ ra doanh thu thật của quán
Đơn hàng có trạng thái là: 

- đang xử lý: Khách vừa đặt hàng
- đang pha chế: Nhân viên hoặc admin quán nhận và đang tiến hành pha chế
- đang giao đơn: Shipper giao hàng
- đã hoàn thành: Đơn đã đến tay khách
- đang tạm dừng: Sau khi có sản phẩm hết hàng (nhân viên nhấn tạm dừng bất kỳ sản phẩm nào trong đơn), khách hàng sẽ nhận thông báo và nhấn tiếp tục đơn hoặc hủy không đặt nữa. Đơn hàng lúc này đã được điều chỉnh giá và bỏ qua sản phẩm hết hàng. Nếu trước đó khách thanh toán bằng momo thì sẽ được tự động gửi tiền lại.
- đã hủy: Đơn hàng đã hủy (nếu thanh toán trước thì sẽ tự động hoàn tiền)

Hệ thống hiển thị các món đề xuất từ lịch sử đặt hàng và sản phẩm ưa thích của khách khi khách ở trang chủ.