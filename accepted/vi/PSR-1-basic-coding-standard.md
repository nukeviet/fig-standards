Basic Coding Standard
=====================

Tiêu chuần của phần này bao gồm các yêu cầu  cần có để mã hóa tiêu chuẩn(standard coding)mục đích đảm bảo một mức độ cao về khả năng tương thích giữa kỹ thuật với  chia sẻ code php

Các từ khóa "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" được giải thích như trong [RFC 2119](http://www.ietf.org/rfc/rfc2119.txt).

[RFC 2119]: http://www.ietf.org/rfc/rfc2119.txt
[PSR-0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md
[PSR-4]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md


1. Tổng quát
-----------

- Files chỉ có thể(MUST) sử dụng tags`<?php` và `<?=`

- Files chỉ có thể (MUST) sử dụng [UTF-8](https://vi.wikipedia.org/wiki/UTF-8) không dùng BOM cho  code PHP

- Files có thể (SHOULD) định nghĩa [symbols](http://tongquanvienthong.blogspot.com/2012/02/symbol-la-gi-dich-ra-thi-no-nghia-la-ky.html) (classes, functions, constants, etc.)
 hoặc gây ra hiệu ứng  lề ([side-effects](http://stevendo87.blogspot.com/2012/02/hieu-ung-le-side-effect-la-gi-loi-ich.html)) (e.g. generate output, change .ini settings, etc.)
  nhưng không nên (SHOULD NOT) làm cả 2

- Namespaces và classes phải(MUST) tuân theo quy chuẩn "autoloading" của PSR: [[PSR-0], [PSR-4]].

- Tên class phải( MUST) viết dưới dạng `StudlyCaps`.

- Tên constants của class phải (MUST) được viết hoa toàn bộ và có dấu gạch dưới ngăn cách giữa các từ

- Tên phương thức (Method) phải  (MUST)được viết dưới dạng `camelCase`.


2. Files
--------

### 2.1. PHP Tags

Code PHP phải (MUST) sử dụng tag `<?php ?>` đầy đủ hoặc  short-echo `<?= ?>` tags; Ngoài ra
không được(MUST NOT) sử dụng các tag thay đổi khác.

### 2.2. Character Encoding(Mã hóa kí tự)

code PHP phải (MUST)[UTF-8](https://vi.wikipedia.org/wiki/UTF-8) không dùng BOM

### 2.3. Side Effects(Hiệu ứng lề)

Một file nên( SHOULD) khai báo new [symbols](http://tongquanvienthong.blogspot.com/2012/02/symbol-la-gi-dich-ra-thi-no-nghia-la-ky.html) (classes, functions, constants,
etc.) và không gây ra bất kỳ hiệu ứng lề (side effects), hoặc nó nên (SHOULD) tạo ra hiệu ứng lề( side
effects),nhưng không nên (SHOULD NOT) làm cả 2.

Cụm từ "side effects" mang ý nghĩa là thực hiện  logic mà không liên quan tới với việc định nghĩa các classes, functions, constants, etc., *chỉ là từ việc include
file*.

"Side effects" bao gồm (nhưng không giới hạn): tạo output,sử dụng `require` hoặc `include`, kết nối đến các dịch vụ bên ngoài, thay đổi file
settings,phát hiện ra lỗi hoặc ngoại lệ (exceptions), chỉnh sửa biển global hoặc biến static,
đọc hoặc viết file, và v.v.

Dưới đây là 1 ví dụ về file chứa cả dinh nghia(declarations) và hiệu ứng lề (side effects);
i.e, an example of what to avoid:
Hàm bật tính năng [phát hiện lỗi](http://www.volvoxfund.com/learnphp/PHPNote/Bat_thong_bao_loi_khi_dich.html)
ini_set('error_reporting', E_ALL);

```php
<?php
// side effect: thay đổi ini settings
ini_set('error_reporting', E_ALL);

// side effect: loads a file
include "file.php";

// side effect: generates output
echo "<html>\n";

// declaration
function foo()
{
    // function body
}
```
Ví dụ sau đây là 1 file chứa các định nghĩa(declaration) không có hiệu ứng lề (side effects)


```php
<?php
// declaration
function foo()
{
    // function body
}

// conditional declaration is *not* a side effect(điều kiện để định nghĩa khi không có 1 side effect)
//khong ton tai file bar thì định nghĩa hàm bar
if (! function_exists('bar')) {
    function bar()
    {
        // function body
    }
}
```


3. Namespace and Class Names
----------------------------

Namespaces và classes phải (MUST) theo chuẩn "autoloading" PSR: [[PSR-0], [PSR-4]].
Điều này có nghĩa là mỗi lớp tương ứng 1 file và có ít nhất 1 level trong namespace:
 a top-level vendor name.

Tên class phải (MUST) viết dưới dạng `StudlyCaps`.

Code written for PHP 5.3 and after MUST use formal namespaces.

For example:

```php
<?php
// PHP 5.3 and later:
namespace Vendor\Model;

class Foo
{
}
```

Code written for 5.2.x and before SHOULD use the pseudo-namespacing convention
of `Vendor_` prefixes on class names.

```php
<?php
// PHP 5.2.x and earlier:
class Vendor_Model_Foo
{
}
```

4. Class Constants, Properties, and Methods
-------------------------------------------

The term "class" refers to all classes, interfaces, and traits.

### 4.1. Constants

Class constants MUST be declared in all upper case with underscore separators.
For example:

```php
<?php
namespace Vendor\Model;

class Foo
{
    const VERSION = '1.0';
    const DATE_APPROVED = '2012-06-01';
}
```

### 4.2. Properties

This guide intentionally avoids any recommendation regarding the use of
`$StudlyCaps`, `$camelCase`, or `$under_score` property names.

Whatever naming convention is used SHOULD be applied consistently within a
reasonable scope. That scope may be vendor-level, package-level, class-level,
or method-level.

### 4.3. Methods

Method names MUST be declared in `camelCase()`.
