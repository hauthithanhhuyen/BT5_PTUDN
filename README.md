# BT5_PTUDN
BT5_HTTH
# PHẦN 1: LÝ THUYẾT DOCKER
1. Docker là gì?
Docker là một nền tảng mã nguồn mở cho phép các nhà phát triển tự động hóa việc triển khai, mở rộng và quản lý các ứng dụng bên trong các môi trường cô lập được gọi là Container. Thay vì ảo hóa toàn bộ hệ điều hành như máy ảo (Virtual Machine), Docker chia sẻ chung nhân (kernel) của hệ điều hành máy chủ nhưng vẫn đảm bảo các ứng dụng chạy độc lập với đầy đủ thư viện và cấu hình riêng của nó.
# Các keyword trong docker-compose.yml
docker-compose là công cụ dùng để định nghĩa và chạy các ứng dụng Docker nhiều container (multi-container).
<img width="548" height="653" alt="image" src="https://github.com/user-attachments/assets/76511788-498d-4028-82fb-a615363f0e3c" />
<img width="561" height="691" alt="image" src="https://github.com/user-attachments/assets/c26fb034-a05f-493d-84fd-06dbe2233d6c" />
# Ưu điểm khi triển khai app bằng Docker
Docker có các ưu điểm chính:
Dễ triển khai: chỉ cần Docker và file Compose.
Đồng nhất môi trường: chạy giống nhau trên laptop, máy ảo, server.
Dễ quản lý nhiều dịch vụ: web, database, API, Grafana, Node-RED chạy cùng hệ thống.
Dễ backup và khôi phục: có thể lưu image bằng docker save, khôi phục bằng docker load. Docker hỗ trợ lưu image ra file tar và load lại từ file tar hoặc file nén.
Tách biệt ứng dụng: mỗi service chạy trong container riêng, ít ảnh hưởng hệ thống thật
# Triển khai app lên máy chủ thật không có Internet
Bước 1: Build và test app trên laptop cá nhân.
Bước 2: Pull đầy đủ image cần dùng.
Bước 3: Xuất các image ra file .tar.
Bước 4: Copy file .tar + mã nguồn + docker-compose.yml sang server.
Bước 5: Trên server dùng docker load để nạp image.
Bước 6: Chạy docker compose up -d.
Bước 7: Kiểm tra container, port, dữ liệu, website.
# PHẦN B — Thực hành BT5
thực hành áp dụng: APP MONITOR + ALERT DATA REALTIME
sử dụng docker compose có nhiều serivce và các thành phần cần thiết để tạo thành ứng dụng:
<img width="1446" height="897" alt="image" src="https://github.com/user-attachments/assets/98e06334-8b08-4468-ba55-30bff8715561" />
# Node-RED lấy dữ liệu thời tiết thật.
Cấu hình HTTP Request lấy thời tiết
<img width="755" height="869" alt="image" src="https://github.com/user-attachments/assets/32175acb-1f13-43cb-8d8b-f6137ee08d9e" />
# Thêm node function
<img width="890" height="918" alt="image" src="https://github.com/user-attachments/assets/d00106e9-43cf-44fc-bc45-aaccfed7f7f6" />
# Thêm node mysql
<img width="913" height="902" alt="image" src="https://github.com/user-attachments/assets/f319cf38-2b12-46fd-b933-0e292239acd7" />
# Thêm node influxdb out.
<img width="810" height="836" alt="image" src="https://github.com/user-attachments/assets/d506e5ca-77ca-464b-a464-f49fdac061e8" />
# Thêm node switch.
<img width="736" height="879" alt="image" src="https://github.com/user-attachments/assets/527d4198-5dd6-43b9-ab4f-8bc8f4172e0c" />
NODE-RED 
<img width="1181" height="609" alt="image" src="https://github.com/user-attachments/assets/6850e1e2-abaa-4217-9c19-02e1343b5941" />
# Thu thập và Trích xuất dữ liệu Realtime
Sử dụng node http request trong Node-RED để gọi API lấy dữ liệu thực tế (thời tiết/chứng khoán). Hệ thống đã kết nối thành công và nhận về gói dữ liệu thô dưới dạng đối tượng JSON (hiển thị ở tab Debug).
<img width="1657" height="724" alt="image" src="https://github.com/user-attachments/assets/adbdebe6-c932-4734-9461-cb5fdf47cd8d" />
<img width="729" height="755" alt="image" src="https://github.com/user-attachments/assets/1bca561e-d07f-47c4-8202-dd8f5d4354ec" />
# Thu thập dữ liệu thô từ API
Kết quả kiểm thử luồng thu thập dữ liệu thời tiết thời gian thực. Thông qua node http request, hệ thống gọi API và nhận về gói dữ liệu định dạng JSON (như hiển thị ở cửa sổ Debug).
<img width="1918" height="774" alt="image" src="https://github.com/user-attachments/assets/388c882f-c0ed-4638-ad29-2db4d38f0709" />








