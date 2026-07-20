---
title: "Worklog Tuần 9"
date: 2026-07-06
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9

* Khởi tạo hạ tầng serverless của SmartStudy bằng AWS CDK và CloudFormation.
* Triển khai và kiểm tra môi trường staging.
* Tích hợp xác thực, API, lưu trữ, xử lý tài liệu bất đồng bộ và frontend ứng dụng.

### Các công việc đã thực hiện trong tuần

| STT | Công việc | Ngày bắt đầu | Ngày hoàn thành | Kết quả |
| --- | --------- | ------------ | --------------- | ------- |
| 1 | **Infrastructure as Code và xác thực** <br> - Bootstrap AWS CDK tại region `us-east-1` <br> - Khai báo tài nguyên staging và IAM role <br> - Tạo Amazon Cognito User Pool và app client <br> - Bổ sung Pre Sign-up Lambda trigger | 06/07/2026 | 07/07/2026 | Hạ tầng nền tảng và xác thực staging |
| 2 | **Backend và tầng dữ liệu** <br> - Tạo HTTP API trên API Gateway và API Lambda <br> - Tạo S3 bucket lưu tài liệu <br> - Khởi tạo các DynamoDB table cho AI job, lượt làm bài, hội thoại, tin nhắn, document chunk, tài liệu, bài thi, quiz và bản tóm tắt <br> - Kết nối các thao tác API với tầng dữ liệu | 08/07/2026 | 09/07/2026 | API và cơ sở dữ liệu staging |
| 3 | **Xử lý tài liệu bất đồng bộ** <br> - Tạo SQS document-processing queue và dead-letter queue <br> - Xây dựng Document Ingestion Lambda <br> - Kết nối S3, SQS, Lambda và DynamoDB <br> - Kiểm tra quá trình lưu metadata và các chunk của tài liệu | 10/07/2026 | 11/07/2026 | Pipeline xử lý tài liệu |
| 4 | **Triển khai và tích hợp staging** <br> - Kết nối repository GitHub với AWS Amplify <br> - Triển khai branch staging <br> - Cấu hình giá trị môi trường frontend cho Cognito và API Gateway <br> - Kiểm thử tích hợp ban đầu với Ollama endpoint trên máy chủ AI local | 11/07/2026 | 12/07/2026 | Môi trường staging đã triển khai |

### Kết quả đạt được tuần 9

* Khởi tạo hạ tầng staging bằng các định nghĩa AWS CDK có thể tái sử dụng.
* Tích hợp Cognito, API Gateway, Lambda, S3, SQS, DynamoDB và Amplify.
* Hoàn thành luồng xử lý tài liệu bất đồng bộ và cơ chế xử lý lỗi qua dead-letter queue.
* Triển khai frontend staging từ GitHub và chuẩn bị hệ thống cho môi trường production.
