---
layout: post
title: Tổng quan về cơ sở dữ liệu
date: 2025-06-29 12:11:32 +0700
categories:
    - module_1
tags:
    - Database
    - SQL
    - NoSQL
author:
summary: Tóm lược chung về các khái niệm trong cơ sở dữ liệu
---

Cơ sở dữ liệu (CSDL) và các hệ thống cơ sở dữ liệu đã và đang trở thành một phần không thể thiếu trong cuộc sống hàng ngày của chúng ta. Các hoạt động thường ngày gắn liền với tương tác cơ sở dữ liệu như: giao dịch ngân hàng, đặt chỗ, ... đều thông qua một chương trình phần mềm để truy cập đến CSDL.  

*[CSDL]: Cơ sở dữ liệu

1. **Một số định nghĩa**  
    **a. Dữ liệu là gì?**  
    Dữ liệu là toàn bộ những gì được máy tính lưu trữ và xử lý. Dữ liệu có thể là ký tự, con số, hình ảnh hoặc âm thanh.  
    **b. Thông tin là gì?**  
    Thông tin là một khái niệm phản ánh tri thức, sự hiểu biết của con người về một đối tượng. Có thể hiểu đơn giản thông tin chính là sản phẩm sau khi ta lọc từ dữ liệu dưới những điều kiện cần thiết với nhu cầu thực tế.  
    **c. CSDL là gì?**  
    CSDL là tập hợp dữ liệu có mối liên hệ chặt chẽ với nhau. Dữ liệu ở đây được hiểu là những gì có thể ghi nhận lại và có ý nghĩa rõ ràng.  
    CSDL phải có ý nghĩa rõ ràng và có những đặc tính cụ thể sau:  
        - CSDL phải biểu diễn một phần thế giới thực.  
        - CSDL là một tập hợp có cấu trúc của những thành phần dữ liệu có liên quan với nhau được lưu trữ trong máy tính.  
        - CSDL được thiết kế, xây dựng và lưu trữ để phục vụ cho mục đích cụ thể.  
    Lưu ý rõ rằng: Dữ liệu của một CSDL thu thập được phải có nguồn gốc, có liên quan với các sự kiện ở thế giới thực.  
    **d. Hệ quản trị CSDL**  
    Hệ quản trị CSDL là các chương trình cho phép người dùng tạo ra và duy trì dữ liệu. Người dùng có thể tự *định nghĩa*, *xây dựng*, *xử lý* và *chia sẻ* CSDL giữa những người dùng khác nhau và ứng dụng.  
        - *Định nghĩa CSDL*: là việc chỉ định kiểu dữ liệu, cấu trúc và ràng buộc của dữ liệu được lưu trữ trong CSDL.  
        - *Xây dựng CSDL*: là lưu trữ dữ liệu trên bộ nhớ phụ được điều khiển bởi một hệ quản trị CSDL.  
        - *Xử lý CSDL*: tập hợp các thao tác như truy xuất dữ liệu theo yêu cầu, cập nhật dữ liệu theo thời gian thực, phát sinh báo cáo từ dữ liệu.  
        - *Chia sẻ CSDL*: cho phép nhiều người dùng và nhiều ứng dụng truy xuất đến CSDL.  
    Hệ quản trị CSDL thường cung cấp một giao diện giứa người dùng và dữ liệu.  
    **e. Hệ CSDL**  
    Hệ CSDL là sự tích hợp giữa CSDL và hệ quản trị CSDL.  

2. **Một số đặc trưng của hướng tiếp cận CSDL**  
    Trước đây, người ta thường sử dụng hệ thống tập tin để quản lý dữ liệu, nhưng hệ thống này đã gây ra nhiều hạn chế cho người dùng:  
        - Dễ liệu dễ bị trùng lặp và dư thừa  
        - Dữ liệu dễ bị thiếu nhất quán  
        - Chia sẻ dữ liệu bị hạn chế  
        - Truy xuất khó khăn  
        - Khó khôi phục dữ liệu sau khi có sự cố  
        - ...  
    Chính vì vậy mà hướng tiếp cận theo CSDL đã ra đời và khắc phục được những hạn chế mà hướng tiếp cận theo tập tin mắc phải.  
    Để dễ hình dung và hiểu rõ hơn những đặc trưng mà hướng tiếp cận CSDL có, chúng ta sẽ xem xét bảng dưới đây:  

    | Các đặc trưng | Chi tiết đặc trưng|
    | :-----------: | :---------------- |
    | Tính tự mô tả | Hệ thống ngoài chứa CSDL còn chứa dữ liệu mô tả cấu trúc của CSDL và các ràng buộc liên quan. Dữ liệu này được lưu trong từ điển của hệ quản trị CSDL, được gọi là siêu dữ liệu (meta-data) |
    | Tính độc lập | Cấu trúc CSDL được lưu trữ trong từ điển của hệ quản trị CSDL và tách biệt với các chương trình truy xuất. Khi cấu trúc CSDL bị thay đổi thì không cần thay đổi chương trình ứng dụng |
    | Tính trừu tượng | Dữ liệu được trình bày ở mức trừu tượng, che đi những chi tiết lưu trữ thực sự bên trong CSDL |
    | Tính nhất quán | Dữ liệu được lưu trữ thống nhất, tránh trùng lặp thông tin. Cơ chế truy xuất dữ liệu cũng hợp lý tránh được xung đột tranh chấp dữ liệu tại mọi thời điểm |
    | Đa khung nhìn | Mỗi người dùng có thể có khung nhìn khác nhau về CSDL, có thể là một phần CSDL hoặc dữ liệu ảo, ... |

3. **Kiến trúc của hệ quản trị CSDL**  
    Dữ liệu trong hệ quản trị CSDL được mô tả theo 3 mức trừu tượng:  
        + Lược đồ quan niệm: Mô tả cấu trúc của toàn thể CSDL cho một cộng đồng người sử dụng.  
        + Lược đồ vật lý (lược đồ trong): mô tả cấu trúc lưu trữ vật lý dữ liệu.  
        + Lược đồ ngoài (lược đồ ngoài): mô tả một phần CSDL mà người dùng quan tâm và che giấu phần còn lại
    được mô tả trong hình dưới đây  
    ![Minh họa kiến trúc ba lược đồ](/assets/img/module_1/kien-truc-3-luoc-do.jpg)

4. **Mô hình dữ liệu**  
    Mô hình dữ liệu là một tập các khái niệm dùng để mô tả cấu trúc của CSDL, cũng như các ràng buộc trên CSDL đó.  
    Ta sẽ tìm hiểu các loại mô hình dữ liệu sau:  
    **a. Mô hình thực thể kết hợp**  
    Mô hình thực thể kết hợp được giới thiệu bởi **Chen** vào năm 1976 và ngày càng trở nên phổ biến. Đến năm 1988, ANSI [^1] chọn mô hình thực thể kết hợp là mô hình chuẩn cho hệ thống từ điển tài nguyên thông tin (IRDSS). [^2]  

    [^1]: American National Standards Institue
    [^2]: Information Resource Dictionary System

    Ứng dụng CSDL được mô tả trong hình dưới đây.  
    ![Mô hình thực thể - kết hợp](/assets/img/module_1/mo-hinh-tt-kh.jpg)  

    **b. Mô hình quan hệ**  
    Mô hình quan hệ được đề xuất bởi **E.F.Codd** vào năm 1970. Các hệ quản trị CSDL được đưa ra vào những năm 1980.  
    Ứng dụng CSDL được mô tả trong hình dưới đây.  
    ![Mô hình quan hệ](/assets/img/module_1/mo-hinh-quan-he.jpg)  

    Ngoài ra, còn có các mô hình dữ liệu khác như: mô hình hướng đối tượng, mô hình mạng, mô hình phân cấp, ...