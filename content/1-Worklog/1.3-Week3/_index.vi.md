---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3

* Tiếp tục tìm hiểu các dịch vụ mạng trong AWS sau phần VPC và Session Manager.
* Hiểu cách VPC Peering kết nối riêng tư giữa hai VPC.
* Nắm được vai trò của route table, Network ACL và DNS trong kết nối giữa các VPC peering.
* Tìm hiểu Transit Gateway như một hub mở rộng để kết nối nhiều VPC và nhiều hệ thống mạng.

### Các công việc cần triển khai trong tuần này

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 1 | **000019 - Thiết lập VPC Peering** <br> - Các bước chuẩn bị <br> - Cập nhật Network ACL <br> - Tạo kết nối Peering <br> - Cấu hình Route tables <br> - Kích hoạt Cross-Peer DNS | 25/05/2026 | 28/05/2026 | <https://github.com/AWS-First-Cloud-Journey/FCJ-2023> |
| 2 | **000020 - Thiết lập Transit Gateway** <br> - Thiết lập hạ tầng <br> - Tạo Transit Gateway <br> - Transit Gateway Attachments <br> - Tạo Route Table cho TGW <br> - Thêm Gateway vào Route Tables và kiểm tra kết quả | 29/05/2026 | 31/05/2026 | <https://github.com/AWS-First-Cloud-Journey/FCJ-2023> |

### Kết quả đạt được tuần 3

* Hiểu mục đích của VPC Peering và trường hợp nên sử dụng để kết nối hai VPC.
* Thực hành các bước chính khi thiết lập VPC Peering, bao gồm cập nhật route table, cấu hình Network ACL và kích hoạt Cross-Peer DNS.
* Nắm được giới hạn của VPC Peering và lý do cần mô hình kết nối tập trung hơn khi hệ thống mạng mở rộng.
* Tìm hiểu Transit Gateway như một dịch vụ mạng theo mô hình hub-and-spoke để kết nối nhiều VPC và hệ thống on-premises.
* Thực hành tạo Transit Gateway attachments và route tables.
* Hiểu rõ hơn cách định tuyến trong AWS ảnh hưởng đến kết nối riêng tư giữa các workload.
