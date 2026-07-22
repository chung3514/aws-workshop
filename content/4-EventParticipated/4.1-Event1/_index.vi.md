---
title: "AWS First Cloud AI Journey – Community Day"
date: 2026-05-23
weight: 2
chapter: false
pre: " <b> 4.1. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Nội dung dưới đây chỉ mang tính chất tham khảo. Vui lòng **không sao chép nguyên văn** vào báo cáo của bạn, bao gồm cả phần cảnh báo này.
{{% /notice %}}

# Báo cáo thu hoạch: "AWS First Cloud AI Journey – Community Day"

### Mục đích của sự kiện

- Chia sẻ những xu hướng mới nhất về Cloud Computing và Generative AI trên nền tảng AWS.
- Giới thiệu các kiến trúc hiện đại trong phát triển ứng dụng AI và điện toán đám mây.
- Hướng dẫn xây dựng hệ thống AI sử dụng Amazon Bedrock, Serverless và các dịch vụ AWS.
- Tìm hiểu về Large Language Models (LLMs), AI Agent và Multi-Agent Systems thông qua các ví dụ thực tế.
- Tạo cơ hội giao lưu, học hỏi và kết nối cộng đồng yêu thích AWS, Cloud và AI.

### Danh sách diễn giả

- **Vy Lam** – Senior Business Systems Analyst, VPBank
- **Thảo Nguyễn** – GenAI Engineer, VIB
- **Mai Nguyễn** – GenAI Engineer, VIB
- **Uyên Lê** – GenAI Engineer, VIB
- **Anh Phạm** – Cloud Consultant, GoAsiaPacific Vietnam
- **Thịnh Nguyễn** – DevOps Engineer, FCAJ
- **Tịnh Trương** – Platform Engineer, GoTymeX
- **Đức Đào** – Solutions Architect, Cloud Kinetics

### Nội dung nổi bật

#### Context Is Everything – Making AI Actually Work for You

Các diễn giả nhấn mạnh rằng **Context** là yếu tố quan trọng quyết định chất lượng phản hồi của các mô hình Generative AI.

Những nội dung nổi bật gồm:

- Vì sao AI thường đưa ra câu trả lời chưa chính xác khi thiếu ngữ cảnh.
- Khái niệm **Second AI Brain** và cách AI lưu trữ, sử dụng thông tin.
- Kết hợp **Prompt Engineering** với Context để nâng cao chất lượng phản hồi.
- Xây dựng hệ thống AI có khả năng ghi nhớ và xử lý thông tin theo ngữ cảnh thực tế.

#### Cloud Architecture với Amazon Bedrock

Workshop giới thiệu kiến trúc AI hiện đại trên nền tảng AWS sử dụng:

- Amazon CloudFront
- Amazon S3
- API Gateway
- AWS Lambda
- Amazon Bedrock
- DynamoDB
- AWS SAM
- React Application

Quy trình hoạt động:

- Người dùng gửi yêu cầu thông qua CloudFront.
- API Gateway tiếp nhận request.
- AWS Lambda xử lý nghiệp vụ.
- Amazon Bedrock thực hiện suy luận AI.
- Dữ liệu được lưu trên Amazon S3 và DynamoDB.
- Kết quả trả về giao diện người dùng.

Lợi ích của kiến trúc:

- Hoàn toàn Serverless.
- Tự động mở rộng.
- Giảm chi phí vận hành.
- Không cần quản lý máy chủ.
- Triển khai AI nhanh chóng và linh hoạt.

#### Nghiên cứu về Large Language Models (LLMs)

Workshop giới thiệu bài nghiên cứu:

**"Non-Determinism of Deterministic LLM Settings"**

Qua đó giúp người tham dự hiểu:

- Vì sao cùng một Prompt nhưng AI vẫn có thể sinh ra nhiều kết quả khác nhau.
- Những yếu tố ảnh hưởng đến tính ổn định của mô hình ngôn ngữ lớn.
- Cách hiểu rõ hơn về hành vi của LLM để xây dựng hệ thống AI đáng tin cậy.

#### Vai trò của Temperature, Top-P và Top-K

Workshop giải thích chi tiết các tham số quan trọng trong mô hình AI.

- **Temperature** điều chỉnh mức độ sáng tạo của AI.
- **Top-P** giới hạn tập từ theo xác suất tích lũy.
- **Top-K** giới hạn số lượng từ được lựa chọn ở mỗi bước sinh văn bản.

Việc hiểu rõ các tham số này giúp tối ưu chất lượng phản hồi của AI trong nhiều bài toán khác nhau.

#### Single-Agent và Multi-Agent Architecture

Một trong những nội dung ấn tượng nhất là phần so sánh giữa Single-Agent và Multi-Agent.

Hạn chế của Single-Agent:

- Context bị giới hạn.
- Single Point of Failure.
- Khó mở rộng.
- Khả năng suy luận còn hạn chế.

Mô hình **Virtual Credit Committee** sử dụng nhiều AI Agent chuyên trách:

- Manager
- Financial Analyst
- Market Analyst
- Team Evaluator
- Risk Assessor
- Compliance

Sự phối hợp giữa nhiều Agent giúp:

- Tăng độ chính xác.
- Giảm sai sót.
- Tăng khả năng reasoning.
- Dễ mở rộng hệ thống.
- Mô phỏng quá trình ra quyết định trong doanh nghiệp.

### Những gì học được

#### Kiến thức về Cloud

- Hiểu cách các dịch vụ AWS phối hợp để xây dựng ứng dụng AI hiện đại.
- Nắm được kiến trúc Serverless và lợi ích của việc không phải quản lý hạ tầng.
- Hiểu rõ hơn về quy trình triển khai ứng dụng AI trên nền tảng AWS.

#### Kiến thức về AI

- Context đóng vai trò rất quan trọng trong Generative AI.
- Prompt Engineering sẽ hiệu quả hơn khi kết hợp với Context.
- Hiểu rõ hơn về cách hoạt động của Large Language Models.

#### Kiến thức về kiến trúc hiện đại

- Amazon Bedrock giúp triển khai Generative AI nhanh chóng.
- Multi-Agent Architecture mang lại hiệu quả cao hơn Single-Agent.
- Serverless giúp hệ thống linh hoạt, dễ mở rộng và tiết kiệm chi phí.

### Ứng dụng vào công việc

Những kiến thức thu được có thể áp dụng vào nhiều dự án thực tế như:

- Xây dựng chatbot AI bằng Amazon Bedrock.
- Thiết kế Serverless Architecture với AWS Lambda và API Gateway.
- Xây dựng hệ thống AI có khả năng ghi nhớ Context.
- Áp dụng Multi-Agent Architecture cho các bài toán doanh nghiệp.
- Tối ưu Prompt Engineering.
- Triển khai ứng dụng AI trên nền tảng AWS Cloud.

### Trải nghiệm tham gia sự kiện

Tham gia **AWS First Cloud AI Journey – Community Day** là một trải nghiệm rất bổ ích, giúp tôi hiểu rõ hơn về Cloud Computing và Generative AI trên nền tảng AWS.

#### Học hỏi từ các chuyên gia

Các diễn giả đến từ VPBank, VIB, GoAsiaPacific Vietnam, GoTymeX và Cloud Kinetics đã chia sẻ nhiều kinh nghiệm thực tế trong việc xây dựng và triển khai các hệ thống AI trên nền tảng AWS.

Những ví dụ thực tế giúp tôi hiểu rõ hơn cách áp dụng kiến trúc Cloud hiện đại vào các dự án doanh nghiệp.

#### Tiếp cận kiến thức thực tiễn

Tôi được tìm hiểu chi tiết về kiến trúc sử dụng Amazon Bedrock kết hợp Lambda, API Gateway, CloudFront, S3 và DynamoDB để xây dựng một ứng dụng AI hoàn chỉnh.

Ngoài ra, phần trình bày về Context Engineering giúp tôi nhận ra rằng một hệ thống AI hiệu quả không chỉ phụ thuộc vào Prompt mà còn phụ thuộc rất nhiều vào Context.

#### Khám phá các công nghệ AI hiện đại

Workshop giúp tôi hiểu rõ hơn về Large Language Models, Temperature, Top-P, Top-K cũng như kiến trúc Multi-Agent.

Đặc biệt, phần so sánh giữa Single-Agent và Multi-Agent giúp tôi nhận thấy lợi ích của việc chia nhỏ nhiệm vụ cho nhiều AI Agent chuyên biệt để nâng cao hiệu quả xử lý.

#### Giao lưu và kết nối

Sự kiện còn mang đến cơ hội trao đổi với các chuyên gia AWS, kỹ sư AI và những người có cùng đam mê về Cloud Computing và Generative AI.

Qua các buổi trao đổi, tôi học hỏi thêm nhiều kinh nghiệm thực tế và mở rộng góc nhìn về xu hướng phát triển AI trong doanh nghiệp.

#### Bài học rút ra

- Context là yếu tố quan trọng quyết định chất lượng của hệ thống AI.
- Amazon Bedrock giúp triển khai Generative AI nhanh chóng mà không cần quản lý hạ tầng mô hình.
- Serverless Architecture giúp tối ưu chi phí và dễ dàng mở rộng.
- Multi-Agent Architecture là hướng phát triển đầy tiềm năng cho các hệ thống AI hiện đại.
- Sự kết hợp giữa Cloud Computing và Generative AI sẽ tạo ra những ứng dụng thông minh, linh hoạt và hiệu quả hơn trong tương lai.

#### Một số hình ảnh tham gia sự kiện

<p align="center">
  <img src="/images/4-Events/event2-1.jpg" width="45%" alt="Opening session">
  <img src="/images/4-Events/event2-2.jpg" width="45%" alt="Workshop discussion">
</p>

<p align="center">
  <img src="/images/4-Events/event2-3.jpg" width="45%" alt="Cloud architecture presentation">
  <img src="/images/4-Events/event2-4.jpg" width="45%" alt="Multi-Agent architecture presentation">
</p>

> Nhìn chung, **AWS First Cloud AI Journey – Community Day** không chỉ mang lại nhiều kiến thức chuyên môn về Cloud và Generative AI mà còn giúp tôi hiểu rõ hơn về kiến trúc hiện đại, cách xây dựng hệ thống AI trên AWS cũng như định hướng áp dụng những công nghệ này vào các dự án học tập và công việc trong tương lai.
