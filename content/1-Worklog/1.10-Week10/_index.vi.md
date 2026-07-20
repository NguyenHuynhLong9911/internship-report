---
title: "Worklog Tuần 10"
date: 2026-07-13
weight: 1
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10

* Triển khai môi trường production của SmartStudy.
* Hoàn thiện toàn bộ luồng tài liệu, phòng học AI, bài luyện tập và kết quả.
* Bổ sung giám sát, xử lý lỗi tích hợp và chuẩn bị demo cuối cùng.

### Các công việc đã thực hiện trong tuần

| STT | Công việc | Ngày bắt đầu | Ngày hoàn thành | Kết quả |
| --- | --------- | ------------ | --------------- | ------- |
| 1 | **Hạ tầng production** <br> - Triển khai Cognito, API Gateway, Lambda, S3, SQS, dead-letter queue và DynamoDB cho production bằng AWS CDK <br> - Tách biệt tài nguyên staging và production <br> - Kiểm tra IAM permission giữa các dịch vụ | 13/07/2026 | 14/07/2026 | Môi trường AWS production |
| 2 | **Triển khai và bảo vệ frontend** <br> - Kết nối branch `main` trên GitHub với AWS Amplify <br> - Triển khai frontend production trên domain mặc định `amplifyapp.com` <br> - Bật AWS WAF protection cho Amplify Hosting <br> - Kiểm tra đăng ký và đăng nhập bằng Cognito | 14/07/2026 | 15/07/2026 | Ứng dụng web production |
| 3 | **Tích hợp tính năng** <br> - Hoàn thiện upload và xử lý tài liệu bất đồng bộ <br> - Tích hợp phòng học với model Ollama chạy trên máy chủ AI local tự quản lý <br> - Hoàn thiện lịch sử hội thoại, tạo quiz, nộp đáp án, chấm điểm và giải thích kết quả <br> - Kiểm tra xử lý lỗi qua SQS dead-letter queue | 15/07/2026 | 17/07/2026 | Các luồng SmartStudy end-to-end |
| 4 | **Giám sát và kiểm tra cuối** <br> - Rà soát log và metric của Lambda, SQS trên Amazon CloudWatch <br> - Cấu hình alarm cho các điều kiện quan trọng của Lambda và queue <br> - Sửa lỗi tích hợp và giao diện người dùng <br> - Chạy kiểm thử end-to-end cuối cùng và quay video demo project hoàn chỉnh | 18/07/2026 | 19/07/2026 | Hệ thống được giám sát và video demo cuối |

### Kết quả đạt được tuần 10

* Triển khai hai môi trường staging và production riêng biệt tại region `us-east-1`.
* Tự động deploy frontend từ GitHub lên AWS Amplify và công bố SmartStudy bằng domain mặc định của Amplify.
* Hoàn thiện luồng xác thực, quản lý tài liệu, học với AI, tạo quiz, chấm điểm và xem lại kết quả.
* Tích hợp model Ollama chạy trên máy chủ AI local tự quản lý làm dịch vụ AI cho dự án.
* Bổ sung giám sát bằng CloudWatch và hoàn thành demo dự án ngày 19/07/2026.

Môi trường production được duy trì đến hết ngày 30/07/2026 để phục vụ đánh giá và trình diễn; worklog không bao gồm hoạt động cleanup.
