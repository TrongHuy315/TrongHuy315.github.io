---
layout: post
title: Classes và Objects trong Python
date: 2025-07-15 9:37:12 +0700
categories:
    - module 1
tags:
    - class
    - object
    - oop
author:
summary: Tìm hiểu căn bản về OOP trong Python
---

Các khái niệm cơ bản về biến và kiểu dữ liệu trong Python đã được mình giới thiệu trong bài trước, mọi người có thể xem [tại đây](https://tronghuy315.github.io/posts/variable-in-python/) trước khi đi vào bài đọc này.  

### Các khái niệm  
OOP là kỹ thuật lập trình cho phép trừu tượng hóa một đối tượng thực tế thành một đối tượng dùng trong lập trình.  
Mỗi đối tượng bao gồm thuộc tính (attribute) và phương thức (method) đặc trưng đi kèm.  
    + Thuộc tính: là dữ liệu của đối tượng (đặc điểm, thông tin, ... của đối tượng).  
    + Phương thức: là hành động, thao tác mà đối tượng thực hiện.  
Lớp (Class) là một bản thể chung cho tập hợp các đối tượng chung một nhóm.  
Đối tượng (Object) là một bản thể cụ thể (có tính riêng) được tạo ra từ lớp.  

OOP có 4 tính chất đặc trưng cơ bản như sau:  
    - Tính đóng gói (Encapsulation): Các dữ liệu và phương thức có liên quan với nhau được đóng gói thành 1 lớp. Tức là mỗi lớp được xây dựng để thực hiện một nhóm chức năng đặc trưng của riêng lớp đó. Che giấu các thông tin của lớp đó đối với bên ngoài thể hiện ở public, protected, private đối với từng thuộc tính và phương thức.  
    - Tính kế thừa (Inheritance): Nguyên tắc này cho phép xây dựng một lớp mới dựa trên 1 lớp đã khai báo từ trước. Lớp con có thể sử dụng lại các thuộc tính và phương thức của lớp cha mà không cần khai báo lại. Tùy thuộc vào từng ngôn ngữ cho phép việc kế thừa 1 hoặc nhiều class cha.  
    - Tính trừu tượng (Abstraction): tổng quát hóa phương thức của đối tượng không quan tâm phương thức thực hiện như thế nào, được thể hiện bởi interface (có các tên phương thức nhưng ko có body của phương thức, khi class nào impliment interface thì thực hiện nó).  
    - Tính đa hình (Polymorphism): Tính đa hình được thể hiện bởi một phương thức, hành động có thể thực hiện theo nhiều cách khác nhau. VD: chó mèo cùng là động vật nhưng khi thực hiện phương thức 'sủa' thì chó sủa 'gogo', mèo sủa 'méo mèo'.  

Trong Python có một phương thức đặc biệt gọi là `__init__()` dùng để khởi tạo giá trị cho các thuộc tính của một đối tượng.  
```python
    class dog:
        legs = 4;
        
        def __init__(self, name):
            self.name = name

    pug = dog('bug')
    print pug.name
    print pug.legs

    husky = dog('husky')
    print husky.name
    print husky.legs
```
Phương thức __init__() là phương thức khởi tạo của tất cả các lớp, mỗi khi tạo một đối tượng phương thức này sẽ tự động được gọi. Bất cứ phương thức nào của Python cũng đều phải có tham số đầu tiên là self rồi mới đến các tham số khác. self ám chỉ đối tượng đã được gọi đó. Chẳng hạn trong ví dụ trên khi chúng ta gọi pug = dog('bug') thì self chính là đối tượng pug.  

Về bản chất trong python thì các khái niệm về private, protected, public không có, trong code chúng ta chỉ ám chỉ điều này cho việc truy cập cho đúng:  
    - Với public thì có thể truy cập được ở mọi nơi, nên cách khai báo như hàm bình thường.  
    - Với protected thì chỉ lớp con có thể truy cập được, cách khai báo bằng cách bắt đầu bằng một dấu gạch ngang "_", VD: _age. Chúng ta sẽ ngầm hiểu là ko sử dụng nếu không phải là class con.  
    - Với private thì chỉ class đó có quyền truy cập, cách khai báo bằng cách bắt đầu bằng 2 dấu gạch ngang "__", VD: __age.  
```python
    class Foo:
        __name = "Foo"

        def __getName(self):
            print(self.__name)

        def get(self):
            self.__getName()

    print(Foo().__name) #error
    Foo().__getName() #error
    Foo().get()
```

#### Kế thừa trong Python  
```python
    class Animal:
    legs = '0'

    def __init__(self):
        pass

    def whoAmI(self):
        print ("Animal")
    
    def eat(self):
        print ("Eating")
    
    
    class Dog(Animal):
    def __init__(self):
        Animal.__init__(self)
        print ("Dog created")
        self.legs = '4'
    
    def whoAmI(self):
        print ("Dog go go")
    
    def eat(self):
        print ("eat eat eat .....")

    def run(self):
        print ("legs: " + self.legs + " run run run .....")
    
    
    d = Dog()
    d.whoAmI()
    d.eat()
    d.run()
```

***Các khái niệm liên quan abstract class, interface có thể tham khảo bên ngoài (do lười quá `=))`).***  

*[OOP]: Object-Oriented Programming