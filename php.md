Hướng dẫn về Coding Style - Coding Style Guide
==================

Bộ quy tắc này dựa trên và mở rộng từ [PSR-1], basic coding standard

1. Khái quát chung
-----------

- Code phải tuân theo "coding style guide" PSR [[PSR-1]].

- Code không dùng tab, mà phải sử dụng 4 dấu cách làm indent.

- Không có hard limit về độ dài của một dòng; soft limit phải là 120
  chữ. Một dòng nên có không quá 80 chữ.

- Cần phải có một dòng trống ở sau phần khai báo `namespace`. Ngoài ra cũng cần có
  một dòng trống phía sau phần khai báo `use`.

- Phải luôn khai báo tính visibility (`public`, `protected` hay là `private`) của properties cũng như methods.
 `abstract` và `final` phải được khai báo phía trước tính visibility và `static` phải được khai báo sau tính visibility.

- Cần phải có một dấu cách phía sau những từ khoá Control structure (như `if`, `else`, `for` ...).
  Không được có dấu cách phía sau tên của method khi gọi hàm.

- Dấu mở ngoặc nhọn cho control structures (như `if`, `else`, `for` ...) phải được viết cùng dòng, trong khi đó đấu đóng ngoặc
  phải được viết ở dòng mới.

- Trong câu lệnh control structures, không được phép có dấu cách ở sau dấu mở ngặc tròn cũng như ở trước dấu đóng ngoặc tròn.


2. Tổng thể
----------

### 2.1 Basic Coding Standard

Code phải tuân theo "coding style guide" PSR [[PSR-1]].

### 2.2 Files

Mọi PHP files phải dùng Unix LF (linefeed) line ending.

Mọi PHP files phải kết thúc bằng một dòng trống.

Trong một file chỉ bao gồm code PHP thì không được viết tag đóng `?>`.

### 2.3. Lines

Không có hard limit về độ dài của một dòng.

Soft limit của độ dài một dòng phải là 120 chữ. 

Một dòng nên có không quá 80 chữ. Dòng mà dài quá 80 chữ thì nên chia nhỏ ra thành nhiều dòng với độ dài mỗi dòng
không quá 80 chữ.

Một dòng không trống không được phép có trailing whitespace (dấu cách ở cuối dòng)

Dòng trống có thể được thêm vào để code có thể được dễ đọc hơn và để phân cách những đoạn code.

Không được phép có quá một statement trên một dòng.

### 2.4. Canh lề - Indenting

Code không dùng tab, mà phải sử dụng 4 dấu cách làm indent. 
Chú ý, không nên sửa theo chuẩn này đối với những file cũ của người khác code.

### 2.5. Keywords và True/False/Null

Những [keywords] của PHP phải được viết thường. (không viết hoa)

Những constants của PHP là `true`, `false`, và `null` cũng cần phải viết thường.

[keywords]: http://php.net/manual/en/reserved.keywords.php


3. Khai báo Namespace và Use
---------------------------------

Cần phải có một dòng trắng phía sau khai báo `namespace`.

Những phần khai báo `use` phải được đặt phía sau phần khai báo `namespace`.

Phải dùng một từ `use` cho mỗi khao báo.

Phải có một dòng trắng phía sau đoạn code `use`.

Ví dụ:

```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

// ... additional PHP code ...

```


4. Classes, Properties, và Methods
-----------------------------------

### 4.1. Extends và Implements

Từ khoá `extends` và `implements` phải được viết cùng dòng với tên class.

Dấu mở ngoặc nhọn của class phải đứng trên một dòng riêng. Dấu đóng ngoặc phải được viết ở dòng sau của phần body.

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

Danh sách những interface được `implements` có thể được viết trên nhiều dòng, trong đó mỗi dòng theo sau được indent 1 lần.
Khi thực hiện việc đó thì tên interface đầu tiên phải được đặt trên 1 dòng mới, và mỗi dòng chỉ được phép chứa tên 1 interface.

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

### 4.2. Properties

Tính Visibility phải được khai báo ở mọi properties.

Không được dùng từ khoá `var` để khai báo một property.

Trong một câu thì không được khai báo quá một property.

Tên property không nên được prefix bởi dấu gạch dưới `_` để biểu thị tính protected hay private.

Khai báo property giống như sau.

```php
<?php
namespace Vendor\Package;

class ClassName {
    public $foo = null;
}
```

### 4.3. Methods

Tên Method không nên được prefix bởi dấu gạch dưới `_` để biểu thị tính protected hay private.

Khi khai báo tên method thì không được để một khoảng trắng ở phía sau tên method.
Không được có khoảng trắng sau dấu mở ngoặc tròn, và không được có khoảng trắng phía trước dấu đóng ngoặc tròn.

Khai báo một hàm giống như sau. Chú ý đến vị trí của dấu ngặc đơn, dấu phẩy, khoảng trắng và dấu ngoặc nhọn.

```php
<?php
namespace Vendor\Package;

class ClassName {
    public function fooBarBaz($arg1, &$arg2, $arg3 = []) {
        // method body
    }
}
```

### 4.4. Method Arguments

Trong danh sách argument (đối số) thì không được có khoảng trắng trước mỗi dấu phẩy, và phải có một khoảng trắng
sau mỗi dấu phẩy.

Những arguments của Method mà có giá trị mặc định phải được đặt ở cuối của danh sách argument.

```php
<?php
namespace Vendor\Package;

class ClassName {
    public function foo($arg1, &$arg2, $arg3 = []) {
        // method body
    }
}
```

Danh sách argument có thể được tách thành nhiều dòng, trong đó mỗi dòng theo sau được indent một lần.
Khi làm vậy thì argument đầu tiên trong danh sách phải được đặt ở trên một dòng mới, và mỗi dòng chỉ được phép có một argument.

Khi mà danh sách argument được chia làm nhiều dòng, thì dấu đóng ngoặc tròn và dấu mở ngoặc nhọn phải được đặt cùng nhau
trên một dòng, với một khoảng trắng ở giữa.

```php
<?php
namespace Vendor\Package;

class ClassName {
    public function aVeryLongMethodName(
        ClassTypeHint $arg1,
        &$arg2,
        array $arg3 = []
    ) {
        // method body
    }
}
```

### 4.5. `abstract`, `final`, và `static`

Khi được sử dụng, `abstract` và `final` phải được đặt trước phần khai báo visibility.

Khi được sử dụng, `static` phải được đặt sau phần khai báo visibility.

```php
<?php
namespace Vendor\Package;

abstract class ClassName {
    protected static $foo;

    abstract protected function zim();

    final public static function bar() {
        // method body
    }
}
```

### 4.6. Gọi Method và Function

Khi gọi một method hay một function, không được phép có khoảng trắng giữa tên của method hay function và dấu mở ngoặc tròn.
Không được phép có khoảng trắng sau dấu mở ngoặc tròn.
Và không được phép có khoảng trắng trước dấu đóng ngoặc tròn.
Trong danh sách argument, không được phép có khoảng trắng trước mỗi dấu phẩy,
và phải có một khoảng trắng sau mỗi dấu phẩy.

```php
<?php
bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);
```

Danh sách argument có thể được tách ra thành nhiều dòng, trong đó mỗi dòng theo sau được indent một lần.
Khi làm như vậy thì argument đầu tiên phải được đặt trên một dòng mới, và mỗi dòng chỉ được phép chứa một argument.

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

Những quy tắc chung khi viết Control Structures bao gồm:

- Phải có một khoảng trắng sau control structure keyword
- Không được có một khoảng trắng sau dấu mở ngoặc tròn
- Không được có một khoảng trắng trước dấu đóng ngoặc tròn
- Phải có một khoảng trắng sau đấu đóng ngoặc tròn và trước dấu mở ngoặc nhọn
- Phần thân của structure phải được indent một lần
- Dấu đóng ngoặc nhọn phỉa được đặt trên một dòng mới sau phần thân

Phần thân của mỗi structure phải được đặt trong dấu đóng mở ngoặc kép. Điều này sẽ làm tiêu chuẩn hoá cách viết structures,
và làm giảm thiểu việc phát sinh ra lỗi khi mà có những dòng mới được thêm vào phần thân.

### 5.1. `if`, `elseif`, `else`

Một `if` structure được viết như sau.
Hãy chú ý đến vị trí của dấu ngoặc tròn, khoảng trắng, dấu ngoặc nhọn. `else` và `elseif` được đặt trên cùng một dòng
với dấu đóng ngoặc nhọn của phần body phía trước.

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

Từ khoá `elseif` nên được dùng thay cho `else if`, để mọi control keywords chỉ là một từ đơn.
Chú ý, tránh sử dụng cấu trúc if else lồng nhau quá nhiều.

### 5.2. `switch`, `case`

Một `switch` structure được viết như sau.
Hãy chú ý đến vị trí của dấu ngoặc tròn, khoảng trắng và dấu ngoặc nhọn.
Phần `case` phải được indent một lần so với `switch`, và `break` keyword (hay các keyword ngắt khác) phải được indent giống
với phần thân của `case`.
Phải có một comment kiểu như `// no break` nếu phần thân của `case` không trống, và được cố tình cho qua (không có break)

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

Một câu lệnh `while` được viết như sau.
Hãy chú ý vào vị trí của dấu ngoặc tròn, khoảng trắng và dấu ngoặc nhọn.

```php
<?php
while ($expr) {
    // structure body
}
```

Tương tự như vậy, một câu lệnh `do while` được viết như sau.
Hãy chú ý vào vị trí của dấu ngoặc tròn, khoảng trắng và dấu ngoặc nhọn.

```php
<?php
do {
    // structure body;
} while ($expr);
```

### 5.4. `for`

Một câu lệnh `for` được viết như sau.
Hãy chú ý vào vị trí của dấu chấm phẩy, dấu ngoặc tròn, khoảng trắng và dấu ngoặc nhọn.

```php
<?php
for ($i = 0; $i < 10; $i++) {
    // for body
}
```

### 5.5. `foreach`

Một câu lệnh `foreach` được viết như sau.
Hãy chú ý vào vị trí của `=>`, dấu ngoặc tròn, khoảng trắng và dấu ngoặc nhọn.

```php
<?php
foreach ($iterable as $key => $value) {
    // foreach body
}
```

### 5.6. `try`, `catch`

Một block `try catch` được viết như sau.
Hãy chú ý vào vị trí của dấu ngoặc tròn, khoảng trắng và dấu ngoặc nhọn.

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

Closures phải được định nghĩa mới một khoảng trắng phía sau keywork `function`, và một khoảng trắng ở phía trước cũng
như phía sau của keywork `use`.

Dấu mở ngoặc ngọn phải được đặt ở cùng dòng, và dấu đóng ngoặc nhọn phải được đặt ở một dòng mời phía sau phần thân.

Không được phép có một khoảng trắng ở phía sau dấu mở ngoặc tròn của phần khai báo danh sách argument hay variable,
và không được phép có một khoảng trắng ở phía trước dấu đóng ngoặc tròn của phần khai báo danh sách argument hay variable.

Trong danh sách arugment hay variable, không được phép có khoảng trắng trước mỗi dấu phẩy, và phải có một khoảng trắng
phía sau mỗi dấu phẩy.

Arguments của Closure mà có giá trị mặc định thì phải được đặt ở cuối của danh sách argument.

Cách định nghĩa một closure trông như sau.

A closure declaration looks like the following.
Hãy chú ý vào vị trí của dấu ngoặc tròn, dấu phẩy, khoảng trắng và dấu ngoặc nhọn.

```php
<?php
$closureWithArgs = function ($arg1, $arg2) {
    // body
};

$closureWithArgsAndVars = function ($arg1, $arg2) use ($var1, $var2) {
    // body
};
```

Danh sách argument và danh sách variable có thể được tách ra làm nhiều dòng, trong đó mỗi dòng theo sau được indent
một lần. Khi làm như vậy thì argument hay variable đầu tiên phải được đặt ở trên một dòng mới, và mỗi dòng chỉ được phép
chứa một argument hay một variable.

Khi mà kết thúc của danh sách (kể cả arguments hay variables) được chia thành nhiều dòng,
thì dấu đóng ngoặc tròn và dấu mở ngoặc nhọn phải được đặt cùng nhau trên một dòng, với một khoảng trắng ở giữa.

Dưới đây là những ví dụ về các closures có và không có danh sách argument hay variable được chia thành nhiều dòng.

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

Chú ý rằng những quy tắc trên còn được áp dụng khi một closure được sử dụng trục tiếp như một argument trong một lời gọi
hàm hay method.

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


7. Một số quy tắc khác
--------------

- Sử dụng `.` thay cho `/` để phân cách đường dẫn.

```php
<?php
AAFW::import('jp.aainc.aafw.base.aafwPOSTActionBase');
);
```
- câu lệnh `if` dù chỉ có một dòng vẫn phải có dấu đóng mở ngoặc và xuống dòng. Ví dụ:

```php
<?php
 if (true) {
    return true;
 }
);
```

- các ký tự gán `=`, `=>` nên để thẳng hàng.

```php
<?php
 $result = [
       "entries"  => $entries,
       "page"     => $this->page,
       "count"    => $this->count,
       "has_next" => $has_next,
 ];
);
```