---
title: "Worklog Tuần 12"
date: 2026-06-29
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12

* Áp dụng phương án kiến trúc mới không sử dụng Route 53 và Bedrock.
* Chạy môi trường AI local bằng Docker.
* Kết nối Local AI vào luồng RAG của SmartStudy.

### Các công việc đã thực hiện

| STT | Công việc | Ngày bắt đầu | Ngày hoàn thành | Kết quả |
| --- | --------- | ------------ | --------------- | ------- |
| 1 | Cập nhật cấu hình và kiến trúc, sử dụng domain Amplify thay cho Route 53 | 29/06/2026 | 30/06/2026 | Loại Route 53 khỏi hệ thống |
| 2 | Chuẩn bị Docker và chạy model AI trong môi trường local | 01/07/2026 | 02/07/2026 | Local AI hoạt động trên máy chủ local |
| 3 | Kết nối Local AI với quy trình truy xuất tài liệu và hỏi đáp RAG | 03/07/2026 | 05/07/2026 | RAG có thể sử dụng model local thay cho Bedrock |

### Kết quả đạt được tuần 12

* Áp dụng thành công phương án không dùng Route 53 và Bedrock.
* Chạy Local AI bằng Docker và tích hợp vào luồng RAG.
