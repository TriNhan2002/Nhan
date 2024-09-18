SSL: Secure Sockets Layer.

**SSL là gì ?**
SSL là một giao thức dùng để mã háo thông tin của người. Mục đích chính của SSL là đảm bảo dữ liệu trao đổi giữa hai bên được bảo mật và không thể bị đọc hoặc can thiệp bởi các bên thứ ba.

Có bao nhiêu cách chứng thực SSL ?
Có 4 chứng thực SSL
+ Chứng thực dựa trên chứng chỉ (Certificate-Based Authentication - CA)
+ Chứng thực thông qua tên miền (Domain Validation - DV)
+ Chứng thực tổ chức (Organization Validation - OV)
+ Chứng thực mở rộng (Extended Validation - EV)

**CSR file dùng làm gì trong quá trình tạo SSL**
Là tệp dùng để chứa thông tin mà bạn cần gửi đến một tổ chức chứng nhận (CA) để yêu cầu cấp chứng chỉ SSL/TLS.



**Sử dụng OpenSSL để gen file CSR sau đó request SSL cho domain tech.training.vietnix.tech**

Là sử dụng để xác thực domain tech.training.vietnix.tech có phải là một tên miền an toàn hay không, yêu cầu xác thực CSR (chứng chỉ), nếu xác thực chứng chỉ thành công thì sau đó sẽ request SSL.



**Pem file là gì ?**
(Privacy Enhanced Mail) là một định dạng tệp được sử dụng để lưu trữ và truyền tải các chứng chỉ, khóa riêng tư, và các dữ liệu bảo mật khác trong các hệ thống mã hóa.



**Private key ssl là gì ?**
Private key ssl là file mã hoá được sinh ra cùng lúc khi tạo các đoạn text.



**PFX file là gì ? Cách chuyển từ file crt file sang PFX file.**
(Personal Information Exchange) là một định dạng tệp được sử dụng để lưu trữ chứng chỉ số và khóa riêng.

**Cách chuyển từ file crt file sang PFX file:**

+ Chuẩn bị file CRT: Bạn copy toàn bộ nội dung của file .ca bỏ vào cuối file .crt rồi lưu file .crt lại. Hoặc bạn có thể copy nội dung ở phẩn Certificate (CRT) và Intermediate/Chain files, bỏ vào chung 1 file rồi lưu lại với tên là tenmien.crt.
+ Chuẩn bị file KEY: Các bạn click vào Get Private Key để lấy nội dung key file. Bỏ vào notepad rồi lưu lại với tên là tenmien.key.
+ Lưu ý: Tên file crt và key file phải giống nhau.



**Domain**

**Domain là gì ?**
Domain (tên miền) là địa chỉ độc nhất của một website trên Internet, hoạt động giống như một “ngôi nhà ảo” chứa đựng toàn bộ nội dung và thông tin của trang web. Thay vì phải ghi nhớ dãy số phức tạp của địa chỉ IP, người dùng có thể dễ dàng truy cập website bằng cách nhập tên miền vào trình duyệt.



**Các trạng thái của domain**
Bao gồm các trạng thái:

+ Active (Hoạt động)
+ Pending (Đang chờ)
+ Expired (Hết hạn)
+ Suspended (Bị đình chỉ)
+ Pending Transfer (Đang chờ chuyển nhượng)
+ Redemption Period (Thời gian khôi phục)
+ Pending Delete (Đang chờ xóa)
+ Locked (Đã khóa)
+ ClientHold (Khách hàng bị giữ)
+ ClientTransferProhibited (Chuyển nhượng của khách hàng bị cấm)



**Subdomain là gì?**
Subdomain là phần mở rộng của một tên miền và thường được sử dụng để phân chia hoặc tổ chức nội dung của một trang web hoặc hệ thống thành các khu vực riêng biệt.



**Virtual Hosts là gì?**
Virtual Host là một dạng lưu trữ mà bạn lưu được nhiều domain khác nhau trên cùng một máy chủ sever. Hiện nay Virtual được xem là một giải pháp tiết kiệm chi phí vì nó cho phép bạn nhúng nhiều domain trên một địa chỉ IP trong một Sever. Server sẽ tự động hiểu tên miền nào đang vận hành bên trong vị trí lưu trữ Server tùy theo cách cài đặt của bạn.



**Mail Server**

Mail Server còn được gọi với tên Email Server à một hệ thống máy chủ được cấu hình riêng dựa trên tên miền của doanh nghiệp hay tổ chức để thực hiện quá trình trao và nhận thư điện tử.



**Tìm hiểu MX Record**
MX Record: Bản ghi này bạn có thể sử dụng để trỏ tên miền đến mail server. MX Record chỉ định server nào quản lý các dịch vụ Email của tên miền đó.



**Tìm hiểu DKIM, SPF, PTR**

+ **DKIM** là một phương pháp xác thực email giúp xác nhận rằng email được gửi từ tên miền của tổ chức và không bị thay đổi trong quá trình gửi. Nó sử dụng chữ ký số để xác minh tính toàn vẹn và tính xác thực của email.
+ **SPF** là một phương pháp xác thực email nhằm ngăn chặn việc giả mạo địa chỉ email. Nó cho phép chủ sở hữu tên miền chỉ định các máy chủ email nào được phép gửi email từ tên miền của họ.
+ **PTR (Pointer Record)** là một loại bản ghi DNS dùng để ánh xạ địa chỉ IP đến tên miền. PTR thường được sử dụng trong cấu hình DNS ngược (reverse DNS) để xác nhận rằng địa chỉ IP mà một máy chủ email gửi đến có tên miền tương ứng mà nó công khai.



**DNS**

**DNS là gì ?**

**DNS (Domain Name System)** có nghĩa là hệ thống phân giải tên miền. DNS là hệ thống cho phép thiết lập tương ứng giữa địa chỉ IP và tên miền trên Internet.



**Các loại recored DNS**

+ CNAME Record
+ A Record
+ MX Record
+ AAAA Record
+ TXT Record
+ SRV Record
+ NS Record

**Nguyên tắc làm việc của DNS**

+ Phân tầng và Cấu Trúc Phân Cấp
+ Quá Trình Phân Giải Tên Miền
+ Cơ Chế Bộ Nhớ Cache
+ Bảo Mật và Xác Thực
+ Dự Phòng và Khả Năng Mở Rộng

**Cách phân giải địa chỉ DNS**

+ Khởi Tạo Yêu Cầu DNS
+ Tra Cứu DNS
+ Trả Kết Quả và Caching
+ Kết Nối Đến Máy Chủ Web