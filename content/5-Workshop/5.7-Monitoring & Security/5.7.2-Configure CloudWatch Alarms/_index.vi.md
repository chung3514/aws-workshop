---
title: "5.7.2 Cấu hình CloudWatch Alarms"
date: 2024-01-01
weight: 2
chapter: false
---

# 5.7.2 Cấu hình CloudWatch Alarms

## Tổng quan

Amazon CloudWatch Alarms giúp theo dõi các chỉ số (Metrics) của dịch vụ AWS và tự động phát hiện các trạng thái bất thường.

Khi một chỉ số vượt quá ngưỡng đã cấu hình, Alarm sẽ chuyển sang trạng thái **ALARM**. Trong chương tiếp theo, chúng ta sẽ cấu hình Amazon SNS để gửi thông báo khi Alarm được kích hoạt.

Trong workshop này, bạn sẽ tạo các CloudWatch Alarm để giám sát:

- AWS Lambda
- Amazon API Gateway
- Amazon RDS
- Amazon SQS
- Amazon Athena

---

## Kiến trúc

```text
AWS Services
      │
      ├── Lambda
      ├── API Gateway
      ├── Amazon RDS
      ├── Amazon SQS
      └── Amazon Athena
               │
               ▼
      Amazon CloudWatch
               │
          CloudWatch Alarm
               │
        Alarm State Change
               │
               ▼
      Amazon SNS (Next Section)
```

---

## Mục tiêu

Sau khi hoàn thành bài này, bạn sẽ:

- Tạo CloudWatch Alarm.
- Thiết lập ngưỡng cảnh báo.
- Theo dõi trạng thái Alarm.
- Chuẩn bị tích hợp với Amazon SNS.

---

# Bước 1. Mở CloudWatch Alarms

Đăng nhập AWS Management Console.

Mở:

```text
Amazon CloudWatch
```

Chọn:

```text
Alarms
```

Nhấn:

```text
Create alarm
```

---

# Bước 2. Tạo Alarm cho Lambda Errors

Chọn Metric:

```text
AWS/Lambda

Errors
```

Chọn Lambda:

```text
backend-api
```

Thiết lập:

| Thuộc tính | Giá trị |
|------------|----------|
| Statistic | Sum |
| Period | 5 Minutes |
| Threshold | Greater than 0 |

Đặt tên:

```text
BackendLambdaErrors
```

Ý nghĩa:

Nếu Lambda phát sinh bất kỳ lỗi nào trong khoảng 5 phút, Alarm sẽ chuyển sang trạng thái **ALARM**.

---

# Bước 3. Tạo Alarm cho Lambda Duration

Metric:

```text
Duration
```

Thiết lập:

| Thuộc tính | Giá trị |
|------------|----------|
| Statistic | Average |
| Threshold | 5000 ms |

Tên Alarm:

```text
BackendLambdaDuration
```

Mục tiêu là phát hiện các lần thực thi Lambda có thời gian xử lý quá lâu.

---

# Bước 4. Tạo Alarm cho API Gateway

Chọn Metric:

```text
AWS/ApiGateway

5XXError
```

Thiết lập:

| Thuộc tính | Giá trị |
|------------|----------|
| Statistic | Sum |
| Threshold | Greater than 0 |

Tên:

```text
ApiGateway5XXErrors
```

Alarm này giúp phát hiện lỗi phía máy chủ (Server Errors).

---

# Bước 5. Tạo Alarm cho Amazon RDS

Chọn Metric:

```text
CPUUtilization
```

Thiết lập:

| Thuộc tính | Giá trị |
|------------|----------|
| Statistic | Average |
| Threshold | 80% |

Tên:

```text
RDSPHighCPU
```

Nếu CPU duy trì trên 80%, cần kiểm tra truy vấn hoặc nâng cấp tài nguyên.

---

# Bước 6. Tạo Alarm cho Amazon SQS

Metric:

```text
ApproximateNumberOfMessagesVisible
```

Thiết lập:

| Thuộc tính | Giá trị |
|------------|----------|
| Statistic | Average |
| Threshold | Greater than 100 |

Tên:

```text
SQSQueueDepth
```

Nếu số lượng tin nhắn trong hàng đợi tăng liên tục, AI Worker có thể đang xử lý chậm.

---

# Bước 7. Tạo Alarm cho Amazon Athena

Chọn Metric:

```text
FailedQueries
```

Thiết lập:

| Thuộc tính | Giá trị |
|------------|----------|
| Statistic | Sum |
| Threshold | Greater than 0 |

Tên:

```text
AthenaFailedQueries
```

Alarm này giúp phát hiện các truy vấn phân tích thất bại.

---

# Bước 8. Xem trạng thái Alarm

Sau khi tạo, chuyển đến:

```text
CloudWatch

Alarms
```

Ví dụ:

| Alarm | State |
|-------|-------|
| BackendLambdaErrors | OK |
| BackendLambdaDuration | OK |
| ApiGateway5XXErrors | OK |
| RDSPHighCPU | OK |
| SQSQueueDepth | OK |
| AthenaFailedQueries | OK |

Khi chỉ số vượt ngưỡng, trạng thái sẽ chuyển sang:

```text
ALARM
```

---

# Bước 9. Kiểm tra lịch sử Alarm

Chọn một Alarm và xem:

```text
History
```

Bạn có thể xem:

- Thời điểm tạo Alarm.
- Thời điểm thay đổi trạng thái.
- Giá trị Metric tại thời điểm kích hoạt.

---

## Best Practices

- Đặt tên Alarm rõ ràng và nhất quán.
- Chọn ngưỡng phù hợp với đặc điểm của ứng dụng.
- Theo dõi Alarm History để phân tích sự cố.
- Chỉ tạo Alarm cho các Metrics quan trọng.
- Kết hợp Alarm với Amazon SNS để gửi thông báo tự động.

---

## Kiểm tra kết quả

Đảm bảo:

- Alarm được tạo thành công.
- Tất cả Alarm ở trạng thái **OK**.
- Có thể xem Metric và History của từng Alarm.
- Hệ thống sẵn sàng tích hợp với Amazon SNS.

---

## Kết quả

Sau khi hoàn thành bài này, bạn đã:

- Tạo CloudWatch Alarms cho các dịch vụ chính.
- Thiết lập ngưỡng cảnh báo phù hợp.
- Theo dõi trạng thái và lịch sử Alarm.
- Chuẩn bị hệ thống cho bước gửi cảnh báo tự động bằng Amazon SNS.