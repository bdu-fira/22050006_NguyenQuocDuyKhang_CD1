# Web Bán Đồ Điện Tử - Chuyên Đề 1

# Giới thiệu đề tài
Đề tài "Web Bán Đồ Điện Tử" xây dựng một hệ thống thương mại điện tử chuyên bán các sản phẩm điện tử như điện thoại, laptop, tai nghe, phụ kiện, v.v. Hệ thống sử dụng kiến trúc microservices, triển khai trên nền tảng cloud AWS (EC2 và RDS) với Docker và Docker Compose để đảm bảo tính mô-đun và khả năng mở rộng. Các dịch vụ chính bao gồm API Gateway (Nginx), Auth Service, Product Service, Order Service, Payment Service, Cart Service, cùng với cơ sở dữ liệu MySQL, Redis và RabbitMQ hỗ trợ giao tiếp bất đồng bộ. Tài liệu báo cáo gồm 81 trang, trình bày chi tiết từ phân tích, thiết kế, triển khai đến kết quả và hướng phát triển.
Thông tin chung

# Trường: Đại học Bình Dương, Khoa Công nghệ Thông tin, Robot và Trí tuệ Nhân tạo  

# Đề tài: Xây dựng website bán đồ điện tử (điện thoại, laptop, tai nghe, phụ kiện, v.v.)  

## 👥 Nhóm thực hiện:
- Nguyễn Quốc Duy Khang - 22050006
- Nghiêm Trung Hiếu - 22050017
- Lê Đức Tài - 22050090

## Giảng viên hướng dẫn:  
- ThS. Nguyễn Thanh Sơn  
- ThS. Hồ Ngọc Giàu  
- ThS. Dương Anh Tuấn  
- ThS. Nguyễn Hữu Quyền  

## Mục tiêu
- Xây dựng website thương mại điện tử bán đồ điện tử với đầy đủ chức năng: duyệt sản phẩm, giỏ hàng, đặt hàng, thanh toán.  
- Có phần quản trị để quản lý sản phẩm, đơn hàng, tài khoản người dùng.

## Nội dung chính

- Phân tích hệ thống: Mô hình tổng quát, phân tích Usecase (Đăng ký, Đăng nhập, Quản lý giỏ hàng, Đặt hàng, Quản lý sản phẩm, v.v.).  
- Thiết kế hệ thống: Sequence Diagram, Database Diagram, thiết kế giao diện (Đăng nhập, Đăng ký, Quản lý Admin/Nhân viên/Người dùng).  
- Triển khai trên Cloud: Sử dụng AWS (EC2, RDS), Docker, Docker Compose để triển khai website.  
- Kết quả đạt được: Website hoạt động với các chức năng cơ bản, giao diện thân thiện, triển khai thành công trên cloud.  
- Hạn chế: Chưa hỗ trợ thanh toán trực tuyến, tìm kiếm nâng cao, bảo mật cơ bản.  
- Hướng phát triển: Thêm thanh toán trực tuyến (Momo, VNPAY), tìm kiếm nâng cao, đánh giá sản phẩm, cải thiện bảo mật.

## Microservices Project
Đây là một dự án microservices được xây dựng bằng Django, MySQL, Redis, RabbitMQ và tích hợp Stripe cho thanh toán.

## Dự án bao gồm các thành phần chính:
Cấu trúc dự án
- API Gateway: Nginx, định tuyến các yêu cầu đến các service tương ứng.
- Auth Service: Xử lý xác thực người dùng, đăng ký, đăng nhập và quản lý ví điện tử.
- Product Service: Quản lý sản phẩm, danh mục sản phẩm và các thông tin liên quan.
- Order Service: Quản lý đơn hàng, trạng thái đơn hàng và lịch sử giao dịch.
- Payment Service: Tích hợp Stripe cho thanh toán trực tuyến.
- Cart Service: Quản lý giỏ hàng của người dùng.
- RabbitMQ: Sử dụng cho giao tiếp bất đồng bộ giữa các service cụ thể như Order Service, Payment Service và Product Service.
- MySQL: Cơ sở dữ liệu chính cho các service.
- Redis: Sử dụng cho cache và lưu trữ tạm thời.
- Django: Framework chính để xây dựng các service.
- ReactJS: Sử dụng cho giao diện người dùng (frontend).

- Frontend: Giao diện người dùng tại http://localhost:8080.
- Ngoài ra, dự án có module seed_data để khởi tạo dữ liệu ban đầu.

## 🗃️ Cấu trúc cơ sở dữ liệu
- auth_db: `TaiKhoan`, `NguoiDung`
- product_db: `ChiTietThongSo`, `DanhMuc`, `HangSanXuat`, `SanPham`, `ThongSo`
- order_db: , `ChiTietDonHang`, `DonHang`, `TrangThai`
- payment_db: `ThanhToan`, `UserBalance`

## ☁️ Mô hình triển khai Cloud

- **Frontend** chạy trên EC2 public subnet.
- **Backend (Auth, Product, Order, Payment, Cart)** chạy riêng biệt trên các container Docker.
- **Database (MySQL)** trên Amazon RDS (private subnet).
- **Redis** và **RabbitMQ** hỗ trợ cache và giao tiếp bất đồng bộ.
- Tất cả chạy trong **VPC riêng biệt** qua Internet Gateway và API Gateway.
- Bảo mật: Sử dụng **Security Group, JWT, mã hóa mật khẩu**.



