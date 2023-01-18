---
title : "Tạo custome metric"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.2. </b> "
---
CloudWatch metric cung cấp sẵn một vài metric cho Lambda function như: số lần function được thực thi, thời gian thực thi của mỗi lần, error rates, và throttle count. Để xem các metric của một function nào đó chúng ta thực hiện như sauL
1. Mở bảng điều khiển của Lambda function
2. Ấn vào function **book-list**
3. Ấn tab **Monitor**, chọn **Metrics**
- Các metric được hiện thị
4. Tiếp theo chúng ta sẽ tạo một metric mới tổng hợp số lần truy cập vào DynamoDB bị lỗi
5. Ấn tab **Code**, thêm dòng code sau ở đầu function
```
client_cloudwatch = boto3.client('cloudwatch')
```
- Thêm đoạn code sau vào except block của scan bảng DynamoDB trước khi trả về kết quả
```
        client_cloudwatch.put_metric_data(
            Namespace='BooksList_Lambda',
            MetricData=[
                {
                    'MetricName': 'FailedConnectToDynamoDB',
                    'Dimensions': [
                        {
                            'Name': 'env',
                            'Value': 'staging'
                        },
                    ],
                    'Value': 1.0,
                    'Unit': 'Seconds'
                },
            ]
        )
```
- Đoạn code giúp bạn tạo một metric mới và đẩy dữ liệu vào đó mỗi lần kết nối với DynamoDB bị lỗi

6. Cấp quyền cho function được phép truy cập vào đẩy dữ liệu vào metric
7. Gọi GET API lần nữa 
8. Mở bảng điều khiển của CloudWatch
9. Ấn vào Mectrics ở menu phía bên trái, sau đó ấn **All metrics**
10. Trong mục **Custom namespaces** xuất hiện metric mà bạn tạo - **BooksList_Lambda**. Ấn vào nó
11. Ấn **env**
12. Chọn **staging**, biểu đồ hiện thị dữ liệu
13. Bạn có thể tuy chọn các thông số hiện thị theo thời gian 1 ngày hay 1 tuần, kiểu hiện thị dòng hay số ở phía bên trên đồ thị
Vậy là chúng ta đã tạo xong một custom metric. Bước tiếp theo chúng ta sẽ sử dụng nó để tạo một CloudWatch Alarm
