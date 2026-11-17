# USER STORY — WEBSITE BÁN HÀNG VINMARK

| Thông tin | Nội dung |
| --- | --- |
| Môn học / Lớp | IS207 — Phát triển ứng dụng Web / IS207.Q12 |
| Học kỳ / Năm học | 1 / 2025–2026 |
| Phiên bản | 1.1 — Hoàn thiện đặc tả User Story |
| Phạm vi | Khách vãng lai, khách hàng, nhân viên và quản trị viên |
| Tài liệu liên quan | [BRD](BRD.md), [SRS](SRS.md), [Thông tin nhóm](../README.md) |

## 1. Mục đích và quy ước

Tài liệu gồm 24 User Story bao phủ các yêu cầu FR-01–FR-32 trong SRS. Mỗi story có mục đích sử dụng, tiền điều kiện, luồng chính và tiêu chí chấp nhận theo Given–When–Then (điều kiện — hành động — kết quả). US-01–US-11 giữ mã liên hệ với BRD; các story sau bổ sung nhu cầu và tách chi tiết các thao tác.

Đây là yêu cầu mục tiêu, chưa phải kết quả kiểm thử. Các phần cần hoàn thiện trong code được ghi tại từng FR và bảng GAP của SRS. Phí giao hàng, tỷ giá, chính sách hủy/hoàn tiền, vòng đời đơn và phạm vi thông báo tuân theo các quyết định cần chốt trong BRD. Không tự coi các chức năng đề xuất là đã triển khai.

**Ưu tiên:** P0 là cốt lõi; P1 là mở rộng/cần tích hợp. Nếu một story liên quan cả hai mức, nghiệm thu riêng từng FR theo SRS. Không gán ước lượng công sức hay người thực hiện khi nhóm chưa thống nhất.

## 2. Danh mục và truy vết

| Mã | User Story | FR liên quan | Kiểm thử SRS |
| --- | --- | --- | --- |
| [US-01](#us-01) | Đăng ký và kích hoạt | FR-01–FR-02 | AT-01 |
| [US-02](#us-02) | Tra cứu sản phẩm | FR-07–FR-09 | AT-04 |
| [US-03](#us-03) | Giỏ hàng và hợp nhất | FR-10–FR-11 | AT-05 |
| [US-04](#us-04) | Đặt hàng COD | FR-06, FR-13–FR-14 | AT-06–AT-08 |
| [US-05](#us-05) | Thanh toán trực tuyến | FR-15–FR-16 | AT-09–AT-10 |
| [US-06](#us-06) | Theo dõi và hủy đơn | FR-17–FR-18 | AT-06, AT-11 |
| [US-07](#us-07) | Đánh giá sau mua | FR-19 | AT-12 |
| [US-08](#us-08) | Cập nhật sản phẩm và hỗ trợ | FR-20, FR-23, FR-25 | AT-06, AT-13, AT-15 |
| [US-09](#us-09) | Xử lý đơn tại cửa hàng | FR-26–FR-28 | AT-11, AT-17 |
| [US-10](#us-10) | Xem thống kê | FR-30 | AT-18 |
| [US-11](#us-11) | Khôi phục mật khẩu | FR-04 | AT-01–AT-02 |
| [US-12](#us-12) | Quản lý hồ sơ | FR-05 | AT-03 |
| [US-13](#us-13) | Quản lý địa chỉ | FR-06 | AT-03, AT-06 |
| [US-14](#us-14) | Lưu sản phẩm yêu thích | FR-12 | AT-05 |
| [US-15](#us-15) | Liên hệ cửa hàng | FR-20 | AT-13 |
| [US-16](#us-16) | Hỏi chatbot | FR-21 | AT-14 |
| [US-17](#us-17) | Quản lý danh mục | FR-24 | AT-15 |
| [US-18](#us-18) | Quản lý người dùng | FR-22–FR-23, FR-29 | AT-16 |
| [US-19](#us-19) | Quản lý hồ sơ vận hành | FR-31 | AT-03 |
| [US-20](#us-20) | Nhận thông báo công việc | FR-32 | AT-19 |
| [US-21](#us-21) | Đăng nhập và đăng xuất khách hàng | FR-03 | AT-02 |
| [US-22](#us-22) | Đăng nhập và kiểm soát quyền quản trị | FR-22–FR-23 | AT-02, AT-06 |
| [US-23](#us-23) | Quản lý thông tin sản phẩm | FR-25 | AT-15 |
| [US-24](#us-24) | Gửi thông tin đơn hàng qua email | FR-28 | AT-17 |

## 3. Đặc tả User Story

<a id="us-01"></a>

### US-01 — Đăng ký và kích hoạt

> Là **khách mới**, tôi muốn **đăng ký và kích hoạt bằng email** để **có tài khoản mua hàng**.

**Truy vết:** FR-01–FR-02; AT-01.

**Tiền điều kiện:** Khách chưa đăng nhập; email chưa được đăng ký; có cấu hình mail thử nghiệm.

**Luồng chính:**

1. Mở đăng ký và nhập họ tên, email, mật khẩu.
2. Hệ thống kiểm tra, tạo tài khoản chờ và gửi link.
3. Khách mở link hợp lệ để kích hoạt.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-01-01 | Thông tin đăng ký hợp lệ | Khách gửi form | Tạo một khách hàng pending, lưu mật khẩu băm và gửi hướng dẫn kích hoạt. |
| AC-01-02 | Email trùng/sai hoặc mật khẩu dưới 6 ký tự | Khách đăng ký | Báo lỗi trường tương ứng; không tạo tài khoản. |
| AC-01-03 | Token kích hoạt hợp lệ và chưa dùng | Khách mở link | Tài khoản chuyển active và token bị vô hiệu hóa. |
| AC-01-04 | Token không tồn tại hoặc đã dùng | Khách mở lại link | Không kích hoạt thêm tài khoản và có thông báo phù hợp. |

<a id="us-02"></a>

### US-02 — Tra cứu sản phẩm

> Là **khách mua hàng**, tôi muốn **tìm kiếm, lọc và xem chi tiết sản phẩm** để **chọn được sản phẩm phù hợp**.

**Truy vết:** FR-07–FR-09; AT-04.

**Tiền điều kiện:** Có dữ liệu sản phẩm và danh mục để tra cứu.

**Luồng chính:**

1. Mở danh sách hoặc nhập từ khóa.
2. Chọn danh mục, khoảng giá và cách sắp xếp.
3. Chuyển trang hoặc mở chi tiết sản phẩm.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-02-01 | Có sản phẩm khớp tên hoặc mô tả | Khách tìm bằng từ khóa không rỗng | Kết quả đúng từ khóa; tìm kiếm phân trang 12 sản phẩm/trang. |
| AC-02-02 | Có danh mục và khoảng giá hợp lệ | Khách lọc/sắp xếp rồi chuyển trang | Kết quả đúng điều kiện, giữ bộ lọc; danh sách lọc phân trang 9 sản phẩm/trang. |
| AC-02-03 | Có slug sản phẩm tồn tại | Khách xem chi tiết | Hiển thị tên, giá, ảnh, tồn, đánh giá trung bình và sản phẩm liên quan. |
| AC-02-04 | Không có kết quả hoặc slug không tồn tại | Khách tra cứu | Có trạng thái rỗng hoặc 404 phù hợp, không hiển thị dữ liệu giả. |

<a id="us-03"></a>

### US-03 — Giỏ hàng và hợp nhất

> Là **khách vãng lai**, tôi muốn **giữ các sản phẩm đã chọn khi đăng nhập** để **không phải chọn hàng lại**.

**Truy vết:** FR-10–FR-11; AT-05.

**Tiền điều kiện:** Có sản phẩm còn bán; khách có giỏ session hoặc giỏ tài khoản.

**Luồng chính:**

1. Thêm sản phẩm và chọn lượng.
2. Cập nhật hoặc xóa dòng giỏ.
3. Đăng nhập khách hàng để hợp nhất giỏ.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-03-01 | Sản phẩm còn đủ tồn | Khách thêm lại sản phẩm đã chọn | Cộng số lượng đúng vào cùng dòng giỏ và cập nhật tổng. |
| AC-03-02 | Số lượng không nguyên dương hoặc vượt tồn | Khách thêm/sửa giỏ | Từ chối trước khi ghi, giữ dữ liệu hợp lệ trước đó. |
| AC-03-03 | Giỏ tạm và giỏ tài khoản có cùng sản phẩm | Khách đăng nhập | Hợp nhất theo sản phẩm, kiểm tra tổng lượng với tồn và thông báo nếu cần điều chỉnh. |
| AC-03-04 | Hợp nhất gặp lỗi hoặc đang đăng nhập guard quản trị | Sự kiện đăng nhập xảy ra | Không xóa mất giỏ tạm hoặc chuyển giỏ khách vào tài khoản vận hành. |

<a id="us-04"></a>

### US-04 — Đặt hàng COD

> Là **khách hàng**, tôi muốn **đặt hàng với địa chỉ của mình và xem tổng tiền** để **mua hàng và trả tiền khi nhận**.

**Truy vết:** FR-06, FR-13–FR-14; AT-06–AT-08.

**Tiền điều kiện:** Khách đăng nhập, giỏ có hàng hợp lệ và có địa chỉ mặc định thuộc mình.

**Luồng chính:**

1. Mở checkout, kiểm tra địa chỉ và tiền.
2. Chọn COD rồi xác nhận.
3. Máy chủ chốt đơn và hiển thị kết quả.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-04-01 | Giỏ có 100.000đ tiền hàng và chính sách phí 25.000đ đã được chốt | Khách xác nhận COD | Tổng hiển thị và tổng lưu cùng bằng 125.000đ, tiền được tính tại máy chủ. |
| AC-04-02 | Giỏ và địa chỉ hợp lệ, đủ tồn | Khách đặt hàng | Tạo đơn pending, dòng hàng có giá lúc đặt, payment cash/pending; trừ tồn và xóa giỏ sau khi chốt. |
| AC-04-03 | Giỏ rỗng, địa chỉ người khác hoặc hàng thiếu tồn | Khách gửi yêu cầu | Từ chối, không tạo đơn hoặc làm thay đổi tồn. |
| AC-04-04 | Gặp lỗi giữa chừng hoặc gửi lặp/đồng thời | Hệ thống xử lý đặt hàng | Rollback khi lỗi; không tạo đơn trùng từ cùng yêu cầu hoặc làm tồn âm. |

<a id="us-05"></a>

### US-05 — Thanh toán trực tuyến

> Là **khách hàng**, tôi muốn **thanh toán qua PayPal hoặc MoMo** để **thanh toán thuận tiện**.

**Truy vết:** FR-15–FR-16; AT-09–AT-10.

**Tiền điều kiện:** Khách có yêu cầu mua hợp lệ; PayPal/MoMo được cấu hình môi trường thử.

**Luồng chính:**

1. Chọn phương thức online và nhận tổng từ máy chủ.
2. Thanh toán tại dịch vụ.
3. Máy chủ xác minh kết quả và trả trạng thái đơn.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-05-01 | Giao dịch có mã tham chiếu gắn đúng yêu cầu mua | Dịch vụ xác nhận hợp lệ | Máy chủ đối chiếu giao dịch, số tiền và người nhận trước khi ghi completed. |
| AC-05-02 | Trình duyệt báo thành công nhưng chưa có xác minh | Khách gửi kết quả | Không coi dữ liệu trình duyệt là bằng chứng đã thanh toán. |
| AC-05-03 | Chữ ký/mã tham chiếu/số tiền sai hoặc dịch vụ lỗi | Hệ thống nhận kết quả | Không ghi thành công; thông báo phù hợp và giữ dấu vết để xử lý. |
| AC-05-04 | Callback hợp lệ đã được xử lý | Dịch vụ gửi lại | Không tạo thêm đơn hoặc trừ tồn lặp; kết quả nhất quán. |

<a id="us-06"></a>

### US-06 — Theo dõi và hủy đơn

> Là **khách hàng**, tôi muốn **xem và hủy đơn còn chờ của mình** để **theo dõi mua hàng và điều chỉnh nhu cầu**.

**Truy vết:** FR-17–FR-18; AT-06, AT-11.

**Tiền điều kiện:** Khách đã đăng nhập và có đơn thuộc tài khoản.

**Luồng chính:**

1. Mở lịch sử và xem chi tiết.
2. Chọn hủy đơn đang chờ.
3. Hệ thống kiểm tra và thông báo kết quả.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-06-01 | Khách có nhiều đơn | Khách mở lịch sử | Chỉ hiển thị đơn của mình, mới nhất trước; chi tiết có hàng, tiền, địa chỉ và trạng thái. |
| AC-06-02 | ID thuộc khách khác | Khách gọi thẳng URL hoặc yêu cầu hủy | Không trả dữ liệu hoặc thay đổi đơn đó. |
| AC-06-03 | Đơn của khách còn pending | Khách hủy hợp lệ | Đổi cancelled, ghi lịch sử và hoàn tồn đúng lượng trong cùng giao dịch. |
| AC-06-04 | Đơn đã hủy/không đủ điều kiện hoặc có hai yêu cầu hủy | Hệ thống xử lý | Không hoàn kho lần hai; đơn đã trả online không tự được coi là đã hoàn tiền. |

<a id="us-07"></a>

### US-07 — Đánh giá sau mua

> Là **khách đã nhận hàng**, tôi muốn **đánh giá sản phẩm đã mua** để **chia sẻ trải nghiệm với người mua khác**.

**Truy vết:** FR-19; AT-12.

**Tiền điều kiện:** Khách đăng nhập và có đơn completed chứa sản phẩm; chưa đánh giá sản phẩm đó.

**Luồng chính:**

1. Mở chi tiết sản phẩm.
2. Nhập điểm và bình luận.
3. Gửi và xem kết quả đánh giá.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-07-01 | Có bằng chứng mua hoàn tất và chưa đánh giá | Khách gửi điểm 1–5, bình luận tối đa 1.000 ký tự | Lưu một đánh giá đúng khách/sản phẩm và cập nhật điểm trung bình. |
| AC-07-02 | Chưa mua hoặc đơn chưa hoàn tất | Khách POST trực tiếp | Máy chủ từ chối dù khách bỏ qua form giao diện. |
| AC-07-03 | Khách đã đánh giá sản phẩm | Khách gửi lại/đồng thời | Không tạo thêm đánh giá trùng. |
| AC-07-04 | Điểm ngoài 1–5 hoặc bình luận quá dài | Khách gửi | Báo lỗi và không lưu dữ liệu sai. |

<a id="us-08"></a>

### US-08 — Cập nhật sản phẩm và hỗ trợ

> Là **nhân viên**, tôi muốn **quản lý sản phẩm và trả lời liên hệ** để **vận hành công việc được giao**.

**Truy vết:** FR-20, FR-23, FR-25; AT-06, AT-13, AT-15.

**Tiền điều kiện:** Staff đăng nhập khu vực quản trị; có manage_products và manage_contacts theo seed.

**Luồng chính:**

1. Mở chức năng được phân quyền.
2. Cập nhật sản phẩm hoặc phản hồi liên hệ.
3. Nhận kết quả thao tác.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-08-01 | Staff có hai permission được cấp | Staff mở sản phẩm/liên hệ | Cho phép các thao tác đúng quyền. |
| AC-08-02 | Staff không có quyền đơn/danh mục/người dùng | Staff gọi thẳng endpoint các nhóm này | Máy chủ từ chối 403, không chỉ ẩn menu. |
| AC-08-03 | Liên hệ tồn tại và nội dung phản hồi hợp lệ | Staff gửi phản hồi | Gửi đúng email lưu trong liên hệ; chỉ đánh dấu đã trả lời khi gửi thành công. |
| AC-08-04 | Có lỗi dữ liệu sản phẩm hoặc gửi email | Staff xác nhận thao tác | Thông báo đúng lỗi và không báo thành công giả. |

<a id="us-09"></a>

### US-09 — Xử lý đơn tại cửa hàng

> Là **quản trị viên**, tôi muốn **xác nhận và theo dõi quá trình xử lý đơn** để **không bỏ sót yêu cầu mua hàng**.

**Truy vết:** FR-26–FR-28; AT-11, AT-17.

**Tiền điều kiện:** Admin có manage_orders và đơn tồn tại.

**Luồng chính:**

1. Mở danh sách và chi tiết.
2. Chọn thao tác hợp lệ theo trạng thái.
3. Kiểm tra trạng thái và lịch sử sau xử lý.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-09-01 | Đơn pending | Admin xác nhận | Chuyển processing và ghi nhận thay đổi. |
| AC-09-02 | Đã chốt quy trình giao/hoàn tất và có quyền | Admin chuyển processing sang shipped rồi completed | Chuyển đúng thứ tự, ghi thời điểm, ghi chú và người thực hiện. |
| AC-09-03 | Đơn đã hủy/hoàn tất | Admin xác nhận lại hoặc chuyển trái quy tắc | Từ chối, không đổi tồn hoặc trạng thái. |
| AC-09-04 | Đơn đủ điều kiện hủy hoặc xác nhận thu COD có bằng chứng | Admin thực hiện thao tác tương ứng | Hủy hoàn kho một lần; thu COD đổi payment riêng, không suy ra đã thu chỉ từ trạng thái đơn. |

<a id="us-10"></a>

### US-10 — Xem thống kê

> Là **quản trị viên**, tôi muốn **xem thống kê hoạt động bán hàng** để **nắm tình hình cửa hàng**.

**Truy vết:** FR-30; AT-18.

**Tiền điều kiện:** Admin hoặc staff được truy cập dashboard; có dữ liệu đối chứng nhiều kỳ.

**Luồng chính:**

1. Mở dashboard.
2. Xem chỉ số và biểu đồ theo kỳ quy định.
3. Đối chiếu số liệu đơn và sản phẩm.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-10-01 | Có đơn ở nhiều trạng thái | Người vận hành xem doanh thu | Chỉ tính đơn completed theo định nghĩa SRS; không tính đơn hủy. |
| AC-10-02 | Có dữ liệu nhiều năm | Xem biểu đồ của một năm | Không gộp số tiền của tháng cùng số ở các năm khác. |
| AC-10-03 | Một số tháng không có đơn hoàn tất | Xem biểu đồ tháng | Tháng đó bằng 0 và có đủ các tháng trong kỳ. |
| AC-10-04 | Có sản phẩm trong đơn chưa hoàn tất/hủy | Xem lượng bán | Lượng bán theo định nghĩa mục tiêu chỉ tính dòng đơn hoàn tất. |

<a id="us-11"></a>

### US-11 — Khôi phục mật khẩu

> Là **khách hàng quên mật khẩu**, tôi muốn **nhận đường dẫn đặt lại qua email đã đăng ký** để **lấy lại quyền truy cập và tiếp tục mua hàng**.

**Truy vết:** FR-04; AT-01–AT-02.

**Tiền điều kiện:** Khách chưa đăng nhập, có email đăng ký và truy cập được hộp thư; cấu hình mail thử nghiệm hợp lệ.

**Luồng chính:**

1. Mở “Quên mật khẩu” và gửi email đã đăng ký.
2. Hệ thống kiểm tra, tạo token và gửi đường dẫn.
3. Khách mở link, nhập email, mật khẩu mới và xác nhận.
4. Máy chủ kiểm tra, lưu mật khẩu băm và vô hiệu hóa token.
5. Khách quay về đăng nhập bằng mật khẩu mới.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-11-01 | Khách chưa đăng nhập, có email đăng ký hợp lệ và dịch vụ mail thử nghiệm hoạt động. | Khách gửi yêu cầu đặt lại mật khẩu. | Hệ thống gửi đường dẫn đặt lại tới đúng email, thông báo đã gửi và chưa thay đổi mật khẩu hiện tại. |
| AC-11-02 | Khách đang ở form quên mật khẩu. | Khách bỏ trống email, nhập sai định dạng hoặc nhập email chưa tồn tại. | Hệ thống báo lỗi phù hợp; không thay đổi mật khẩu và không gửi đường dẫn đặt lại cho địa chỉ không hợp lệ. |
| AC-11-03 | Một đường dẫn đặt lại đã được tạo cho email trong vòng 60 giây trước đó. | Khách yêu cầu gửi lại ngay. | Hệ thống từ chối gửi quá sớm theo giới hạn cấu hình, thông báo cần thử lại; không đổi mật khẩu. |
| AC-11-04 | Token đúng email, chưa dùng và chưa quá hạn 60 phút. | Khách nhập mật khẩu mới từ 6 ký tự trở lên, xác nhận khớp và gửi form. | Hệ thống cập nhật mật khẩu băm, vô hiệu hóa token và chuyển tới trang đăng nhập với thông báo thành công. |
| AC-11-05 | Khách có đường dẫn đặt lại hợp lệ. | Khách nhập mật khẩu dưới 6 ký tự hoặc xác nhận không khớp. | Hệ thống chỉ rõ lỗi; mật khẩu hiện tại không bị thay đổi. |
| AC-11-06 | Token không tồn tại, không khớp email, đã dùng hoặc đã quá hạn. | Khách gửi yêu cầu đặt lại mật khẩu. | Hệ thống từ chối cập nhật và thông báo không thể đặt lại bằng đường dẫn này; khách có thể yêu cầu đường dẫn mới. |
| AC-11-07 | Tài khoản khách đang hoạt động và vừa đặt lại mật khẩu thành công. | Khách lần lượt thử đăng nhập bằng mật khẩu cũ và mật khẩu mới. | Mật khẩu cũ bị từ chối; mật khẩu mới đăng nhập thành công. |
| AC-11-08 | Tài khoản đang `pending`, `banned` hoặc `deleted`. | Khách đặt lại mật khẩu bằng token hợp lệ rồi thử đăng nhập. | Thao tác đặt lại không đổi trạng thái tài khoản sang `active`; khách vẫn không đăng nhập được khi chưa đủ điều kiện. |

Thời hạn 60 phút và khoảng cách gửi lại 60 giây lấy từ cấu hình hiện tại, cần cập nhật tiêu chí nếu thay đổi cấu hình. Lỗi gửi mail không được thông báo đã giao thư thành công; driver log không chứng minh thư đến hộp thư.

<a id="us-12"></a>

### US-12 — Quản lý hồ sơ

> Là **khách hàng**, tôi muốn **sửa thông tin và đổi mật khẩu** để **giữ thông tin tài khoản chính xác**.

**Truy vết:** FR-05; AT-03.

**Tiền điều kiện:** Khách đăng nhập bằng tài khoản của mình.

**Luồng chính:**

1. Mở hồ sơ.
2. Sửa thông tin/ảnh hoặc nhập mật khẩu cũ và mới.
3. Lưu và kiểm tra thông tin.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-12-01 | Thông tin hợp lệ | Khách lưu hồ sơ | Chỉ cập nhật người dùng của phiên hiện tại. |
| AC-12-02 | Ảnh đúng định dạng, tối đa 2 MB | Khách tải ảnh | Ảnh được lưu và hiển thị đúng URL. |
| AC-12-03 | Mật khẩu cũ đúng, mới tối thiểu 6 ký tự và xác nhận khớp | Khách đổi mật khẩu | Lưu mật khẩu băm mới và báo thành công. |
| AC-12-04 | Mật khẩu cũ sai, xác nhận lệch hoặc ảnh không hợp lệ | Khách lưu | Báo lỗi phù hợp và không ghi dữ liệu sai. |

<a id="us-13"></a>

### US-13 — Quản lý địa chỉ

> Là **khách hàng**, tôi muốn **lưu nhiều địa chỉ và chọn mặc định** để **thuận tiện khi đặt hàng**.

**Truy vết:** FR-06; AT-03, AT-06.

**Tiền điều kiện:** Khách đã đăng nhập; dữ liệu địa chỉ tách theo tài khoản.

**Luồng chính:**

1. Mở danh sách địa chỉ.
2. Thêm hoặc chọn địa chỉ mặc định.
3. Xóa địa chỉ được phép xóa.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-13-01 | Tên 3–100 ký tự, điện thoại 10 chữ số, địa chỉ 5–255 ký tự, thành phố 2–100 ký tự | Khách thêm địa chỉ | Lưu đúng chủ sở hữu. |
| AC-13-02 | Khách có nhiều địa chỉ | Chọn một mặc định | Chỉ tối đa một mặc định của khách đó. |
| AC-13-03 | Địa chỉ không thuộc khách | Khách yêu cầu xóa/đặt mặc định | Từ chối và không tác động tài khoản khác. |
| AC-13-04 | Địa chỉ đã được dùng trong đơn | Khách yêu cầu xóa | Bảo toàn dữ liệu giao dịch hoặc chặn xóa theo chính sách SRS. |

<a id="us-14"></a>

### US-14 — Lưu sản phẩm yêu thích

> Là **khách hàng**, tôi muốn **thêm và bỏ sản phẩm yêu thích** để **tìm lại sản phẩm quan tâm**.

**Truy vết:** FR-12; AT-05.

**Tiền điều kiện:** Khách đăng nhập và sản phẩm tồn tại.

**Luồng chính:**

1. Thêm yêu thích tại sản phẩm.
2. Mở danh sách yêu thích.
3. Bỏ sản phẩm không còn quan tâm.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-14-01 | Sản phẩm chưa trong yêu thích | Khách thêm | Có một bản ghi gắn đúng khách và sản phẩm. |
| AC-14-02 | Sản phẩm đã được yêu thích | Khách thêm lại | Không tạo dòng trùng. |
| AC-14-03 | Có dữ liệu nhiều khách | Khách xem/xóa | Chỉ xem/xóa dữ liệu của mình. |
| AC-14-04 | Sản phẩm không tồn tại hoặc chưa đăng nhập | Gửi yêu cầu thêm | Từ chối phù hợp, không tạo dữ liệu không hợp lệ. |

<a id="us-15"></a>

### US-15 — Liên hệ cửa hàng

> Là **khách truy cập**, tôi muốn **gửi câu hỏi qua form liên hệ** để **được cửa hàng hỗ trợ**.

**Truy vết:** FR-20; AT-13.

**Tiền điều kiện:** Khách truy cập được trang liên hệ.

**Luồng chính:**

1. Nhập tên, email, điện thoại và nội dung.
2. Gửi form.
3. Nhận thông báo đã ghi nhận yêu cầu.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-15-01 | Tên/email hợp lệ tối đa 255 ký tự, điện thoại 10–15 chữ số, nội dung không rỗng | Khách gửi | Lưu liên hệ chưa trả lời và báo tiếp nhận. |
| AC-15-02 | Thiếu nội dung hoặc email/điện thoại sai | Khách gửi | Báo lỗi và không lưu liên hệ sai. |
| AC-15-03 | Có liên hệ mới | Người có manage_contacts mở danh sách | Hiển thị yêu cầu mới theo thứ tự mới nhất trước. |
| AC-15-04 | Có lỗi lưu dữ liệu | Khách gửi | Không thông báo đã ghi nhận thành công. |

<a id="us-16"></a>

### US-16 — Hỏi chatbot

> Là **khách truy cập**, tôi muốn **hỏi chatbot về sản phẩm** để **nhận tư vấn nhanh bằng tiếng Việt**.

**Truy vết:** FR-21; AT-14.

**Tiền điều kiện:** Khách vãng lai hoặc khách đăng nhập mở được khung chat.

**Luồng chính:**

1. Gửi câu hỏi về sản phẩm.
2. Hệ thống lưu tin và lấy ngữ cảnh.
3. Hiển thị câu trả lời hoặc thông báo lỗi dịch vụ.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-16-01 | Tin nhắn không rỗng và tối đa 2.000 ký tự | Khách gửi | Lưu đúng chủ thể, phản hồi tiếng Việt khi dịch vụ hoạt động. |
| AC-16-02 | Có nhiều tài khoản/phiên khách | Khách xem lịch sử | Không hiển thị lịch sử thuộc người khác. |
| AC-16-03 | Khách vãng lai có lịch sử và đăng nhập khách thành công | Hợp nhất chat | Chuyển lịch sử đúng chủ thể, không gắn nhầm vào guard quản trị. |
| AC-16-04 | Thiếu API key, timeout hoặc dịch vụ lỗi | Khách gửi | Thông báo phù hợp; giỏ/đặt hàng vẫn sử dụng được và bot không tự thực hiện giao dịch. |

<a id="us-17"></a>

### US-17 — Quản lý danh mục

> Là **quản trị viên**, tôi muốn **thêm, sửa và ngừng sử dụng danh mục** để **tổ chức hàng hóa dễ tìm**.

**Truy vết:** FR-24; AT-15.

**Tiền điều kiện:** Admin đăng nhập và có manage_categories.

**Luồng chính:**

1. Mở danh mục.
2. Nhập/sửa tên, mô tả, ảnh.
3. Lưu hoặc yêu cầu xóa theo chính sách dữ liệu.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-17-01 | Tên/slug chưa trùng, ảnh hợp lệ tối đa 2 MB | Admin thêm/sửa | Lưu và hiển thị đúng danh mục. |
| AC-17-02 | Tên/slug trùng hoặc ảnh sai | Admin lưu | Báo lỗi rõ, không lưu dở dữ liệu. |
| AC-17-03 | Người dùng không có permission | Gọi endpoint danh mục | Bị từ chối và không đổi dữ liệu. |
| AC-17-04 | Danh mục liên quan dữ liệu đã giao dịch | Admin yêu cầu xóa | Chặn hoặc xử lý theo chính sách bảo toàn lịch sử, không cascade làm mất đơn. |

<a id="us-18"></a>

### US-18 — Quản lý người dùng

> Là **quản trị viên**, tôi muốn **quản lý trạng thái và nâng khách thành nhân viên** để **phân công và kiểm soát truy cập**.

**Truy vết:** FR-22–FR-23, FR-29; AT-16.

**Tiền điều kiện:** Admin có manage_users; tài khoản đích tồn tại.

**Luồng chính:**

1. Mở danh sách người dùng.
2. Chọn cập nhật trạng thái hoặc nâng khách thành staff.
3. Kiểm tra vai trò/trạng thái sau lưu.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-18-01 | Có nhiều tài khoản | Admin xem danh sách | Hiển thị vai trò và phân trang 9 người/trang. |
| AC-18-02 | Tài khoản đích là khách hàng đủ điều kiện | Admin nâng thành staff | Chỉ chuyển đúng vai trò cho phép, không tự cấp quyền admin. |
| AC-18-03 | Trạng thái ngoài tập hợp hợp lệ hoặc vai trò đích không phù hợp | Admin gửi request | Từ chối, không lưu chuyển đổi sai. |
| AC-18-04 | Thao tác làm mất admin cuối cùng hoặc người gọi thiếu quyền | Gửi request | Từ chối theo chính sách bảo vệ tài khoản quản trị trong SRS. |

<a id="us-19"></a>

### US-19 — Quản lý hồ sơ vận hành

> Là **nhân viên hoặc quản trị viên**, tôi muốn **cập nhật hồ sơ và mật khẩu riêng** để **bảo quản tài khoản làm việc**.

**Truy vết:** FR-31; AT-03.

**Tiền điều kiện:** Staff/admin đăng nhập guard quản trị.

**Luồng chính:**

1. Mở hồ sơ vận hành.
2. Sửa thông tin, ảnh hoặc mật khẩu.
3. Lưu và kiểm tra kết quả.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-19-01 | Tên/email/địa chỉ hợp lệ và email chưa trùng | Lưu hồ sơ | Cập nhật đúng tài khoản của phiên admin. |
| AC-19-02 | Mật khẩu cũ đúng, mới đủ dài và xác nhận khớp | Đổi mật khẩu | Lưu băm mật khẩu mới. |
| AC-19-03 | Ảnh hợp lệ tối đa 2 MB | Tải avatar | Lưu và hiển thị đúng ảnh. |
| AC-19-04 | Email trùng, mật khẩu cũ sai hoặc ảnh không hợp lệ | Lưu | Báo lỗi và không thay đổi dữ liệu tương ứng. |

<a id="us-20"></a>

### US-20 — Nhận thông báo công việc

> Là **nhân viên hoặc quản trị viên**, tôi muốn **xem và đánh dấu thông báo đã đọc** để **theo dõi việc cần xử lý**.

**Truy vết:** FR-32; AT-19.

**Tiền điều kiện:** Người vận hành đăng nhập; đã chốt thông báo cá nhân hay hộp thư chung.

**Luồng chính:**

1. Mở thông báo chưa đọc.
2. Xem thông báo có liên kết công việc.
3. Đánh dấu đã đọc.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-20-01 | Có sự kiện đơn/liên hệ mới trong phạm vi thông báo đã chốt | Hệ thống xử lý sự kiện | Tạo thông báo đúng người nhận/phạm vi. |
| AC-20-02 | Có thông báo chưa đọc | Người có quyền mở danh sách | Chỉ trả đúng phạm vi được phép. |
| AC-20-03 | Thông báo thuộc phạm vi quyền | Đánh dấu đọc | Cập nhật trạng thái đã đọc đúng bản ghi. |
| AC-20-04 | Thông báo ngoài phạm vi cá nhân hoặc ID không hợp lệ | Gọi endpoint đọc | Không sửa dữ liệu của người khác và phản hồi phù hợp. |

<a id="us-21"></a>

### US-21 — Đăng nhập và đăng xuất khách hàng

> Là **khách hàng**, tôi muốn **đăng nhập và đăng xuất tài khoản** để **sử dụng thông tin mua hàng của mình và kết thúc phiên khi cần**.

**Truy vết:** FR-03; AT-02.

**Tiền điều kiện:** Khách có tài khoản; đang ở trang đăng nhập.

**Luồng chính:**

1. Nhập email và mật khẩu.
2. Hệ thống xác thực trạng thái/vai trò.
3. Khách sử dụng tài khoản rồi đăng xuất.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-21-01 | Email/mật khẩu đúng, role customer và status active | Khách đăng nhập | Tạo lại session và cho truy cập khu vực khách hàng. |
| AC-21-02 | Tài khoản pending/banned/deleted, sai vai trò hoặc sai mật khẩu | Khách đăng nhập | Từ chối, không cấp phiên khách hợp lệ. |
| AC-21-03 | Khách đang đăng nhập | Khách đăng xuất | Hủy session và thay token CSRF. |
| AC-21-04 | Đã đăng xuất | Dùng phiên cũ gọi chức năng yêu cầu đăng nhập | Bị yêu cầu đăng nhập lại, không trả dữ liệu riêng tư. |

<a id="us-22"></a>

### US-22 — Đăng nhập và kiểm soát quyền quản trị

> Là **nhân viên hoặc quản trị viên**, tôi muốn **đăng nhập vào khu vực làm việc theo quyền được cấp** để **thực hiện đúng nhiệm vụ của mình**.

**Truy vết:** FR-22–FR-23; AT-02, AT-06.

**Tiền điều kiện:** Có tài khoản admin hoặc staff.

**Luồng chính:**

1. Mở đăng nhập quản trị.
2. Nhập thông tin.
3. Truy cập chức năng theo permission rồi đăng xuất.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-22-01 | Thông tin đúng, role admin/staff và status active | Đăng nhập quản trị | Tạo phiên guard admin hợp lệ. |
| AC-22-02 | Tài khoản bị khóa, khách hàng hoặc sai mật khẩu | Đăng nhập | Bị từ chối. |
| AC-22-03 | Đã đăng nhập nhưng thiếu permission | Gọi thẳng endpoint nghiệp vụ | Nhận 403 và không làm đổi dữ liệu. |
| AC-22-04 | Chưa đăng nhập hoặc đã đăng xuất | Truy cập endpoint bảo vệ | Chuyển tới đăng nhập, không sử dụng được phiên đã hủy. |

<a id="us-23"></a>

### US-23 — Quản lý thông tin sản phẩm

> Là **người có quyền quản lý sản phẩm**, tôi muốn **thêm, sửa và ngừng bán sản phẩm** để **cung cấp thông tin hàng hóa chính xác cho khách**.

**Truy vết:** FR-25; AT-15.

**Tiền điều kiện:** Admin/staff có manage_products; danh mục hợp lệ tồn tại.

**Luồng chính:**

1. Mở form thêm/sửa sản phẩm.
2. Nhập thông tin và ảnh.
3. Lưu hoặc ngừng bán theo chính sách dữ liệu.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-23-01 | Giá không âm, tồn nguyên không âm, danh mục đúng và slug duy nhất | Lưu sản phẩm | Lưu tên, giá, lượng, đơn vị, trạng thái và mô tả đúng. |
| AC-23-02 | Ảnh hợp lệ không quá 2 MB mỗi ảnh | Thêm hoặc thay ảnh | Lưu ảnh đúng đường dẫn và hiển thị được sau cập nhật. |
| AC-23-03 | Giá/tồn sai, slug trùng hoặc danh mục không tồn tại | Lưu | Báo lỗi, không lưu sản phẩm/ảnh dở dang. |
| AC-23-04 | Sản phẩm có lịch sử mua | Yêu cầu xóa/ngừng bán | Bảo toàn dòng đơn và giá lịch sử; thống nhất trạng thái bán trên các màn hình. |

<a id="us-24"></a>

### US-24 — Gửi thông tin đơn hàng qua email

> Là **người có quyền quản lý đơn hàng**, tôi muốn **gửi email thông tin đơn cho đúng khách** để **khách kiểm tra và lưu thông tin mua hàng**.

**Truy vết:** FR-28; AT-17.

**Tiền điều kiện:** Người gọi có manage_orders; đơn có khách, email và địa chỉ hợp lệ.

**Luồng chính:**

1. Mở chi tiết đơn.
2. Chọn gửi thông tin đơn.
3. Hệ thống lấy người nhận từ đơn và báo kết quả gửi.

**Tiêu chí chấp nhận:**

| Mã | Given — Điều kiện | When — Hành động | Then — Kết quả cần đạt |
| --- | --- | --- | --- |
| AC-24-01 | Đơn và dữ liệu khách hợp lệ, dịch vụ mail hoạt động | Người có quyền gửi | Gửi đúng email khách của đơn, nội dung đúng dòng hàng/tiền/địa chỉ. |
| AC-24-02 | Thiếu đơn/email/địa chỉ | Gửi yêu cầu | Báo lỗi, không báo đã gửi thành công. |
| AC-24-03 | Dịch vụ mail lỗi | Hệ thống gửi | Báo thất bại và cho xử lý lại, không đổi trạng thái thanh toán. |
| AC-24-04 | Người gọi không có manage_orders | Gọi endpoint gửi | Bị từ chối; email thông tin đơn không được coi là hóa đơn điện tử kế toán. |

## 4. Ưu tiên và phụ thuộc

- Tài khoản và xác thực (US-01, US-11, US-21–US-22) là điều kiện của các thao tác cần đăng nhập; US-11 cần dịch vụ mail để kiểm tra gửi/nhận thực tế.
- Danh mục/sản phẩm (US-17, US-23), địa chỉ (US-13), giỏ (US-03) là dữ liệu đầu vào của đặt hàng COD (US-04).
- Thanh toán online (US-05) cần cấu hình thử, xác minh máy chủ và chống xử lý lặp; không nghiệm thu chỉ bằng việc xuất hiện nút PayPal/MoMo.
- Theo dõi/xử lý đơn (US-06, US-09), đánh giá (US-07), thống kê (US-10) và email thông tin đơn (US-24) phụ thuộc trạng thái/dữ liệu đơn nhất quán.
- Chatbot (US-16) và thông báo (US-20) kế thừa ưu tiên P1; chính sách người nhận thông báo phải được chốt trước kiểm thử.
- US-08 là nhu cầu tổng quát của nhân viên; thao tác sản phẩm được mô tả sâu hơn ở US-23. US-09 bao quát xử lý đơn; gửi email được tách chi tiết ở US-24. Không tính những phần trùng này thành chức năng độc lập khi ước lượng.

## 5. Điều kiện hoàn tất

1. Các tiêu chí chấp nhận trong phạm vi đã chốt có kịch bản thử và bằng chứng kết quả; các tiêu chí chưa đạt được ghi rõ.
2. Kiểm tra luồng hợp lệ, dữ liệu sai và quyền truy cập, gồm gọi endpoint trực tiếp.
3. Các thao tác ảnh hưởng tiền/tồn kho có kiểm thử lỗi giữa chừng, gửi lặp và xử lý đồng thời trên DB thử riêng.
4. Kiểm thử tích hợp email/thanh toán/AI có cấu hình và môi trường thử phù hợp; không đưa khóa, token thật hoặc mật khẩu vào bằng chứng công khai.
5. Kết quả được đối chiếu các AT/NFR và GAP trong SRS. Bản đặc tả này không tự xác nhận code đã đạt các tiêu chí.
6. Khi thay đổi chính sách hoặc phạm vi, cập nhật đồng bộ BRD, SRS và User Story, giữ nguyên mã để truy vết.
