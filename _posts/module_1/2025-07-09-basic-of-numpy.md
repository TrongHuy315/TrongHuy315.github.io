---
layout: post
title: Numpy cơ bản
date: 2025-07-09 12:02:24 +0700
categories:
    - module 1
tags:
    - introduction
    - numpy
    - matrix
    - array
author:
summary: Nền tảng numpy
---

Trước khi đi tìm hiểu các khái niệm liên quan tới Numpy, chúng ta sẽ tìm hiểu sơ lược qua về các định nghĩa cơ bản trong toán học có liên quan đến phần kiến thức này.  

### List vs Numpy
Vector biểu diễn các điểm trong không gian hai hoặc nhiều chiều.  
Array là tập hợp các vector trong không gian xác định.  

Trong thực tế, những dữ liệu phức tạp như ảnh 2D sẽ được biểu diễn thông qua ma trận hai chiều hoặc ảnh RGB sẽ được biểu diễn qua ma trận 3 chiều (có thêm một chiều màu).  

**So sánh**
- List là tập hợp những phần tử có thứ tự và những phần tử trong List có kiểu bất kỳ.  
- Numpy Array có thể được tạo từ List nhưng yêu cầu những phần tử bên trong phải có cùng kiểu dữ liệu.  

### Nội dung về Numpy  
Để biết được kích thước của Numpy, sử dụng lệnh `shape` sẽ trả về một tuple cho biết kích thước mỗi chiều.  
Dưới đây là một ví dụ cho thấy cách biểu diễn chiều trong Numpy.  
```python
    import numpy as np

    arr_1 = np.array([1, 2, 3, 4])
    print(arr_1.shape)

    arr_2 = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])
    print(arr_2.shape)

    arr_3 = np.array([
        [
            [1, 2],
            [3, 4]
        ],
        [
            [5, 6],
            [7, 8]
        ],
        [
            [9, 10],
            [11, 12]
        ]
    ])
    print(arr_3.shape)

    # ...

    # (4, )
    # (2, 3)
    # (3, 2, 2)
```

Numpy cũng cung cấp rất nhiều hàm để khởi tạo array.  
```python
    import numpy as np

    a = np.zeros((2, 2))   # Tạo một ma trận có tất cả các phần tử là 0
    print(a)

    b = np.ones((2, 2))   # Tạo một ma trận có tất cả các phần tử là 1
    print(b)

    c = np.full((2, 2), 3)   # Tạo một ma trận có tất cả các phần tử là hằng số
    print(c)

    d = np.eye(2)   # Tạo một ma trận đơn vị kích thước (2 x 2)
    print(d)

    e = np.randomm.random((2, 2))   # Tạo một ma trận có các phần tử mang giá trị ngẫu nhiên trong khoảng (0, 1)
    print(e)

    f = np.arange(7)   # Tạo một ma trận có các phần tử từ 0 đến 6
    print(f)

    # [[0.  0.], [0.  0.]]
    # [[1.  1.], [1.  1.]]
    # [[3.  3.], [3.  3.]]
    # [[1.  0.], [0.  1.]]
    # [[0.15145274  0.52435282], [0.45243267  0.45352582]]
    # [0, 1, 2, 3, 4, 5, 6]
```

Tương tự như List, ma trận Numpy cũng có thể sử dụng slicing để cắt các phần xác định trong ma trận.  
```python
    import numpy as np

    a = np.array([
        [1, 2, 3, 4],
        [5, 6, 7, 8],
        [9, 10, 11, 12]
    ])

    b = a[:2, 1:3]
    print(b)

    # [[2, 3], [6, 7]]

    # Khi thay đổi giá trị phần tử trong b thì phần tử tương ứng trong a sẽ thay đổi, vì bản chất b chỉ đang trỏ tới vùng cùng địa chỉ với a
```

Ngoài ra, có thể tận dụng việc tối ưu hóa indexing trong Numpy để truy xuất một cách nhanh chóng thay vì thủ công.
```python
    import numpy as np

    a = np.array([
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
    ])

    print(a[[0, 1, 2], [0, 1, 1]])

    # [1, 5, 8]

    # Một cách khác để truy cập phần tử nhưng thủ công hơn
    print(np.array([a[0, 0], a[1, 1], a[2, 1]]))

    # [1, 5, 8]
```

Các phần tử trong ma trận Numpy thường sẽ được xác định kiểu dữ liệu tự động nếu không có đối số truyền vào các hàm khởi tạo ma trận trong Numpy.  
```python
    import numpy as np

    x = np.array([1, 2])
    print(x.dtype)

    y = np.array([3.0, 4.0])
    print(y.dtype)

    z = np.array([5.3, 6.4], dtype=np.float64)
    print(z.astype(np.int64).dtype)   # Ép kiểu từ float64 về int64 (Numpy hỗ trợ casting)

    # int64
    # float64
    # int64
```

Đặc biệt hơn là, Numpy hỗ trợ việc thao tác giữa các ma trận với nhau thông qua các toán tử `+`, `-`, `*`, `/`, `sqrt()`, ... như các số có kiểu dữ liệu nguyên thủy.  
Để nhân tích vô hướng hai ma trận, chúng ta sử dụng hàm `dot`.  
```python
    import numpy as np

    a = np.array([
        [1, 2],
        [3, 4]
    ])

    b = np.array([
        [5, 6],
        [7, 8]
    ])

    print(a.dot(b))
    print(np.dot(a, b))

    # 70
    # 70
```

Ngoài ra, Numpy hỗ trợ chuyển vị ma trận khi sử dụng ký tự `T`.  
```python
    import numpy as np

    a = np.array([
        [1, 2],
        [3, 4]
    ])

    print(a)
    print(a.T)

    # [[1, 2], [3, 4]]
    # [[1, 3], [2, 4]]
```

Bên cạnh đó, cơ chế broadcasting của Numpy cũng hỗ trợ đặc biệt cho việc thực thi các thao tác phức tạp trên ma trận như cộng mỗi hàng trong một ma trận cho một vector hằng.  
```python
    import numpy as np

    a = np.array([
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
    ])

    b = np.array([1, 0, 1])

    c = a + b
    print(c)

    # [[2, 2, 4], [5, 5, 7], [8, 8, 10]]
```

Các bạn muốn tìm hiểu sâu hơn về Numpy có thể tham khảo tài liệu đầy đủ tại [documentation](https://numpy.org/doc/stable/reference/routines.math.html).

*[Array]: Ma trận
*[RGB]: gồm ba màu cơ bản red, green, blue