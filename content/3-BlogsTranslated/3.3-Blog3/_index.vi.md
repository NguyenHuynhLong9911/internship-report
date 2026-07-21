---
title: "Xây dựng AI Gateway cho Amazon Bedrock bằng Amazon API Gateway"
date: 2026-07-21
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# Xây dựng AI Gateway cho Amazon Bedrock bằng Amazon API Gateway

Khi nhiều ứng dụng cùng sử dụng mô hình nền tảng, việc gọi trực tiếp Amazon Bedrock có thể làm tăng độ phức tạp trong quản lý quyền truy cập, hạn mức, chi phí và vòng đời API. Bài viết của AWS giới thiệu một **AI Gateway** đặt Amazon API Gateway phía trước Amazon Bedrock để tạo lớp truy cập tập trung và có kiểm soát.

![Kiến trúc AI Gateway cho Amazon Bedrock](/internship-report/images/3-BlogsTranslated/3.3-Blog3/ai-gateway.png)

*Hình 1: Kiến trúc tham khảo sử dụng API Gateway và Lambda để kiểm soát truy cập Amazon Bedrock.*

## Vấn đề cần giải quyết

Trong môi trường doanh nghiệp, một AI Gateway cần hỗ trợ nhiều yêu cầu hơn việc chuyển tiếp request:

- Xác thực và phân quyền người dùng hoặc ứng dụng.
- Giới hạn tốc độ và quota theo tenant hoặc API key.
- Theo dõi, kiểm soát chi phí sử dụng mô hình.
- Quản lý phiên bản API và triển khai canary.
- Truyền phản hồi của mô hình theo thời gian thực.
- Bổ sung các lớp bảo vệ như AWS WAF và lọc nội dung.

Mẫu kiến trúc giúp client tiếp tục sử dụng giao diện tương tự API Bedrock, trong khi các chính sách quản trị được xử lý tại gateway.

## Các thành phần kiến trúc

### Amazon Route 53

Route 53 là thành phần tùy chọn, dùng để ánh xạ custom domain tới endpoint của API Gateway. Nếu không cần domain riêng, client có thể sử dụng endpoint mặc định của API Gateway.

### Amazon API Gateway

API Gateway là điểm truy cập chính. Dịch vụ tiếp nhận request, áp dụng authorization, throttling, usage plan và quản lý các stage. Response streaming cho phép dữ liệu từ mô hình được gửi dần về client thay vì chờ hoàn thành toàn bộ phản hồi.

### Lambda authorizer

Lambda authorizer xác minh request trước khi cho phép truy cập. Giải pháp tham khảo kiểm tra JWT từ hệ thống nhận dạng hiện có, nhưng có thể thay bằng Amazon Cognito hoặc cơ chế authorization khác của API Gateway.

### Lambda integration

Lambda integration đóng vai trò bộ chuyển tiếp động. Hàm nhận header, body và parameter từ request, ký request bằng AWS Signature Version 4 rồi chuyển tiếp tới endpoint Bedrock phù hợp. Cách làm này giúp gateway hỗ trợ thêm API Bedrock mà không phải xây dựng route riêng cho từng tác vụ.

### Amazon Bedrock

Bedrock cung cấp quyền truy cập tới foundation model và các khả năng AI. Client không cần trực tiếp quản lý AWS credential để gọi Bedrock vì việc ký request được thực hiện trong tầng tích hợp.

## Luồng xử lý request

1. Client gửi request tới custom domain hoặc endpoint API Gateway.
2. API Gateway áp dụng các giới hạn và chuyển thông tin xác thực tới Lambda authorizer.
3. Sau khi được chấp nhận, request được chuyển đến Lambda integration.
4. Lambda giữ lại thông tin request, ký bằng SigV4 và gọi API Amazon Bedrock tương ứng.
5. Kết quả được trả về client; với response streaming, dữ liệu có thể được hiển thị khi mô hình đang tạo nội dung.

## Triển khai và mở rộng

Giải pháp tham khảo có thể được triển khai bằng AWS CloudFormation. Bài hướng dẫn bắt đầu với private API Gateway và tạm tắt authorizer để kiểm thử hạ tầng, sau đó mới bổ sung các kiểm soát bảo mật phù hợp.

Một số hướng mở rộng quan trọng gồm:

- Rate limiting và throttling để tránh một tenant sử dụng quá nhiều tài nguyên.
- Private, Regional hoặc edge-optimized endpoint tùy phạm vi truy cập.
- Stage và canary deployment để phát hành phiên bản mới an toàn hơn.
- AWS WAF để hỗ trợ bảo vệ endpoint trước các request không mong muốn.
- Cache prompt hoặc response nhằm giảm độ trễ và chi phí với request lặp lại.
- Lọc dữ liệu nhạy cảm ở Lambda integration, kết hợp Amazon Bedrock Guardrails.

## Điểm cần lưu ý

AI Gateway tạo thêm một tầng vận hành, vì vậy cần giám sát độ trễ, lỗi Lambda, quota API Gateway và chi phí phát sinh. Không nên tắt authorization trong môi trường production. Quyền IAM của Lambda integration cũng nên tuân theo nguyên tắc đặc quyền tối thiểu và chỉ cho phép các hành động Bedrock cần thiết.

## Kết luận

Mẫu AI Gateway cung cấp một điểm truy cập thống nhất cho Amazon Bedrock và tách chính sách quản trị khỏi ứng dụng client. API Gateway đảm nhiệm kiểm soát truy cập và lưu lượng, Lambda xử lý authorization cùng việc ký/chuyển tiếp request, còn Bedrock cung cấp năng lực mô hình. Kiến trúc phù hợp khi tổ chức cần quản lý nhiều ứng dụng hoặc tenant sử dụng AI ở quy mô lớn.

### Nguồn tham khảo

[Building an AI gateway to Amazon Bedrock with Amazon API Gateway](https://aws.amazon.com/vi/blogs/architecture/building-an-ai-gateway-to-amazon-bedrock-with-amazon-api-gateway/) — AWS Architecture Blog, 19/11/2025.
