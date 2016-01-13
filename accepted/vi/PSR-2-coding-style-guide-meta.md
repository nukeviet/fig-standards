Siêu tài liệu  PSR-2
===================

1.Tóm tắt
----------


Mục đích của hướng dẫn này là để giảm sự khó khăn khi lấy, hay đọc code của 1 người khác.
Việc này được thực hiện bằng cách liệu kê các qui tắc và ngoại lệ trong việc định dạng PHP code


Các quy tắc này bắt nguồn từ sự tương đồng trong cách định dạng của các thành viên trong dự án.
Khi các tác giả hợp tác với nhau trong nhiều dự án, sẽ rất có ích nếu có một hướng dẫn thống nhất áp dụng vào toàn bộ dự án. Do đó lợi ích của hướng dẫn này không nằm ở các qui tắc, mà năm trong việc phổ biên các quy tắc đó


2.  Bỏ phiếu
--------

- **Acceptance Vote:** [ML](https://groups.google.com/d/msg/php-fig/c-QVvnZdMQ0/TdDMdzKFpdIJ)


3. Errata
---------

### 3.1 - Multi-line Arguments (09/08/2013)


Sử dụng 1 hay nhiều dòng arguments *đối số* (nghĩa là mảng hay *anonymous functions*) không chia thành danh sách argument *đối số*.
Vì thế phần 4.6 không được tự động thực thi, mảng hay *anonymous functions* có thể viết thành nhiều dòng


Ví dụ dưới đây là hoàn toàn hợp lệ trong PSR-2:

```php
<?php
somefunction($foo, $bar, [
  // ...
], $baz);

$app->get('/hello/{name}', function ($name) use ($app) { 
    return 'Hello '.$app->escape($name); 
});
```

### 3.2 - Extending Multiple Interfaces (10/17/2013)


Khi mở rộng đa giao diện, danh sách `extends` nên được dùng như 1 danh sách `implements` như đã đề cập ở phần 4.1


