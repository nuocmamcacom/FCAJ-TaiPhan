---
title : "Kiểm tra Gateway Endpoint"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.3.2 </b> "
---

#### Tạo S3 bucket

1. Truy cập **S3 management console**
2. Trong Bucket console, chọn **Create bucket**

![Create bucket](/images/5-Workshop/5.3-S3-vpc/create-bucket.png)

3. Trong **Create bucket console**
- **Đặt tên bucket**: chọn tên chưa được dùng bởi bucket nào trên toàn cầu (gợi ý: số lab và tên của bạn)

![Bucket name](/images/5-Workshop/5.3-S3-vpc/bucket-name.png)

- Giữ nguyên các trường còn lại (mặc định)
- Kéo xuống và chọn **Create bucket**

![Create](/images/5-Workshop/5.3-S3-vpc/create-button.png)

- Tạo S3 bucket thành công.

![Success](/images/5-Workshop/5.3-S3-vpc/bucket-success.png)

#### Kết nối EC2 bằng Session Manager

- Trong workshop này, bạn sẽ dùng **AWS Session Manager** để truy cập một số **EC2 instance**. **Session Manager** là một tính năng được quản lý hoàn toàn của **AWS Systems Manager**, cho phép quản lý **Amazon EC2 instances** và cả máy ảo on-premises thông qua một shell web tương tác. Session Manager giúp quản lý instance an toàn và có thể kiểm tra mà không cần mở inbound port, không cần bastion host hay SSH key.

- Tham khảo [First Cloud AI Journey Lab](https://000058.awsstudygroup.com/1-introduce/) để hiểu sâu hơn về Session Manager.

1. Trong **AWS Management Console**, gõ ```Systems Manager``` vào ô tìm kiếm nhanh và nhấn **Enter**:

![system manager](/images/5-Workshop/5.3-S3-vpc/sm.png)

2. Trong menu **Systems Manager**, tìm **Node Management** ở thanh bên trái và chọn **Session Manager**:

![system manager](/images/5-Workshop/5.3-S3-vpc/sm1.png)

3. Nhấp **Start Session** và chọn EC2 instance tên **Test-Gateway-Endpoint**.
{{% notice info %}}
EC2 instance này đang chạy trong "VPC Cloud" và sẽ được dùng để kiểm tra kết nối đến Amazon S3 thông qua Gateway endpoint vừa tạo (s3-gwe).
{{% /notice %}}

![Start session](/images/5-Workshop/5.3-S3-vpc/start-session.png)

**Session Manager** sẽ mở một tab trình duyệt mới với shell prompt: `sh-4.2 $`

![Success](/images/5-Workshop/5.3-S3-vpc/start-session-success.png)

Bạn đã mở session thành công và kết nối tới EC2 instance trong VPC Cloud. Ở bước tiếp theo, chúng ta sẽ tạo S3 bucket và một file để kiểm tra.

#### Tạo file và upload lên S3 bucket

1. Chuyển về thư mục home của `ssm-user` bằng lệnh ```cd ~``` trong CLI

![Change user's dir](/images/5-Workshop/5.3-S3-vpc/cli1.png)

2. Tạo file test bằng lệnh ```fallocate -l 1G testfile.xyz```. Lệnh này sẽ tạo một file dung lượng 1GB tên là `testfile.xyz`.

![Create file](/images/5-Workshop/5.3-S3-vpc/cli-file.png)

3. Upload file lên S3 bucket bằng lệnh ```aws s3 cp testfile.xyz s3://your-bucket-name```. Hãy thay `your-bucket-name` bằng tên bucket bạn đã tạo trước đó.

![Uploaded](/images/5-Workshop/5.3-S3-vpc/uploaded.png)

Bạn đã upload file thành công lên S3 bucket. Bây giờ bạn có thể kết thúc session.

#### Kiểm tra object trong S3 bucket

1. Truy cập S3 console.
2. Nhấp vào tên bucket S3 của bạn.
3. Trong Bucket console, bạn sẽ thấy file đã upload.

![Check S3](/images/5-Workshop/5.3-S3-vpc/check-s3-bucket.png)

#### Tóm tắt phần này

Chúc mừng bạn đã hoàn thành việc truy cập S3 từ VPC. Ở phần này, bạn đã tạo Gateway endpoint cho Amazon S3 và dùng AWS CLI để upload object. Việc upload hoạt động vì Gateway endpoint cho phép giao tiếp đến S3 mà không cần Internet Gateway gắn vào "VPC Cloud". Điều này cho thấy Gateway endpoint là một đường truy cập an toàn đến S3 mà không phải đi qua Public Internet.
