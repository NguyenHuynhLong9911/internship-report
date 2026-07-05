---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8

* Bắt đầu triển khai dự án SmartStudy AI.
* Phân chia công việc thành các phần AWS architecture, backend và frontend.
* Hoàn thiện kiến trúc AWS chính cho workflow GenAI và RAG.
* Xây dựng nền tảng backend và frontend ban đầu cho nền tảng web.

### Mô tả dự án

SmartStudy AI là nền tảng trợ lý học tập thông minh trên AWS. Hệ thống cho phép sinh viên tải lên tài liệu học tập, đặt câu hỏi với chatbot AI, tạo đề thi tự động và nhận phản hồi về kết quả học tập.

### Các công việc cần triển khai trong tuần này

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 1 | **Hoàn thiện AWS architecture** <br> - Chỉnh sửa architecture diagram <br> - Xác định luồng upload tài liệu và luồng RAG <br> - Map các AWS services với từng thành phần <br> - Rà soát bảo mật, khả năng mở rộng và chi phí | 29/06/2026 | 01/07/2026 | AWS architecture design |
| 2 | **Triển khai backend** <br> - Thiết kế API endpoints cho upload tài liệu, chatbot, tạo đề thi và đánh giá kết quả <br> - Chuẩn bị luồng xử lý dữ liệu cho tài liệu được upload <br> - Xác định các điểm tích hợp với AI/RAG services | 02/07/2026 | 03/07/2026 | Backend tasks |
| 3 | **Triển khai frontend** <br> - Xây dựng các màn hình ban đầu cho upload, chat, quiz và xem kết quả <br> - Kết nối thiết kế frontend với backend API <br> - Rà soát trải nghiệm người dùng và chuẩn bị integration testing | 04/07/2026 | 05/07/2026 | Frontend tasks |

### Kết quả đạt được tuần 8

* Phân chia dự án SmartStudy AI thành các luồng công việc AWS architecture, backend và frontend.
* Hoàn thiện kiến trúc AWS rõ ràng hơn cho nền tảng.
* Xác định luồng API backend chính cho upload, chatbot, tạo đề thi và đánh giá kết quả.
* Xây dựng cấu trúc frontend ban đầu cho các workflow chính của người dùng.
* Chuẩn bị dự án cho bước tích hợp giữa web interface, backend services và AI/RAG components.
