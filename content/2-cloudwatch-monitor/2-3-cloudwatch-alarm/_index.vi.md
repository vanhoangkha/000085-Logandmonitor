---
title : "Tạo cảnh báo với CloudWatch Alarm"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.3. </b> "
---
1. Mở bảng điều khiển của [CloudWatch]()
2. Mở rộng **Alarms** phía bên trái, ấn **In alarm**
3. Ấn **Create alarm**
4. Ấn **Select metric**
5. Chọn metric vừa tạo ở bước trước - **BooksList_Lambda**, sau đó ấn **env**, tiếp theo chọn **staging**
- Ấn **Select metric**
6. Chọn **Sum** cho mục **Statistic**
7. Thiếp lập điều kiện tại mục condition
- Chọn **Static** cho **Threshold type**
- Chọn **Greater/Equal** làm điều kiện cho cảnh báo
- Nhập **2** là giá trị của ngưỡng cảnh báo
8. Ấn **Next**
9. Chọn **Create new topic**
10. Nhập tên topic
12. Nhập email mà bạn muốn nhận thông báo
13. Ấn **Create topic**
14. Kéo xuống dưới, ấn **Next**
15. Nhập tên cho cảnh báo
- Ấn **Next**
16. Kéo xuống cuối và ấn **Create alarm**
17. Trở lại với màn hình của Postman, bạn hãy ấn **Send** hai lần để gọi API hai lần
18. Mở email và kiểm tra 
19. Trở lại với bảng điều khiển của CloudWatch
20. Ấn **All alarms**, sau đó chọn cảnh báo mà bạn vừa tạo
21. Biểu đồ của metric được hiện thị