---
title: "Worklog Tuần 8"
date: 2026-06-29
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8

* Điều chỉnh kiến trúc ban đầu theo khả năng kỹ thuật, chi phí và giới hạn thực tế của dự án.
* Xác lập các luồng chính cho frontend, backend, xác thực, lưu trữ, xử lý bất đồng bộ và AI.
* Bắt đầu phát triển giao diện và API backend của SmartStudy.

### Quyết định điều chỉnh kiến trúc

Nhóm không thể mua custom domain qua Amazon Route 53 và không thể sử dụng Amazon Bedrock. Vì vậy, SmartStudy sử dụng domain mặc định của AWS Amplify và model chạy bằng Ollama trên máy chủ AI local tự quản lý. AWS Secrets Manager và AWS CloudTrail cũng được loại khỏi phạm vi triển khai. Kiến trúc serverless sau điều chỉnh tập trung vào AWS Amplify, AWS WAF, Amazon Cognito, Amazon API Gateway, AWS Lambda, Amazon S3, Amazon SQS, Amazon DynamoDB và Amazon CloudWatch.

### Các công việc đã thực hiện trong tuần

| STT | Công việc | Ngày bắt đầu | Ngày hoàn thành | Kết quả |
| --- | --------- | ------------ | --------------- | ------- |
| 1 | **Điều chỉnh kiến trúc** <br> - Rà soát diagram cũ và các giới hạn của dự án <br> - Loại Route 53, Bedrock, Secrets Manager và CloudTrail khỏi kiến trúc mục tiêu <br> - Bổ sung SQS, dead-letter queue, WAF, quy trình deploy từ GitHub và Ollama bên ngoài AWS <br> - Xác định hai môi trường staging và production | 29/06/2026 | 01/07/2026 | Kiến trúc đã điều chỉnh |
| 2 | **Thiết kế backend và dữ liệu** <br> - Xác định HTTP API cho xác thực, tài liệu, hội thoại, quiz, bài thi và lượt làm bài <br> - Thiết kế lưu tài liệu trên S3 và xử lý bất đồng bộ qua SQS <br> - Thiết kế các thực thể và access pattern trên DynamoDB <br> - Xác định giao thức tích hợp với Ollama API | 02/07/2026 | 03/07/2026 | Thiết kế API và mô hình dữ liệu |
| 3 | **Phát triển frontend** <br> - Xây dựng trang giới thiệu, luồng xác thực, dashboard, thư viện tài liệu, phòng học, luyện tập và kết quả <br> - Kết nối cấu trúc frontend với các API backend dự kiến <br> - Chuẩn bị repository GitHub và quy trình branch để triển khai qua Amplify | 04/07/2026 | 05/07/2026 | Giao diện SmartStudy ban đầu |

### Kết quả đạt được tuần 8

* Xác lập kiến trúc có thể triển khai phù hợp với các dịch vụ AWS khả dụng và ngân sách dự án.
* Xác định luồng upload tài liệu, xử lý bất đồng bộ, hỏi đáp AI và tạo bài luyện tập.
* Chọn Ollama chạy trên máy chủ AI local tự quản lý để thay thế Amazon Bedrock.
* Hoàn thành các màn hình frontend ban đầu và hợp đồng API cần thiết cho quá trình tích hợp hạ tầng ở tuần 9.
