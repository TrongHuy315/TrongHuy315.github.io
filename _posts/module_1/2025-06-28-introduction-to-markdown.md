---
layout: post
title: "Làm quen với Markdown"
date: 2025-06-28 22:03:00 +0700
categories:
    - module_1
tags:
    - introduction
    - markdown
author:
summary: Luyện cú pháp markdown trước khi viết blog
---

*Để chuẩn bị nội dung các bài post thật là chỉn chu, sạch đẹp trong tương lai thì bài post này là một kiến thức hữu ích để chuẩn bị hành trang sắp tới. Dự định xa hơn là tham gia các cuộc thi, luận án tốt nghiệp hoặc CV công việc, ...*  

1. Cú pháp Markdown cơ bản

Sử dụng # ở đầu dòng để viết tiêu đề:
```
    #: Tiêu đề cấp 1
    ##: Tiêu đề cấp 2
    ###: Tiêu đề cấp 3
    ####: Tiêu đề cấp 4
    ...
```
hoặc có thể trình bày tiêu đề như này:
```
    Tiêu đề cấp 1
    ====================

    Tiêu đề cấp 2
    --------------------
```

Các đoạn văn được phân cách với nhau bởi một hoặc nhiều dòng trống (giống trong latex).
```
    Đoạn thứ nhất

    Đoạn thứ hai
```

Để xuống dòng trong cùng một đoạn văn, sử dụng dấu hai cách ở cuối câu và trình bày nội dung câu tiếp theo ở dòng mới.
```
    Dòng thứ nhất  <- Ở đây có 2 dấu cách
    Dòng thứ hai
```

Định dạng chữ thông qua số lượng dấu * hoặc dấu _ như sau:
```
    *In nghiêng*
    _In nghiêng_

    **In đậm**
    __In đậm__

    ***In nghiêng, in đậm***
    ___In nghiêng, in đậm___
```

Trong markdown có thể sử dụng trích dẫn '>', chúng có thể lồng nhau
```
    > Trích dẫn

    > > Trích dẫn lồng
```

Danh sách có thể được biểu diễn thông qua các dấu '*', '+' hoặc '-' như sau:
```
    - Mục 1
    - Mục 2
        * Mục con 2.1
        * Mục con 2.2
    - Mục 3

    hoặc

    1. Mục thứ nhất
    2. Mục thứ hai
    3. Mục thứ ba   (Mục có thể ghi sai thứ tự, markdown sẽ tự động chỉnh sửa lại)
```

Trong các phần trình bày, thường có một đường gạch ngang đi hết một trang, sử dụng ba hoặc nhiều hơn các ký tự đơn '*', '-', '_':
```
    ***
    ---
    ___
```

Liên kết ngắn gọn trong một đoạn text làm cho văn bản trông đẹp hơn:
```
    This is [link](https://www.facebook.com/TrongHuyDo315)
```

Đối với hình ảnh cũng như vậy, có thêm dấu '!' ở đầu dòng
```
    ![Văn bản thay thế khi ảnh không được hiển thị](https://www.facebook.com/photo/?fbid=2078835615956371&set=a.231176424055642)
```

Sử dụng ký tự '\' đứng trước các ký tự đặc biệt để hiển thị được chúng
```
    \* Không phải in nghiêng \*
```

2. Cú pháp Markdown mở rộng

Tính năng vẽ bảng trong markdown thực sự hữu ích
```
    | Tiêu đề 1 | Tiêu đề 2 | Tiêu đề 3 |
    | :-------- | :-------: | --------: |
    | Căn trái  |  Căn giữa |  Căn phải |
    | Nội dung  |  Nội dung |  Nội dung |
```

Khối code block được biểu diễn:
```
    ```<Loại code block đi kèm, mặc định là plaintext>

        Nội dung trong block ở đây

    ```
```

Chú thích ở cuối trang, được biểu diễn:
```
    Ở đây có chú thích.[^1]

    [^1]: Đây là nội dung của chú thích
```

Để gạch ngang một đoạn văn bản (dạng như outdated hoặc lỗi thời), sử dụng '~~':
```
    ~~ Đã bị gạch bỏ ~~
```

Danh sách công việc:
```
    - [x] Tác vụ đã hoàn thành
    - [] Tác vụ chưa hoàn thành
        - [] Tác vụ con
```

Để highlight một từ, dòng hoặc văn bản, sử dụng '==' và kẹp hai đầu:
```
    == Đã được đánh dấu ==

    -> == được hỗ trợ bởi một số nền tảng theme nhất định, cần tìm hiểu phù hợp trước khi sử dụng
```

Có thể sử dụng biểu tượng cảm xúc bằng cách gán trực tiếp (được lấy từ Pichon từ Microsoft Store trong việc thiết kế UI ứng dụng) hoặc dùng mã rút gọn:
```
    :smile:   :tada:   :rocket:
```

Có thể thêm id hoặc class vào cho một đoạn markdown:
```
    Văn bản nè
    {:.my-class #my-id}
```

Ngoài ra còn có hỗ trợ định nghĩa viết tắt (giải thích nội dung 1 lần, sử dụng nhiều lần)
```
    Những ví dụ về HTML.

    *[HTML]: HyperText Markup Language
```
