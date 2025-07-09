---
layout: post
title: Làm quen với Unix/Linux trong Data Science
date: 2025-07-08 11:05:23 +0700
categories:
    - module 1
tags:
    - introduction
    - unix
    - linux
    - command Line
    - shell
author:
summary: Thực hành với command line trong khoa học dữ liệu
---

### Roadmap for learning Data Science

![image.png](/assets/img/module_1/2025-07-08/roadmap-for-learning-data-science.png)

### Tổng quan về Unix/Linux

Linux là hệ điều hành mã nguồn mở phổ biến trong phân tích dữ liệu, mang lại hiệu quả cao nhờ khả năng xử lý dữ liệu qua command line và tích hợp tốt với công cụ phân tích hiện đại.

Tính chất đặc trưng của Linux:

- Mã nguồn mở
- Dùng cho phân tích dữ liệu
- Hiệu quả cao
- Tích hợp tốt

Linux có nhiều phiên bản (distributions) đáp ứng nhu cầu đa dạng của Data Science.

- Ubuntu: Ubuntu thân thiện với người dùng
- Debian: Cực kỳ ổn định, bảo mật cao. Lý tưởng cho nghiên cứu khoa học
- CentOS/RHEL: Tiêu chuẩn doanh nghiệp Hadoop/Big Data, tương thích enterprise
- WSL (Windows Subsystem for Linux): Linux trong Windows, không cần dual-boot hay máy ảo

![image.png](/assets/img/module_1/2025-07-08/logical-tree.png)

Triết lý Unix dựa trên đơn giản hóa, chuyên biệt hoá và tính nhất quán, tạo sức mạnh cho xử lý dữ liệu thông qua kết hợp các công cụ nhỏ chuyên biệt.

![image.png](/assets/img/module_1/2025-07-08/features-of-unix.png)

Shell là giao diện dòng lệnh trung gian giữa người dùng và hệ điều hành, giúp Data Scientists xử lý dữ liệu hiệu quả qua các lệnh cơ bản.

![image.png](/assets/img/module_1/2025-07-08/features-of-shell.png)

Linux tổ chức hệ thống file theo cấu trúc chuẩn với các thư mục chức năng chuyên biệt cho lệnh, dữ liệu người dùng, cấu hình, dữ liệu biến đổi, ứng dụng và phần mềm bên thứ ba.

![image.png](/assets//img/module_1/2025-07-08/construction-of-linux.png)

### Các lệnh cơ bản

Các lệnh Unix/Linux thiết yếu giúp Data Scientists làm việc với thư mục, quản lý files, tìm kiếm và xử lý dữ liệu hiệu quả.

1. **Làm việc với thư mục**
- `pwd`: hiển thị đường dẫn đầy đủ của thư mục hiện tại, giúp định vị vị trí hiện tại trong hệ thống.
- `cd`: di chuyển giữa các thư mục (cd .. : quay về thư mục cha, cd ~: về thư mục home)
- `ls`: liệt kê files và thư mục (-l: xem chi tiết trên dòng, -h: kích thước dễ đọc, -S: sắp xếp theo kích thước).
- `ls -la`: hiển thị tất cả files (kể cả ẩn), kèm thông tin quyền, kích thước và thời gian chỉnh sửa.
- `cd ~/datasets`: di chuyển đến thư mục datasets.
2. **Tạo và quản lý files/thư mục**
- `mkdir datasets`: tạo thư mục đơn.
- `mkdir -p projects/datasets`: tạo cấu trúc thư mục đa cấp.
- `touch data.csv`: tạo file trống.
- `touch {train, test, validation}.csv`: tạo nhiều file cùng lúc.
- `rm temp.csv`: xóa file đơn.
- `rm -i *.tmp`: xóa có xác nhận với người dùng.
- `rm -rf cache/`: xóa thư mục và mọi thứ bên trong nó.
- `cp source.csv target.csv`: sao chép file đơn.
- `cp -r data_folder backup_folder`: sao chép toàn bộ thư mục dữ liệu.
- `mv raw_data.csv processed_data.csv`: đổi tên file.
- `mv *.csv ~/projects/analysis/`: di chuyển nhiều files vào thư mục xác định.
3. **Xem nội dung file**
- `cat data.csv`: hiển thị toàn bộ nội dung file.
- `less data.csv`: duyệt qua file lớn để xem từng trang, dùng phím mũi tên để cuộn, “/” để tìm kiếm pattern và “q” để thoát chế độ.
- `head -n 10 data.csv`: xem 10 dòng đầu file.
- `tail -n 10 data.csv`: xem 10 dòng cuối file.
4. **Tìm kiếm files và dữ liệu**
- `find . -name "*.csv"`: tìm tất cả file csv trong thư mục hiện tại và thư mục con.
- `grep "pattern" data.csv`: tìm kiếm những dòng chứa “pattern” trong file cần tìm.
- `grep -r "data"`: tìm nội dung xuất hiện trong các files và thư mục con.
- `find . -name "*.csv" -mtime -7`: tìm files csv được tạo sửa trong 7 ngày qua.
5. **Thao tác với dữ liệu text cơ bản**
- `wc`: đếm số dòng, từ, ký tự trong file.
- `sort`: sắp xếp dữ liệu theo nhiều tiêu chí.
- `uniq`: lọc hoặc đếm dòng trùng lặp (thường dùng sau sort).

Linux sử dụng hệ thống phân quyền `rwx (read - write - execute)` cho từng đối tượng `(user - group - others)` để kiểm soát truy cập files.

![image.png](/assets/img/module_1/2025-07-08/interaction-of-users.png)

Quản lý tiến trình giúp theo dõi, kiểm soát và tối ưu hóa các tác vụ phân tích dữ liệu và huấn luyện mô hình (model) trong dự án Data Science.

- `ps aux | grep python`: liệt kê tất cả các process Python đang chạy, giúp theo dõi các script phân tích dữ liệu và model training đang hoạt động.
- `top -u username`: hiển thị process theo thời gian thực của user cụ thể, hữu ích khi theo dõi tài nguyên CPU/RAM cho các tác vụ Machine Learning nặng.
- `kill -9 PID`: dừng process theo ID khi model training bị treo hoặc script xử lý dữ liệu chiếm quá nhiều tài nguyên.
- `nohup python [train.py](http://train.py) &`: chạy script huấn luyện model ở background và duy trì chạy kể cả khi đăng xuất khỏi server, kết quả được lưu vào nohup.out

### Xử lý dữ liệu qua command line (nâng cao)

Pipe và Redirect là các công cụ thiết yếu trong Linux để điều hướng luồng dữ liệu, kết nối các lệnh và lưu trữ kết quả.

![image.png](/assets/img/module_1/2025-07-08/features-of-pipe-and-redirect.png)

Các lệnh filter trong Linux là công cụ mạnh mẽ giúp xử lý, biến đổi và trích xuất thông tin từ dữ liệu dạng văn bản, đặc biệt hiệu quả khi kết hợp với pipe và redirect.

- `sed`: thay thế văn bản, xử lý regex và lọc dòng.
- `awk`: xử lý theo cột với ngôn ngữ lập trình hoàn chỉnh.
- `cut`: trích xuất cột hoặc ký tự từ dữ liệu có cấu trúc.
- `tr`: thay thế hoặc xóa ký tự, chuyển đổi định dạng file.
- `grep`: tìm kiếm chuỗi/pattern trong nhiều files.

Xargs - xử lý dữ liệu song song: công cụ mạnh mẽ chuyển đổi input thành arguments cho lệnh khác, hỗ trợ xử lý dữ liệu song song và tối ưu hiệu suất cho các tác vụ phân tích dữ liệu lớn.

![image.png](/assets/img/module_1/2025-07-08/features-of-xargs.png)

Tải dữ liệu từ Internet có hai công cụ command line phổ biến để tải dữ liệu:

- `wget`: phù hợp với dữ liệu lớn, khả năng tiếp tục tải khi bị ngắt.
- `curl`: linh hoạt hơn cho tương tác APIs và xác thực.

Ngoài ra, các lệnh `tar` và `gzip` giúp đóng gói, nén và giải nén dữ liệu , tiết kiệm không gian lưu trữ và băng thông khi chia sẻ. Đặc biệt hữu ích khi làm việc với datasets lớn, cho phép xử lý dữ liệu nén mà không cần giải nén hoàn toàn.