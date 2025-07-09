---
layout: post
title: Biến trong Python
date: 2025-07-09 20:36:34 +0700
categories:
    - module 1
tags:
    - variable
    - python
    - rule
author:
summary: Kiến thức liên quan về biến trong Python (phần 1)
---

Mọi người nên chạy thử các chương trình Python làm quen thông qua một số ví dụ đơn giản (có thể kiếm trên google) trước khi đọc bài post này.  
Để làm quen với biến, chúng ta sẽ tìm hiểu về quy tắc đặt tên biến trong Python, tưởng đơn giản nhưng hóa ra lại rất quan trọng.

### Quy tắc đặt tên biến  
Mỗi ngôn ngữ lập trình, mỗi môi trường phát triển đều có những quy tắc, luật lệ riêng. Python cũng không phải ngoại lệ. Các biến trong Python được đặt theo những quy tắc sau:  
    + Tên biến chỉ có thể chứa chữ cái, số và dấu gạch dưới (_). Có thể bắt đầu bằng chữ cái hoặc dấu gạch dưới, nhưng không được bắt đầu bằng số.  
        VD: `bien`, `_bien` thì được, còn `1_bien` thì không được phép sử dụng.  
    + Khoảng trống không được phép khi đặt tên biến, nhưng có thể sử dụng dấu gạch dưới để phân tách các từ trong biến cho dễ đọc, dễ hiểu.  
    + Biến trong Python không được đặt trùng với tên các từ khóa hoặc tên các hàm được khai báo.  

Quy tắc đặt tên biến trong Python còn được gọi là camel rule, đơn giản vì hình dạng tên biến được khai báo lồi lõm nhờ dấu gạch dưới khiến người ta liên tưởng đến con lạc đà.  

*[từ khóa]: keyword

### Các kiểu dữ liệu trong Python  
Trong Python, ta có 5 kiểu dữ liệu chuẩn sau: `Number`, `String`, `List`, `Tuple`, `Set`, `Dictionary`.  
Ngoài ra, ta có thể sử dụng hàm `type` để kiểm tra kiểu dữ liệu của biến.  

1. **Number**  
Python sẽ hỗ trợ 5 kiểu dữ liệu numbers khác nhau: `Int`, `Float`, `Long`, `Complex` (Số phức), `Fraction` (Số thập phân).  
Bên cạnh đó, Python cũng hỗ trợ các phép toán cơ bản với các kiểu dữ liệu number trên như: `+`, `-`, `*`, `/`, `%`, `//`, `**`.  

2. **String**  
Chuỗi trong Python được biểu diễn bằng nhiều cách, các chuỗi có thể nằm trong dấu ngoặc đơn `''` hoặc dấu ngoặc kép `""` hoặc nhiều cặp dấu ngoặc kép `""""` đều được Python hỗ trợ.  
Bản chất chuỗi trong Python là bất biến, nếu có thao tác CRUD trên một chuỗi thì thực tế là nhận lại bản sao ở vùng địa chỉ khác chứa chuỗi mới trong Python. Các ký tự trong chuỗi được lập chỉ mục để có thể thao tác.  
Có thể nối chuỗi trong Python bằng toán tử `+`.  
    ```
        word = "Python"
        print(word[0])
        print(word[0:2])
        print(word[2:5])

        sub_word = "here"
        print(w + sub_word)

        # P
        # Py
        # tho
        # Python here
    ```
*[bất biến]: immutable
*[CRUD]: Create, Read, Update and Delete

3. **List**  
List được biểu diễn bằng dãy các giá trị, phân cách nhau bởi dấu `,` và nằm trong cặp ngoặc vuông `[]`.  
Các phần tử trong List có thể có các kiểu dữ liệu khác nhau, nhưng thường chúng sẽ cùng kiểu để biểu diễn như một ma trận.  
    ```
        vd = [1, 2, 4, 8]
        haha = ["hay", 'hi', 3.0, -6]
    ```
List trong Python hỗ trợ chỉ mục để có thể truy cập một cách dễ dàng.  
Các phương thức khác có thể thao tác trên List như: `append`, `del`, ...  

(Còn tiếp, sẽ cập nhật sau khi tui thi xong ...)