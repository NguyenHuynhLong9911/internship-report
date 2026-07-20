---
title: "Blog đã dịch"
date: 2026-06-08
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

# Blog AWS đã dịch

Phần này trình bày một bài viết kỹ thuật AWS được lựa chọn, biên dịch và tóm tắt trong thời gian thực tập. Bài viết tập trung vào cách xây dựng ứng dụng Python có khả năng mở rộng bằng SQLAlchemy 2.x và Amazon Aurora DSQL.

## [Xây dựng ứng dụng Python với SQLAlchemy và Amazon Aurora DSQL](3.1-Blog1/)

Amazon Aurora DSQL là cơ sở dữ liệu phân tán, serverless, tương thích PostgreSQL, có khả năng tự động mở rộng theo lưu lượng ứng dụng và xác thực bằng AWS IAM. Khi kết hợp với SQLAlchemy, developer vẫn sử dụng được quy trình ORM quen thuộc của Python nhưng cần điều chỉnh một số pattern thiết kế và kết nối cho môi trường phân tán.

Bài viết tập trung vào ba điều chỉnh quan trọng:

- Sử dụng UUID làm primary key để hỗ trợ insert phân tán có khả năng mở rộng.
- Khai báo quan hệ ở tầng ứng dụng bằng `relationship()`, `primaryjoin` và `foreign()` thay cho foreign key constraint.
- Cấu hình SQLAlchemy engine ở chế độ AUTOCOMMIT để tránh thao tác SAVEPOINT không được Aurora DSQL hỗ trợ.

Bài viết cũng đề cập Aurora DSQL Python Connector, xác thực IAM, thao tác CRUD, eager loading, quản lý vòng đời connection và retry với exponential backoff cùng jitter khi xảy ra xung đột optimistic concurrency.

[Đọc bài viết đã dịch →](3.1-Blog1/)
