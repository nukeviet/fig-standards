Hướng dẫn về Coding Style - Coding Style Guide
==================

This guide extends and expands on [PSR-1], the basic coding standard.
Hướng dẫn này được dựa trên và phát triển từ [PSR-1], các tiêu chuẩn coding cơ bản

The intent of this guide is to reduce cognitive friction when scanning code
from different authors. It does so by enumerating a shared set of rules and
expectations about how to format PHP code.
Mục đích của hướng dẫn này là để giảm sự khó khăn khi đọc code của những người khác, bằng cách đặt ra các tiêu chuẩn chung hay gợi ý về việc format PHP code

The style rules herein are derived from commonalities among the various member
projects. When various authors collaborate across multiple projects, it helps
to have one set of guidelines to be used among all those projects. Thus, the
benefit of this guide is not in the rules themselves, but in the sharing of
those rules.
Các tiêu chuẩn về style ở đây đều được bắt nguồn từ sự giống nhau giữa các project khác nhau.Khi mọi người hợp tác với nhau trong cùng 1 project, những tiêu chuẩn này sẽ là bộ tiêu chuẩn chung được dùng trong toàn bộ project đó.Vì vậy lợi ích đạt được không chỉ ở những tiêu chuẩn này mà còn ở việc chia sẻ những tiêu chuẩn này

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be
interpreted as described in [RFC 2119].
Những từ "MUST" *PHẢI*, "MUST NOT"*PHẢI KHÔNG...*, "REQUIRED", "SHALL", "SHALL NOT", "SHOULD"*NÊN*,
"SHOULD NOT"*KHÔNG NÊN*, "RECOMMENDED", "MAY"*CÓ THỂ*, và "OPTIONAL" trong tài liệu này cần được hiểu như trong mô tả ở [RFC 2119].

[RFC 2119]: http://www.ietf.org/rfc/rfc2119.txt
[PSR-0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md
[PSR-1]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md


1. Overview Khái Quát
-----------

- Code MUST follow a "coding style guide" PSR [[PSR-1]].
- Code PHẢI tuân theo "coding style guide" PRS [[PSR-1]]

- Code MUST use 4 spaces for indenting, not tabs.
- Code không dùng tab mà PHẢI dùng 4 dấu cách để indenting*lùi đầu dòng*

- There MUST NOT be a hard limit on line length; the soft limit MUST be 120
  characters; lines SHOULD be 80 characters or less.
- KHÔNG có hard limit về độ dài của 1 dòng; soft limit PHẢI là 120 ký tự; 1 dòng NÊN từ 80 ký tự trở xuống

- There MUST be one blank line after the `namespace` declaration, and there
  MUST be one blank line after the block of `use` declarations.
- PHẢI có 1 dòng trống sau phần khai báo `namespace`, và PHẢI có 1 dòng trống sau phần khái báo `use`

- Opening braces for classes MUST go on the next line, and closing braces MUST
  go on the next line after the body.
- Dấu mở ngoặc nhọn khi khai báo class PHẢI viết ở dòng mới* xuống dòng* và khi đóng ngoặc PHẢI viết ở dòng mới sau phần body

- Opening braces for methods MUST go on the next line, and closing braces MUST
  go on the next line after the body.
- Dấu ngoặc nhọn khi khai khai báo methods PHẢI viết ở dòng mới* xuống dòng* và khi khi đóng ngoặc phải viết ở dòng mới sau phần body

- Visibility MUST be declared on all properties and methods; `abstract` and
  `final` MUST be declared before the visibility; `static` MUST be declared
  after the visibility.
- Visibility *public protect private* PHẢI được khai báo trong các properties và methods; `abstract` và `final` PHẢI được khai báo phía trước visibility; `static` PHẢI khai báo phái sau visibility
  
- Control structure keywords MUST have one space after them; method and
  function calls MUST NOT.
- Phía sau của Control structure keywords*if else for* PHẢI có dấu cách

- Opening braces for control structures MUST go on the same line, and closing
  braces MUST go on the next line after the body.
- Dấu mở ngoặc nhọn của control structures PHẢI viết cùng dòng và khi đóng ngoặc phải viết ở dòng mới sau phần body

- Opening parentheses for control structures MUST NOT have a space after them,
  and closing parentheses for control structures MUST NOT have a space before.
- Dấu mở ngoặc đơn của control structures PHẢI KHÔNG có dấu cách phía sau và cả khi đóng ngoặc cũng PHẢI KHÔNG có dấu cách phía trước

### 1.1. Example Ví dụ

This example encompasses some of the rules below as a quick overview:
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

2. General Tổng thể
----------

### 2.1 Basic Coding Standard Tiêu chuẩn cơ bản của Coding

Code MUST follow all rules outlined in [PSR-1].
Code PHẢI tuân theo tất cả các quy tắc được nêu ra trong phần [PSR-1].

### 2.2 Files Các Tập tin

All PHP files MUST use the Unix LF (linefeed) line ending.
Tất cả các tập tin PHP PHẢI sử dụng Unix LF (linefeed) line ending.

All PHP files MUST end with a single blank line.
Tất cả các tập tin PHP PHẢI kết thúc bằng 1 dòng trống

The closing `?>` tag MUST be omitted from files containing only PHP.
Trong tập tin chỉ chứa PHP thì KHÔNG PHẢI viết thẻ đóng `?>`

### 2.3. Lines Dòng

There MUST NOT be a hard limit on line length.
KHÔNG có hard limit về độ dài của 1 dòng

The soft limit on line length MUST be 120 characters; automated style checkers
MUST warn but MUST NOT error at the soft limit.
Soft limit độ dài của 1 dòng phải là 120 ký tự; automated style checkers PHẢI cảnh báo nhưng sẽ không báo lỗi khi vượt qua soft limit

Lines SHOULD NOT be longer than 80 characters; lines longer than that SHOULD
be split into multiple subsequent lines of no more than 80 characters each.
1 Dòng Không nên dài hơn 80 ký tự; Nếu dài hơn 80 ký tự thì dòng đó NÊN được chia thành nhiều dòng và mỗi dòng không nhiều hơn 80 ký tự

There MUST NOT be trailing whitespace at the end of non-blank lines.
Dòng không trống *non-blank lines* PHẢI KHÔNG có trailing whitespace*dấu cách cuối dòng* ở cuối

Blank lines MAY be added to improve readability and to indicate related
blocks of code.
Dòng trống CÓ THỂ được thêm vào để dễ đọc hơn và cho thấy mối quan hệ của các khối lệnh

There MUST NOT be more than one statement per line.
Mỗi dòng PHẢI KHÔNG quá 1 statement.

### 2.4. Indenting Căn lề

Code MUST use an indent of 4 spaces, and MUST NOT use tabs for indenting.
Code Phải dùng 4 dấu cách chứ KHÔNG PHẢI dùng tabs để căn lề

> N.b.: Using only spaces, and not mixing spaces with tabs, helps to avoid
> problems with diffs, patches, history, and annotations. The use of spaces
> also makes it easy to insert fine-grained sub-indentation for inter-line 
> alignment.
> N.b.: Chỉ sử dụng dấu cách và không trộn dấu cách và tabs, giúp tránh được các vấn đề với diffs, patches, history, and annotations.
> Khi sử dụng dấu cách cũng khiến việc chèn fine-grained sub-indentation vào giữa các dòng

### 2.5. Keywords and True/False/Null Từ Khóa và True/False/Null

PHP [keywords] MUST be in lower case.
Các [keywords] PHP PHẢI viết thường
The PHP constants `true`, `false`, and `null` MUST be in lower case.
Các Hằng số PHP `true`, `false`, và `null` PHẢI viết thường
[keywords]: http://php.net/manual/en/reserved.keywords.php



3. Namespace and Use Declarations Khai báo  Namespace và Use
---------------------------------

When present, there MUST be one blank line after the `namespace` declaration.
Khi sử dụng PHẢI có 1 dòng trắng phía sau khai báo `namespace`
When present, all `use` declarations MUST go after the `namespace`
declaration.
Khi sử dụng, Những phần khai báo `use` PHẢI đặt phái sau khai báo `namespace`

There MUST be one `use` keyword per declaration.
PHẢI có 1 từ khóa `use` với mỗi khai báo

There MUST be one blank line after the `use` block.
PHẢI có 1 dòng trống phía sau đoạn code `use`

For example: Ví dụ:

```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

// ... additional PHP code ...

```


4. Classes, Properties, and Methods
-----------------------------------

The term "class" refers to all classes, interfaces, and traits.
Khái niệm "class" ám chỉ tất cả các classes, interfaces,và traits.

### 4.1. Extends and Implements

The `extends` and `implements` keywords MUST be declared on the same line as
the class name.
Từ khóa `extends` và `implements` PHẢI khai báo cùng dòng với tên class

The opening brace for the class MUST go on its own line; the closing brace
for the class MUST go on the next line after the body.
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

Lists of `implements` MAY be split across multiple lines, where each
subsequent line is indented once. When doing so, the first item in the list
MUST be on the next line, and there MUST be only one interface per line.
Danh sách `implements` CÓ THỂ được chia thành nhiều dòng, trong đó mỗi dòng sẽ indented*căn lề* 1 lần
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

### 4.2. Properties Thuộc tính

Visibility MUST be declared on all properties.
Visibility PHẢI được khai báo ở mọi thuộc tính

The `var` keyword MUST NOT be used to declare a property.
PHẢI KHÔNG sử dụng `var` để khái báo 1 thuộc tính.

There MUST NOT be more than one property declared per statement.
KHÔNG được khai báo quá 1 thuộc tính mỗi câu
Property names SHOULD NOT be prefixed with a single underscore to indicate
protected or private visibility.
Tên thuộc tính KHÔNG NÊN được prefixed bởi dấu gạch dưới _ để biểu thị tính protected hay private

A property declaration looks like the following.
Khai báo 1 thuôc tính được viết như sau:

```php
<?php
namespace Vendor\Package;

class ClassName
{
    public $foo = null;
}
```

### 4.3. Methods

Visibility MUST be declared on all methods.
Visibility PHẢI được khai báo ở mọi methods

Method names SHOULD NOT be prefixed with a single underscore to indicate
protected or private visibility.
Tên của Method KHÔNG NÊN được prefixed bởi dấu gạch dưới để biểu thị tính protected hay private

Method names MUST NOT be declared with a space after the method name. The
opening brace MUST go on its own line, and the closing brace MUST go on the
next line following the body. There MUST NOT be a space after the opening
parenthesis, and there MUST NOT be a space before the closing parenthesis.
Tên của Method PHẢI KHÔNG được có dấu cách phía sau tên method.
Khi mở ngoặc nhọn PHẢI ở 1 dòng riêng, và khi đóng ngoặc PHẢI ở dòng mới phía dưới phần body của method.
PHẢI KHÔNG có dấu cách phía sau khi mở ngoặc tròn, và PHẢI KHÔNG có dấu cách phía trước khi đóng ngoặc tròn

A method declaration looks like the following. Note the placement of
parentheses, commas, spaces, and braces:
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

In the argument list, there MUST NOT be a space before each comma, and there
MUST be one space after each comma.
Trong danh sách các argument*đối số* PHẢI KHÔNG được có dấu cách trước mỗi dấu phẩy, và PHẢI có 1 dấu cách phía sau mỗi dấu phẩy

Method arguments with default values MUST go at the end of the argument
list.
Những Method Arguments có giá trị mặc định PHẢI đặt ở cuối danh sách argument

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

Argument lists MAY be split across multiple lines, where each subsequent line
is indented once. When doing so, the first item in the list MUST be on the
next line, and there MUST be only one argument per line.
Danh sách Argument CÓ THỂ chia thành nhiều dòng, trong đó mỗi dòng sẽ được indented*căn lề* 1 lần
Khi đó, thành phần đâu tiên PHẢI đặt ở dòng mới, và chỉ được có 1 argument mỗi dòng

When the argument list is split across multiple lines, the closing parenthesis
and opening brace MUST be placed together on their own line with one space
between them.
Khi chia danh sách argument thành các dòng, dấu đóng ngoặc tròn và dấu mở ngoặc nhọn PHẢI được đặt cùng 1 dòng với 1 dấu cách ở giữa

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

When present, the `abstract` and `final` declarations MUST precede the
visibility declaration.
Khai sử dụng, Phần khai báo `abstract` và `final` PHẢI được đặt trước khai báo visibility

When present, the `static` declaration MUST come after the visibility
declaration.
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

When making a method or function call, there MUST NOT be a space between the
method or function name and the opening parenthesis, there MUST NOT be a space
after the opening parenthesis, and there MUST NOT be a space before the
closing parenthesis. In the argument list, there MUST NOT be a space before
each comma, and there MUST be one space after each comma.
Khi gọi 1 method hoặc function, PHẢI KHÔNG có dấu cách giữa tên của method hoặc function và dấu mở ngoặc tròn, PHẢI KHÔNG có dấu cách phía sau dấu mở ngoặc tròn, và PHẢI KHÔNG có dấu cách trước dấu đóng ngoặc tròn.
Trong dánh sách các argument, PHẢI KHÔNG có dấu dấu phía trước mỗi dấu phẩy, và PHẢI có dấu cách phía sau dấu phẩy

```php
<?php
bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);
```

Argument lists MAY be split across multiple lines, where each subsequent line
is indented once. When doing so, the first item in the list MUST be on the
next line, and there MUST be only one argument per line.
Danh sách các Argument CÓ THỂ chia thành các dòng, mỗi dòng sẽ được indented*căn lề* 1 lần.Thành phần đầu tiên trong danh sách PHẢI viết ở dòng mới, Mỗi dòng chỉ dược chứa 1 argument

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

The general style rules for control structures are as follows:
Các quy tắc chung khi dùng ontrol structures gồm:

- There MUST be one space after the control structure keyword
- PHẢI có 1 dấu cách sau control structure keyword
- There MUST NOT be a space after the opening parenthesis
- PHẢI KHÔNG có dấu cách sau dấu mở ngoặc tròn
- There MUST NOT be a space before the closing parenthesis
- PHẢI KHÔNG có dấu cách trước dấu đóng ngoặc tròn
- There MUST be one space between the closing parenthesis and the opening
  brace
PHẢI có 1 dấu cách giữa dấu đóng ngoặc tròn và dấu mở ngoặc nhọn
- The structure body MUST be indented once
- Phàn body của structure PHẢI được indented*căn lề* 1 lần 
- The closing brace MUST be on the next line after the body
- Dấu đóng ngoặc nhọn PHẢI ở dòng mới phía sau phần body

The body of each structure MUST be enclosed by braces. This standardizes how
the structures look, and reduces the likelihood of introducing errors as new
lines get added to the body.
Phần body của mỗi structure PHẢI đặt trong dấu ngoặc nhọn.Điều này tiêu chuẩn hóa cách viết structures và giảm thiệu phát sinh lỗi khi dòng mới được thêm vào phần thân



### 5.1. `if`, `elseif`, `else`

An `if` structure looks like the following. Note the placement of parentheses,
spaces, and braces; and that `else` and `elseif` are on the same line as the
closing brace from the earlier body.
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

The keyword`else` and `elseif` SHOULD be used instead of `else if` so that all control
keywords look like single words.
Từ khóa `else` and `elseif` NÊN đươc sử dụng để thay thế `else if`như vậy mọi từ khóa control đều thành 1 từ đơn

### 5.2. `switch`, `case`

A `switch` structure looks like the following. Note the placement of
parentheses, spaces, and braces. The `case` statement MUST be indented once
from `switch`, and the `break` keyword (or other terminating keyword) MUST be
indented at the same level as the `case` body. There MUST be a comment such as
`// no break` when fall-through is intentional in a non-empty `case` body.
Một cấu trúc`switch`được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn.
Phần `case` PHẢI được indented*căn lề* 1 lần so với `switch`,và từ khóa `break`(hay các từ khóa ngắt khác) PHẢI indented*căn lề* bằng với phần thân của `case`. PHẢI có 1 comment như `// no break` khi phần thân của `case` không trống và được có tình bỏ qua*fall-through is intentional in a non-empty*


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

A `while` statement looks like the following. Note the placement of
parentheses, spaces, and braces.
Một câu lệnh `while`được viết như sau. Chú ý vị trsi của các dấu ngoặc tròn, dấu cách, và dấu ngoặc nhọn

```php
<?php
while ($expr) {
    // structure body
}
```

Similarly, a `do while` statement looks like the following. Note the placement
of parentheses, spaces, and braces.
Tương tự như vậy,một câu lệnh `do while` được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn

```php
<?php
do {
    // structure body;
} while ($expr);
```

### 5.4. `for`

A `for` statement looks like the following. Note the placement of parentheses,
spaces, and braces.
Một câu lệnh `for` có được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn

```php
<?php
for ($i = 0; $i < 10; $i++) {
    // for body
}
```

### 5.5. `foreach`
    
A `foreach` statement looks like the following. Note the placement of
parentheses, spaces, and braces.
Một câu lệnh `foreach` có được viết như sau. Chú ý vị trí của các dấu ngoặc tròn, dấu cách, dấu ngoặc nhọn

```php
<?php
foreach ($iterable as $key => $value) {
    // foreach body
}
```

### 5.6. `try`, `catch`

A `try catch` block looks like the following. Note the placement of
parentheses, spaces, and braces.
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
*argument=đói số*
*variable=biến số*

Closures MUST be declared with a space after the `function` keyword, and a
space before and after the `use` keyword.
Closures PHẢI được khai báo với 1 dấu cách phía sau từ khóa `function`, và 1 dấu cách phía trước và sau từ khóa `use`

The opening brace MUST go on the same line, and the closing brace MUST go on
the next line following the body.
Dấu mở ngoặc nhọn PHẢI viết cùng dòng, và dấu đóng ngoặc nhọn PHẢI ở dòng mới phía sau phần body

There MUST NOT be a space after the opening parenthesis of the argument list
or variable list, and there MUST NOT be a space before the closing parenthesis
of the argument list or variable list.
PHẢI KHÔNG có dấu cách sau dấu mở ngoặc tròn của danh sách argument hoặc danh sách variable, và PHẢI KHÔNG có dấu cách phía trước dấu đóng ngoặc tròn của danh sách argument hoặc danh sách variable

In the argument list and variable list, there MUST NOT be a space before each
comma, and there MUST be one space after each comma.
Trong danh sách argument và danh sách variable, PHẢI KHÔNG có dấu cách trước mỗi dấu phẩy, và PHẢI có 1 dấu cách sau mỗi dấu phẩy.

Closure arguments with default values MUST go at the end of the argument
list.
Các  closure arguments có giá trị mặc định PHẢI đặt ở cuối danh sách argument

A closure declaration looks like the following. Note the placement of
parentheses, commas, spaces, and braces:
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

Argument lists and variable lists MAY be split across multiple lines, where
each subsequent line is indented once. When doing so, the first item in the
list MUST be on the next line, and there MUST be only one argument or variable
per line.
Danh sách Argument và danh sách variable CÓ THỂ được chia thành nhiều dòng, mỗi dòng sẽ được indented* căn lề* 1 lần. Thành phần đầu tiên trong danh sách PHẢI được viết ở dòng mới, và mỗi dòng chỉ được có 1 argument hoặc variable

When the ending list (whether or arguments or variables) is split across
multiple lines, the closing parenthesis and opening brace MUST be placed
together on their own line with one space between them.
Khi đoạn cuối của danh sách (kể cả arguments hay variables ) được chia thành nhiều dòng, các dấu đóng ngoặc tròn và mở ngoặc nhọn PHẢI được đặt cùng dòng với 1 dấu cách đặt ở giữa

The following are examples of closures with and without argument lists and
variable lists split across multiple lines.
Ví dụ dưới đây về các closures và danh sách *without argument* và danh sách variable được chia thành nhiều dòng

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

Note that the formatting rules also apply when the closure is used directly
in a function or method call as an argument.
Chú ý các quy định formatting cũng áp dụng khi closure được sử dụng trực tiếp trong 1 function hay method call như 1 argument

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


7. Conclusion Lời kết
--------------

There are many elements of style and practice intentionally omitted by this
guide. These include but are not limited to:
Có rất nhiêt yếu tố về style và practice bị bọ qua trong hướng dẫn này.Ví dụ như:


- Declaration of global variables and global constants
- Khai báo biến global và hằng global

- Declaration of functions
- Khai báo hàm

- Operators and assignment
- *Operators and assignment*

- Inter-line alignment
- *Inter-line alignment*

- Comments and documentation blocks
- Comments và khối documentation

- Class name prefixes and suffixes
- Tiền tố và hậu tố trong tên Class

- Best practices
- *Best practices*

Future recommendations MAY revise and extend this guide to address those or
other elements of style and practice.
Các kiến nghị trong tương lai CÓ THỂ sửa đổi và mở rộng hướng dẫn này để đề cập đến các yếu tố khác về style và practice.

Appendix A. Survey
------------------

In writing this style guide, the group took a survey of member projects to
determine common practices.  The survey is retained herein for posterity.

### A.1. Survey Data Dữ liệu khảo sát

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

### A.2. Survey Legend Ghi chú khảo sát

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

### A.3. Survey Results Kết quả khảo sát

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
