---
title: "Worklog Tuần 7"
date: 2026-05-25
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7

* Thống nhất ý tưởng chính thức cho dự án nhóm.
* Xác định vấn đề, người dùng và các chức năng cốt lõi của dự án.
* Tìm hiểu những dịch vụ AWS có thể sử dụng cho từng thành phần hệ thống.
* Đánh giá sơ bộ tính khả dụng, quyền truy cập và chi phí của các dịch vụ được cân nhắc.

### Ý tưởng dự án được thống nhất

Nhóm thống nhất phát triển **SmartStudy AI**, nền tảng hỗ trợ học tập từ tài liệu. Hệ thống dự kiến cho phép người dùng tải tài liệu, tương tác với trợ lý AI, tạo quiz và xem kết quả học tập. Đây là định hướng ban đầu và kiến trúc vẫn cần được kiểm chứng trước khi triển khai.

### Các công việc đã thực hiện

| STT | Công việc | Ngày bắt đầu | Ngày hoàn thành | Kết quả |
| --- | --------- | ------------ | --------------- | ------- |
| 1 | **Thống nhất ý tưởng SmartStudy AI** <br> - Tổng hợp các ý tưởng đã đề xuất <br> - Xác định vấn đề học tập cần giải quyết <br> - Thống nhất người dùng mục tiêu và các chức năng cốt lõi <br> - Phác thảo luồng sử dụng ban đầu | 25/05/2026 | 27/05/2026 | Nhóm thống nhất định hướng và phạm vi sơ bộ của dự án |
| 2 | **Tìm hiểu các dịch vụ AWS khả dụng** <br> - Khảo sát dịch vụ cho frontend, xác thực, API và backend <br> - Tìm hiểu lựa chọn cho lưu trữ, xử lý bất đồng bộ, dữ liệu và giám sát <br> - Xem xét các dịch vụ AI có thể hỗ trợ RAG và tạo quiz <br> - Kiểm tra sơ bộ giới hạn tài khoản, quyền sử dụng và chi phí | 28/05/2026 | 30/05/2026 | Có danh sách dịch vụ ứng viên để tiếp tục đánh giá |
| 3 | **Phác thảo giải pháp ban đầu** <br> - Ghép các dịch vụ ứng viên vào từng thành phần <br> - Thảo luận luồng tải tài liệu và xử lý AI <br> - Ghi nhận các rủi ro kỹ thuật và phương án cần kiểm chứng | 30/05/2026 | 31/05/2026 | Hoàn thành kiến trúc sơ bộ, chưa xem là kiến trúc triển khai cuối cùng |

### Kết quả đạt được tuần 7

* Nhóm thống nhất ý tưởng **SmartStudy AI** và các chức năng chính của sản phẩm.
* Xác định được các thành phần frontend, xác thực, backend, storage, dữ liệu, hàng đợi, monitoring và AI cần nghiên cứu.
* Tạo danh sách dịch vụ AWS ứng viên như Amplify, Cognito, API Gateway, Lambda, S3, SQS, DynamoDB và CloudWatch.
* Tìm hiểu Amazon Bedrock như một phương án AI ban đầu nhưng chưa xác nhận khả năng sử dụng.
* Hoàn thành kiến trúc sơ bộ để tiếp tục kiểm chứng và điều chỉnh trong các tuần sau.
