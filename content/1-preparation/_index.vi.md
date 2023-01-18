---
title : "Chuẩn bị"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
Trước khi thực hiện nội dung chính của workshop này, chúng ta chuẩn bị các dịch vụ và dữ liệu cho ứng dụng.
1. Tải source code của sam project dưới đây

{{%attachments title="SAM source" pattern=".*\.(zip)$"/%}}

2. Chạy câu lệnh dưới đây để triển khai sam
```
sam build
sam deploy --guided
```

3. Mở bảng điều khiển của [CloudFormation]()
4. Đợi stack được tạo xong, bấm vào stack **fcj-book-store**

![CreateRepository](/images/1-preparation/1-preparation-1.png?featherlight=false&width=90pc)

5. Ấn **Output** tab, ghi lại API URL

![CreateRepository](/images/1-preparation/1-preparation-2.png?featherlight=false&width=90pc)

6. Tải tệp dữ liệu cho DynamoDB sau

{{%attachments title="SAM source" pattern=".*\.(json)$"/%}}

7. Chạy câu lệnh sau tại thư mục chứa tệp json bạn vừa tải về để ghi dữ liệu lên bảng **Books** trong DynamoDB
```
aws dynamodb batch-write-item --request-item file://dynamoDB.json
```

8. Mở bảng điều khiển của [AWS DynamoDB]()

![CreateRepository](/images/1-preparation/1-preparation-3.png?featherlight=false&width=90pc)

9. Ấn **Tables** ở menu phía bên phải

![CreateRepository](/images/1-preparation/1-preparation-4.png?featherlight=false&width=90pc)

10. Ấn **Explore items**
- Chọn bảng **Books**, dữ liệu bảng đã được ghi lên

![CreateRepository](/images/1-preparation/1-preparation-5.png?featherlight=false&width=90pc)

Chúng ta đã chuẩn bị xong source cần thiết cho các bước tiếp theo.
