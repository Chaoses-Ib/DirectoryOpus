# 求值器变量

求值器支持以下变量类型：

| 类型 | 描述 | 最小值 | 最大值 |
|---|---|---|---|
| bool | 布尔值 (true 或 false) | 无 | 无 |
| int | 有符号 32 位整数 | -2147483648 | 2147483647 |
| uint | 无符号 32 位整数 | 0 | 4294967295 |
| int64 | 有符号 64 位整数 | -9223372036854775808 | 9223372036854775807 |
| uint64 | 无符号 64 位整数 | 0 | 18446744073709551615 |
| double | 双精度浮点数 | 1.7E-308 | 1.7E+308 |
| date | 日期/时间 | 1601-01-01 00:00:00 | 9999-12-31 23:59:59 |
| str | 字符串 | 无 | 无 |
| path | 路径 | 无 | 无 |
| map | 值容器 | 无 | 无 |

初始化变量时，某些类型会自动推断：

| 示例 | 初始化为 |
|---|---|
| x = true; | bool |
| x = false; | bool |
| x = 15; | uint |
| x = -15; | int |
| x = 5000000000; | uint64 |
| x = -5000000000; | int64 |
| x = 1185.15; | double |
| x = "string"; | str |
| x = [a = 1; b = 2;]; | map |

你可以通过两种方式显式地初始化某个类型的变量。这是 *date* 和 *path* 变量必需的，它们总是从字符串初始化。

- 您可以使用 `[As](/Manual/reference/evaluator/as.zh.md)` 运算符，例如 `d = "2023-08-20" as date;`
- 您可以使用 `:` 运算符，例如 `d: date = "2023-08-20";`

例如，要将变量初始化为路径而不是普通字符串：

    p = "C:\Windows" as path;
    p = p + "System32";
    Output(p);

    --> "C:\Windows\System32"

请注意，在上例中，最终字符串在 "Windows" 和 "System32" 之间包含一个反斜杠 - 这是因为它被初始化为 *path* 变量，并且将字符串添加到 *path* 变量会自动添加路径分隔符。

查看 [As](/Manual/reference/evaluator/as.zh.md) 运算符的文档以获取有关显式初始化的更多详细信息。`:` 运算符使用与 **As** 运算符相同的类型关键字。

如果需要，求值器将隐式转换变量类型。例如，如果你调用一个记录为接受 *int* 的函数，但你传递给它的却是 *uint*、 *int64* 甚至是 *str*，那么该值将被自动转换（当然，假设此类转换是可能的）。

你可以使用 `[typeof](/Manual/reference/evaluator/typeof.zh.md)` 函数来确定变量的类型。

##### 变量名

普通变量必须以字母开头；之后，它们可以包含任意数量的字母、数字或符号，如 `_` 和 `$`。

求值器还允许你访问以 `$` 符号开头的外部变量。例如，一个使用了 `@set name Jon` 然后调用求值器代码的函数将能够使用名称 `$name` 访问该变量。可以访问作用域为标签页和列出器的外部变量，例如 `$glob:name` 允许你从求值器中获取或设置全局作用域的变量。

通常，尝试使用不存在的变量的值会导致错误，但是出于兼容性原因，以 `$` 开头的变量允许这样做——如果它们之前没有被定义，它们将简单地返回一个空字符串。

你还可以像在普通函数中一样从求值代码中访问环境变量。例如，

    Output(%PROGRAMFILES%);
    --> C:\Program Files

你也可以从求值代码中设置环境变量，但请注意，这只会影响 Opus 本身的环境——全局地，系统的其他部分不会看到已更改的值。

##### 数字常量

你可以使用多种方式来表示数字常量：

- 普通十进制数，例如 `15` 或 `-15`。
- 十六进制数，例如 `0xe`。
- 大小值，例如 `5kb`、`21gb`、`1.75tb`（注意：仅支持二进制单位）。
- 在日期中添加或减去时使用后缀 `h`（小时）、`m`（分钟）、`s`（秒）、`d`（天）、`M`（月）和 `y`（年）的日期单位。
- 分数，例如 `1185.15`。
- `true` 和 `false` 也可用作布尔常量。
- `pi` 被预定义为 π 的值。

##### 值容器

*值容器* 是一个可以包含其他变量的变量——类似于 C++ 中的 *struct* 或 JavaScript 中的 *map*。

值容器使用 `[ ]` 运算符定义。方括号充当 *作用域*——在方括号内，你分配的变量将成为容器的成员。例如，

    // 定义一个空容器
    x = [ ];

    // 定义一个有三个成员的容器
    x = [ a = 5; b = 10; c = "hello!"; ];

在创建和/或初始化值容器后，你可以使用 `.` 运算符访问其成员变量（或添加新的成员变量）。

    Output(x.c);
    --> hello!

    x.c = Left(x.c, 5) + " world!";
    Output(x.c);
    --> hello world!