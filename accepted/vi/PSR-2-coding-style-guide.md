Hướng dẫn về Coding Style
==================


Hướng dẫn này được dựa trên và phát triển từ [PSR-1], các tiêu chuẩn coding cơ bản


Mục đích của hướng dẫn này là để giảm sự khó khăn khi đọc code của những người khác, bằng cách đặt ra các tiêu chuẩn chung hay gợi ý về việc format PHP code


Các tiêu chuẩn về style ở đây đều được bắt nguồn từ sự giống nhau giữa các dự án khác nhau.Khi mọi người hợp tác với nhau trong cùng 1 dự án, những tiêu chuẩn này sẽ là bộ tiêu chuẩn chung được dùng trong toàn bộ dự án đó.Vì vậy lợi ích đạt được không nằm ở những tiêu chuẩn này mà còn ở việc chia sẻ những tiêu chuẩn này


Những từ "MUST" *PHẢI*, "MUST NOT" *PHẢI KHÔNG...*, "REQUIRED" *BẮT BUỘC*, "SHALL", "SHALL NOT", "SHOULD" *NÊN*,
"SHOULD NOT" *KHÔNG NÊN*, "RECOMMENDED" *KHUYẾN CÁO*, "MAY" *CÓ THỂ*, và "OPTIONAL" *KHÔNG BẮT BUỘC* trong tài liệu này cần được hiểu như trong mô tả ở [RFC 2119].

[RFC 2119]: http://www.ietf.org/rfc/rfc2119.txt
[PSR-0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md
[PSR-1]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md


1. Khái Quát
-----------


- Code PHẢI tuân theo "coding style guide" PRS [[PSR-1]]


- Code không dùng tab mà PHẢI dùng 4 dấu cách để indenting *căn lề*


- KHÔNG có hard limit về độ dài của 1 dòng; soft limit PHẢI là 120 ký tự; 1 dòng NÊN từ 80 ký tự trở xuống


- PHẢI có 1 dòng trống sau phần khai báo `namespace`, và PHẢI có 1 dòng trống sau phần khái báo `use`


- Dấu mở ngoặc nhọn khi khai báo class PHẢI viết ở dòng mới* xuống dòng* và khi đóng ngoặc PHẢI viết ở dòng mới sau phần body


- Dấu ngoặc nhọn khi khai khai báo methods PHẢI viết ở dòng mới* xuống dòng* và khi khi đóng ngoặc phải viết ở dòng mới sau phần body


- Visibility *public protect private* PHẢI được khai báo trong các properties và methods; `abstract` và `final` PHẢI được khai báo phía trước visibility; `static` PHẢI khai báo phái sau visibility
  

- Phía sau của Control structure keywords*if else for* PHẢI có dấu cách


- Dấu mở ngoặc nhọn của control structures PHẢI viết cùng dòng và khi đóng ngoặc phải viết ở dòng mới sau phần body


- Dấu mở ngoặc đơn của control structures PHẢI KHÔNG có dấu cách phía sau và cả khi đóng ngoặc cũng PHẢI KHÔNG có dấu cách phía trước

### 1.1.Ví dụ


Ví dụ sau đây bao gồm một vài quy định đã được nói ở phần Tồng Quan
```php
<?php
namespace Vendor\Package;

use FooInterface;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class Foo extends Bar implements FooInterface
{
    public function sampleFunction($a, $b = null)
    {
        if ($a === $b) {
            bar();
        } elseif ($a > $b) {
            $foo->bar($arg1);
        } else {
            BazClass::bar($arg2, $arg3);
        }
    }

    final public static function bar()
    {
        // method body
    }
}
```

2.Tổng thể
----------

### 2.1Tiêu chuẩn cơ bản của Coding


Code PHẢI tuân theo tất cả các quy tắc được nêu ra trong phần [PSR-1].

### 2.2 Các Tập tin


Tất cả các tập tin PHP PHẢI sử dụng Unix LF (linefeed) line ending.


Tất cả các tập tin PHP PHẢI kết thúc bằng 1 dòng trống


Trong tập tin chỉ chứa PHP thì KHÔNG PHẢI viết thẻ đóng `?>`

### 2.3. Dòng


KHÔNG có hard limit về độ dài của 1 dòng


Soft limit độ dài của 1 dòng phải là 120 ký tự; automated style checkers PHẢI cảnh báo nhưng sẽ không báo lỗi khi vượt qua soft limit


1 Dòng Không nên dài hơn 80 ký tự; Nếu dài hơn 80 ký tự thì dòng đó NÊN được chia thành nhiều dòng và mỗi dòng không nhiều hơn 80 ký tự


Dòng không trống *non-blank lines* PHẢI KHÔNG có trailing whitespace *dấu cách cuối dòng* ở cuối


Dòng trống CÓ THỂ được thêm vào để dễ đọc hơn và cho thấy mối quan hệ của các khối lệnh


Mỗi dòng PHẢI KHÔNG quá 1 statement.

### 2.4.Căn lề


Code Phải dùng 4 dấu cách chứ KHÔNG PHẢI dùng tabs để căn lề


> N.b.: Chỉ sử dụng dấu cách và không trộn dấu cách và tabs, giúp tránh được các vấn đề với diffs, patches, history, and annotations.
> Khi sử dụng dấu cách cũng khiến việc chèn fine-grained sub-indentation vào giữa các dòng

### 2.5. Keywords and True/False/Null *Từ Khóa và True/False/Null*


Các [keywords] PHP PHẢI viết thường

Các Hằng số PHP `true`, `false`, và `null` PHẢI viết thường
[keywords]: http://php.net/manual/en/reserved.keywords.php



3. Khai báo  Namespace và Use
---------------------------------


Khi sử dụng PHẢI có 1 dòng trắng phía sau khai báo `namespace`

Khi sử dụng, Những phần khai báo `use` PHẢI đặt phái sau khai báo `namespace`


PHẢI có 1 từ khóa `use` với mỗi khai báo


PHẢI có 1 dòng trống phía sau đoạn code `use`

 Ví dụ:

```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

// ... additional PHP code ...

```


4. Classes, Properties, and Methods *Lớp, thuộc tính, và phương pháp*
-----------------------------------


Khái niệm "class" ám chỉ tất cả các classes, interfaces,và traits.

### 4.1. Extends and Implements


Từ khóa `extends` và `implements` PHẢI khai báo cùng dòng với tên class


Khi mở ngoặc nhọn phải viết ở dòng mới phía sau phần body

```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements \ArrayAccess, \Countable
{
    // constants, properties, methods
}
```


Danh sách `implements` CÓ THỂ được chia thành nhiều dòng, trong đó mỗi dòng sẽ indented *căn lề* 1 lần
Khi đó thành phần đầu tiên PHẢI viết ở dòng mới và mỗi dùng chỉ được có 1 interface

```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements
    \ArrayAccess,
    \Countable,
    \Serializable
{
    // constants, properties, methods
}
```

### 4.2. Properties *Thuộc tính*


Visibility PHẢI được khai báo ở mọi thuộc tính


PHẢI KHÔNG sử dụng `var` để khái báo 1 thuộc tính.


KHÔNG được khai báo quá 1 thuộc tính mỗi câu

Tên thuộc tính KHÔNG NÊN được prefixed bởi dấu gạch dưới _ để biểu thị tính protected hay private


Khai báo 1 thuôc tính được viết như sau:

```php
<?php
namespace Vendor\Package;

class ClassName
{
    public $foo = null;
}
```

### 4.3. Methods *Phương pháp*


Visibility PHẢI được khai báo ở mọi methods


Tên của Method KHÔNG NÊN được prefixed  bởi dấu gạch dưới để biểu thị tính protected hay private


Tên của Method PHẢI KHÔNG được có dấu cách phía sau tên method.
Khi mở ngoặc nhọn PHẢI ở 1 dòng riêng, và khi đóng ngoặc PHẢI ở dòng mới phía dưới phần body của method.
PHẢI KHÔNG có dấu cách phía sau khi mở ngoặc tròn, và PHẢI KHÔNG có dấu cách phía trước khi đóng ngoặc tròn


Khai báo 1 Method được viết như sau. Chú ý vị trí của dấu ngoặc tròn, dấu phẩy, dấu cách, và ngoặc nhọn:

```php
<?php
namespace Vendor\Package;

class ClassName
{
    public function fooBarBaz($arg1, &$arg2, $arg3 = [])
    {
        // method body
    }
}
```    

### 4.4. Method Arguments


Trong danh sách các argument*đối số* PHẢI KHÔNG được có dấu cách trước mỗi dấu phẩy, và PHẢI có 1 dấu cách phía sau mỗi dấu phẩy


Những Method Arguments có giá trị mặc định PHẢI đặt ở cuối danh sách argument*đối số*

```php
<?php
namespace Vendor\Package;

class ClassName
{
    public function foo($arg1, &$arg2, $arg3 = [])
    {
        // method body
    }
}
```


Danh sách Argument*đối số* CÓ THỂ chia thành nhiều dòng, trong đó mỗi dòng sẽ được indented*căn lề* 1 lần
Khi đó, thành phần đâu tiên PHẢI đặt ở dòng mới, và chỉ được có 1 argument*đối số* mỗi dòng


Khi chia danh sách argument*đối số* thành các dòng, dấu đóng ngoặc tròn và dấu mở ngoặc nhọn PHẢI được đặt cùng 1 dòng với 1 dấu cách ở giữa

```php
<?php
namespace Vendor\Package;

class ClassName
{
    public function aVeryLongMethodName(
        ClassTypeHint $arg1,
        &$arg2,
        array $arg3 = []
    ) {
        // method body
    }
}
```

### 4.5. `abstract`, `final`, and `static`


Khai sử dụng, Phần khai báo `abstract` và `final` PHẢI được đặt trước khai báo visibility


Khi sử dụng, Phần khai báo `static` PHẢI được đặt sau khai báo visibility

```php
<?php
namespace Vendor\Package;

abstract class ClassName
{
    protected static $foo;

    abstract protected function zim();

    final public static function bar()
    {
        // method body
    }
}
```

### 4.6. Method and Function Calls - Gọi Method và Function


Khi gọi 1 method hoặc function, PHẢI KHÔNG có dấu cách giữa tên của method hoặc function và dấu mở ngoặc tròn, PHẢI KHÔNG có dấu cách phía sau dấu mở ngoặc tròn, và PHẢI KHÔNG có dấu cách trước dấu đóng ngoặc tròn.
Trong dánh sách các argument*đối số*, PHẢI KHÔNG có dấu dấu phía trước mỗi dấu phẩy, và PHẢI có dấu cách phía sau dấu phẩy

```php
<?php
bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);
```


Danh sách các Argument*đối số* CÓ THỂ chia thành các dòng, mỗi dòng sẽ được indented*căn lề* 1 lần.Thành phần đầu tiên trong danh sách PHẢI viết ở dòng mới, Mỗi dòng chỉ dược chứa 1 argument*đối số*

```php
<?php
$foo->bar(
    $longArgument,
    $longerArgument,
    $muchLongerArgument
);
```

5. Control Structures
---------------------


Các quy tắc chung khi dùng ontrol structures gồm:


- PHẢI có 1 dấu cách sau control structure keyword

- PHẢI KHÔNG có dấu cách sau dấu mở ngoặc tròn

- PHẢI KHÔNG có dấu cách trước dấu đóng ngoặc tròn

- PHẢI có 1 dấu cách giữa dấu đóng ngoặc tròn và dấu mở ngoặc nhọn

- Phần body của structure PHẢI được indented*căn lề* 1 lần 

- Dấu đóng ngoặc nhọn PHẢI ở dòng mới phía sau phần body


Phần body của mỗi structure PHẢI đặt trong dấu ngoặc nhọn.Điều này tiêu chuẩn hóa cách viết structures và giảm thiệu phát sinh lỗi khi dòng mới được thêm vào phần thân



### 5.1. `if`, `elseif`, `else`


Một cấu trúc `if` được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn;`else` and `elseif` được đặt cùng dòng với dấu đóng ngoặc nhọn của phần body phía trước

```php
<?php
if ($expr1) {
    // if body
} elseif ($expr2) {
    // elseif body
} else {
    // else body;
}
```

Từ khóa `else` and `elseif` NÊN đươc sử dụng để thay thế `else if`như vậy mọi từ khóa control đều thành 1 từ đơn

### 5.2. `switch`, `case`


Một cấu trúc`switch`được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn.
Phần `case` PHẢI được indented*căn lề* 1 lần so với `switch`,và từ khóa `break`(hay các từ khóa ngắt khác) PHẢI indented*căn lề* bằng với phần thân của `case`. PHẢI có 1 comment như `// no break` khi phần thân của `case` không trống và được có tình bỏ qua


```php
<?php
switch ($expr) {
    case 0:
        echo 'First case, with a break';
        break;
    case 1:
        echo 'Second case, which falls through';
        // no break
    case 2:
    case 3:
    case 4:
        echo 'Third case, return instead of break';
        return;
    default:
        echo 'Default case';
        break;
}
```


### 5.3. `while`, `do while`


Một câu lệnh `while`được viết như sau. Chú ý vị trsi của các dấu ngoặc tròn, dấu cách, và dấu ngoặc nhọn

```php
<?php
while ($expr) {
    // structure body
}
```


Tương tự như vậy,một câu lệnh `do while` được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn

```php
<?php
do {
    // structure body;
} while ($expr);
```

### 5.4. `for`


Một câu lệnh `for` có được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn

```php
<?php
for ($i = 0; $i < 10; $i++) {
    // for body
}
```

### 5.5. `foreach`
    

Một câu lệnh `foreach` có được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn

```php
<?php
foreach ($iterable as $key => $value) {
    // foreach body
}
```

### 5.6. `try`, `catch`


Một khối `try catch` được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn

```php
<?php
try {
    // try body
} catch (FirstExceptionType $e) {
    // catch body
} catch (OtherExceptionType $e) {
    // catch body
}
```

6. Closures
-----------



Closures PHẢI được khai báo với 1 dấu cách phía sau từ khóa `function`, và 1 dấu cách phía trước và sau từ khóa `use`


Dấu mở ngoặc nhọn PHẢI viết cùng dòng, và dấu đóng ngoặc nhọn PHẢI ở dòng mới phía sau phần body


PHẢI KHÔNG có dấu cách sau dấu mở ngoặc tròn của danh sách argument*đối số* hoặc danh sách variable*biến số*, và PHẢI KHÔNG có dấu cách phía trước dấu đóng ngoặc tròn của danh sách argumen*đối số*t hoặc danh sách variable*biến số*


Trong danh sách argument*đối số* và danh sách variable*biến só*, PHẢI KHÔNG có dấu cách trước mỗi dấu phẩy, và PHẢI có 1 dấu cách sau mỗi dấu phẩy.


Các  closure arguments*đối số* có giá trị mặc định PHẢI đặt ở cuối danh sách argument*đối số*


Khai báo 1 closure được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn

```php
<?php
$closureWithArgs = function ($arg1, $arg2) {
    // body
};

$closureWithArgsAndVars = function ($arg1, $arg2) use ($var1, $var2) {
    // body
};
```


Danh sách Argument*đối số* và danh sách variable*biến số* CÓ THỂ được chia thành nhiều dòng, mỗi dòng sẽ được indented* căn lề* 1 lần. Thành phần đầu tiên trong danh sách PHẢI được viết ở dòng mới, và mỗi dòng chỉ được có 1 argument*đối số* hoặc variable*biến số*


Khi đoạn cuối của danh sách (kể cả arguments*đối số* hay variables*biến số* ) được chia thành nhiều dòng, các dấu đóng ngoặc tròn và mở ngoặc nhọn PHẢI được đặt cùng dòng với 1 dấu cách đặt ở giữa


Ví dụ dưới đây về các closures và danh sách *without argument* và danh sách variable*biến số* được chia thành nhiều dòng

```php
<?php
$longArgs_noVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) {
   // body
};

$noArgs_longVars = function () use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
   // body
};

$longArgs_longVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
   // body
};

$longArgs_shortVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use ($var1) {
   // body
};

$shortArgs_longVars = function ($arg) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
   // body
};
```


Chú ý các quy định định dạng cũng áp dụng khi closure được sử dụng trực tiếp trong 1 function hay method call như 1 argument*đối số*

```php
<?php
$foo->bar(
    $arg1,
    function ($arg2) use ($var1) {
        // body
    },
    $arg3
);
```


7.Lời kết
--------------


Có rất nhiêt yếu tố về style và practice bị bỏ qua trong hướng dẫn này.Ví dụ như:



- Khai báo biến global và hằng global


- Khai báo hàm

- Operators and assignment


- Inter-line alignment



- Comments và khối documentation


- Tiền tố và hậu tố trong tên Class

- Best practices



Các kiến nghị trong tương lai CÓ THỂ sửa đổi và mở rộng hướng dẫn này để đề cập đến các yếu tố khác về style và practice.

Appendix A. Survey
------------------


Khi viết hướng dẫn này, nhóm đã khảo sát các thành viên để xác định các thông lệ chung. 


### A.1.Dữ liệu khảo sát

    url,http://www.horde.org/apps/horde/docs/CODING_STANDARDS,http://pear.php.net/manual/en/standards.php,http://solarphp.com/manual/appendix-standards.style,http://framework.zend.com/manual/en/coding-standard.html,http://symfony.com/doc/2.0/contributing/code/standards.html,http://www.ppi.io/docs/coding-standards.html,https://github.com/ezsystems/ezp-next/wiki/codingstandards,http://book.cakephp.org/2.0/en/contributing/cakephp-coding-conventions.html,https://github.com/UnionOfRAD/lithium/wiki/Spec%3A-Coding,http://drupal.org/coding-standards,http://code.google.com/p/sabredav/,http://area51.phpbb.com/docs/31x/coding-guidelines.html,https://docs.google.com/a/zikula.org/document/edit?authkey=CPCU0Us&hgd=1&id=1fcqb93Sn-hR9c0mkN6m_tyWnmEvoswKBtSc0tKkZmJA,http://www.chisimba.com,n/a,https://github.com/Respect/project-info/blob/master/coding-standards-sample.php,n/a,Object Calisthenics for PHP,http://doc.nette.org/en/coding-standard,http://flow3.typo3.org,https://github.com/propelorm/Propel2/wiki/Coding-Standards,http://developer.joomla.org/coding-standards.html
    voting,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,no,no,no,?,yes,no,yes
    indent_type,4,4,4,4,4,tab,4,tab,tab,2,4,tab,4,4,4,4,4,4,tab,tab,4,tab
    line_length_limit_soft,75,75,75,75,no,85,120,120,80,80,80,no,100,80,80,?,?,120,80,120,no,150
    line_length_limit_hard,85,85,85,85,no,no,no,no,100,?,no,no,no,100,100,?,120,120,no,no,no,no
    class_names,studly,studly,studly,studly,studly,studly,studly,studly,studly,studly,studly,lower_under,studly,lower,studly,studly,studly,studly,?,studly,studly,studly
    class_brace_line,next,next,next,next,next,same,next,same,same,same,same,next,next,next,next,next,next,next,next,same,next,next
    constant_names,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper
    true_false_null,lower,lower,lower,lower,lower,lower,lower,lower,lower,upper,lower,lower,lower,upper,lower,lower,lower,lower,lower,upper,lower,lower
    method_names,camel,camel,camel,camel,camel,camel,camel,camel,camel,camel,camel,lower_under,camel,camel,camel,camel,camel,camel,camel,camel,camel,camel
    method_brace_line,next,next,next,next,next,same,next,same,same,same,same,next,next,same,next,next,next,next,next,same,next,next
    control_brace_line,same,same,same,same,same,same,next,same,same,same,same,next,same,same,next,same,same,same,same,same,same,next
    control_space_after,yes,yes,yes,yes,yes,no,yes,yes,yes,yes,no,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes
    always_use_control_braces,yes,yes,yes,yes,yes,yes,no,yes,yes,yes,no,yes,yes,yes,yes,no,yes,yes,yes,yes,yes,yes
    else_elseif_line,same,same,same,same,same,same,next,same,same,next,same,next,same,next,next,same,same,same,same,same,same,next
    case_break_indent_from_switch,0/1,0/1,0/1,1/2,1/2,1/2,1/2,1/1,1/1,1/2,1/2,1/1,1/2,1/2,1/2,1/2,1/2,1/2,0/1,1/1,1/2,1/2
    function_space_after,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no
    closing_php_tag_required,no,no,no,no,no,no,no,no,yes,no,no,no,no,yes,no,no,no,no,no,yes,no,no
    line_endings,LF,LF,LF,LF,LF,LF,LF,LF,?,LF,?,LF,LF,LF,LF,?,,LF,?,LF,LF,LF
    static_or_visibility_first,static,?,static,either,either,either,visibility,visibility,visibility,either,static,either,?,visibility,?,?,either,either,visibility,visibility,static,?
    control_space_parens,no,no,no,no,no,no,yes,no,no,no,no,no,no,yes,?,no,no,no,no,no,no,no
    blank_line_after_php,no,no,no,no,yes,no,no,no,no,yes,yes,no,no,yes,?,yes,yes,no,yes,no,yes,no
    class_method_control_brace,next/next/same,next/next/same,next/next/same,next/next/same,next/next/same,same/same/same,next/next/next,same/same/same,same/same/same,same/same/same,same/same/same,next/next/next,next/next/same,next/same/same,next/next/next,next/next/same,next/next/same,next/next/same,next/next/same,same/same/same,next/next/same,next/next/next

### A.2. Ghi chú khảo sát

`indent_type`:
The type of indenting. `tab` = "Use a tab", `2` or `4` = "number of spaces"
Các loại indenting*căn lề* `tab` = "dùng nút tab" , `2` or `4` = "số dấu cách"
`line_length_limit_soft`:
The "soft" line length limit, in characters. `?` = not discernible or no response, `no` means no limit.
độ dài các ký tự soft limit trong 1 dòng `?` = không rõ hoặc không phản hồi, `no`nghĩa là không giới hạn.

`line_length_limit_hard`:
The "hard" line length limit, in characters. `?` = not discernible or no response, `no` means no limit.
độ dài các ký tự hard limit trong 1 dòng. `?` = không rõ hoặc không phản hồi, `no`nghĩa là không giới hạn.

`class_names`:
How classes are named. `lower` = lowercase only, `lower_under` = lowercase with underscore separators, `studly` = StudlyCase.
Cách đặt tên classes. `lower` = chỉ chữ thường, `lower_under` = chữ thường với gạch dưới, `studly` = StudlyCase.

`class_brace_line`:
Does the opening brace for a class go on the `same` line as the class keyword, or on the `next` line after it?
Dấu mở ngoặc nhọn của 1 class viết `cùng dòng` với từ khóa class, hoặc viết ở `dòng mới` sau nó

`constant_names`:
How are class constants named? `upper` = Uppercase with underscore separators.
Cách đặt tên class constants?  `upper` = chữ hoa với gạch dưới.

`true_false_null`:
Are the `true`, `false`, and `null` keywords spelled as all `lower` case, or all `upper` case?
Từ khó `true`, `false`, và `null` viết `thường` tất hay viết `hoa` tất

`method_names`:
How are methods named? `camel` = `camelCase`, `lower_under` = lowercase with underscore separators.
Cách đặt tên methods?  `camel` = `camelCase`, `lower_under` = viết thường với gạch dưới.

`method_brace_line`:
Does the opening brace for a method go on the `same` line as the method name, or on the `next` line?
Dấu mở ngoặc nhọn của 1 moethod viết `cùng dòng` với tên method hay viết ở `dòng mới`

`control_brace_line`:
Does the opening brace for a control structure go on the `same` line, or on the `next` line?
Dấu mở ngoặc nhọn của control structure viết `cùng dòng` hay viết ở `dòng mới`

`control_space_after`:
Is there a space after the control structure keyword?
Có dấu cách phía sau từ khóa control structure?

`always_use_control_braces`:
Do control structures always use braces?
Có luôn luôn dùng dấu ngoặc nhọn cho control structures?

`else_elseif_line`:
When using `else` or `elseif`, does it go on the `same` line as the previous closing brace, or does it go on the `next` line?
Khi sử dụng `else` hay `elseif`, viết nó `cùng dòng` với dấu đóng ngoặc nhọn trước trước, hay biết nó ở `dòng mới`

`case_break_indent_from_switch`:
How many times are `case` and `break` indented from an opening `switch` statement?
indented*căn lề*  `case` và `break` mấy lần từ câu lệnh mở đâu `switch`?

`function_space_after`:
Do function calls have a space after the function name and before the opening parenthesis?
function calls có dấu cách sau tên functionvà trước dấu mở ngoặc tròn không?

`closing_php_tag_required`:
In files containing only PHP, is the closing `?>` tag required?
Trong các file chỉ chứ PHP thẻ đóng `?>` có cần thiết không?

`line_endings`:
What type of line ending is used?
Dùng dạng gì của line ending?

`static_or_visibility_first`:
When declaring a method, does `static` come first, or does the visibility come first?
Khi khái báo 1 method, viết  `static` hay visibility trước

`control_space_parens`:
In a control structure expression, is there a space after the opening parenthesis and a space before the closing parenthesis? `yes` = `if ( $expr )`, `no` = `if ($expr)`.
Trong 1 biểu thức control structure, có dùng dấu cách sau dấu mở ngoặc tròn và dấu cách trước dấu đóng ngoặc tròn không?
`có` = `if ( $expr )`, `không` = `if ($expr)`.

`blank_line_after_php`:
Is there a blank line after the opening PHP tag?
Có dòng trống sau thẻ opening PHP không?

`class_method_control_brace`:
A summary of what line the opening braces go on for classes, methods, and control structures.
Một bản tóm tắt vể dấu mở ngoặc nhọn cho các classes, methods, và control structures.

### A.3. Kết quả khảo sát

    indent_type:
        tab: 7
        2: 1
        4: 14
    line_length_limit_soft:
        ?: 2
        no: 3
        75: 4
        80: 6
        85: 1
        100: 1
        120: 4
        150: 1
    line_length_limit_hard:
        ?: 2
        no: 11
        85: 4
        100: 3
        120: 2
    class_names:
        ?: 1
        lower: 1
        lower_under: 1
        studly: 19
    class_brace_line:
        next: 16
        same: 6
    constant_names:
        upper: 22
    true_false_null:
        lower: 19
        upper: 3
    method_names:
        camel: 21
        lower_under: 1
    method_brace_line:
        next: 15
        same: 7
    control_brace_line:
        next: 4
        same: 18
    control_space_after:
        no: 2
        yes: 20
    always_use_control_braces:
        no: 3
        yes: 19
    else_elseif_line:
        next: 6
        same: 16
    case_break_indent_from_switch:
        0/1: 4
        1/1: 4
        1/2: 14
    function_space_after:
        no: 22
    closing_php_tag_required:
        no: 19
        yes: 3
    line_endings:
        ?: 5
        LF: 17
    static_or_visibility_first:
        ?: 5
        either: 7
        static: 4
        visibility: 6
    control_space_parens:
        ?: 1
        no: 19
        yes: 2
    blank_line_after_php:
        ?: 1
        no: 13
        yes: 8
    class_method_control_brace:
        next/next/next: 4
        next/next/same: 11
        next/same/same: 1
        same/same/same: 6
