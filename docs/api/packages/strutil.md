# Strutil

strutil 包含处理字符串的相关函数。

<div STYLE="page-break-after: always;"></div>

## 源码:

-   [https://github.com/duke-git/lancet/blob/main/strutil/string.go](https://github.com/duke-git/lancet/blob/main/strutil/string.go)

<div STYLE="page-break-after: always;"></div>

## 用法:

```go
import (
    "github.com/duke-git/lancet/v2/strutil"
)
```

<div STYLE="page-break-after: always;"></div>

## 目录

-   [After](#After)
-   [AfterLast](#AfterLast)
-   [Before](#Before)
-   [BeforeLast](#BeforeLast)
-   [CamelCase](#CamelCase)
-   [UpperCamelCase](#UpperCamelCase)
-   [Capitalize](#Capitalize)
-   [IsString](#IsString)
-   [KebabCase](#KebabCase)
-   [UpperKebabCase](#UpperKebabCase)
-   [LowerFirst](#LowerFirst)
-   [UpperFirst](#UpperFirst)
-   [Pad](#Pad)
-   [PadEnd](#PadEnd)
-   [PadStart](#PadStart)
-   [Reverse](#Reverse)
-   [SnakeCase](#SnakeCase)
-   [UpperSnakeCase](#UpperSnakeCase)
-   [SplitEx](#SplitEx)
-   [Substring](#Substring)
-   [Wrap](#Wrap)
-   [Unwrap](#Unwrap)
-   [SplitWords](#SplitWords)
-   [WordCount](#WordCount)
-   [RemoveNonPrintable](#RemoveNonPrintable)
-   [StringToBytes](#StringToBytes)
-   [BytesToString](#BytesToString)
-   [IsBlank](#IsBlank)
-   [IsNotBlank](#IsNotBlank)
-   [HasPrefixAny](#HasPrefixAny)
-   [HasSuffixAny](#HasSuffixAny)
-   [IndexOffset](#IndexOffset)
-   [ReplaceWithMap](#ReplaceWithMap)
-   [Trim](#Trim)
-   [SplitAndTrim](#SplitAndTrim)
-   [HideString](#HideString)
-   [ContainsAll](#ContainsAll)
-   [ContainsAny](#ContainsAny)
-   [RemoveWhiteSpace](#RemoveWhiteSpace)
-   [SubInBetween](#SubInBetween)
-   [HammingDistance](#HammingDistance)
-   [Concat](#Concat)
-   [Ellipsis](#Ellipsis)
-   [Shuffle](#Shuffle)
-   [Rotate](#Rotate)
-   [TemplateReplace](#TemplateReplace)
-   [RegexMatchAllGroups](#RegexMatchAllGroups)
-   [ExtractContent](#ExtractContent)
-   [FindAllOccurrences](#FindAllOccurrences)


<div STYLE="page-break-after: always;"></div>

## 文档

### <span id="After">After</span>

<p>返回源字符串中特定字符串首次出现时的位置之后的子字符串。</p>

<b>函数签名:</b>

```go
func After(s, char string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/RbCOQqCDA7m)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.After("foo", "")
    result2 := strutil.After("foo", "foo")
    result3 := strutil.After("foo/bar", "foo")
    result4 := strutil.After("foo/bar", "/")
    result5 := strutil.After("foo/bar/baz", "/")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)

    // Output:
    // foo
    //
    // /bar
    // bar
    // bar/baz
}
```

### <span id="AfterLast">AfterLast</span>

<p>返回源字符串中指定字符串最后一次出现时的位置之后的子字符串。</p>

<b>函数签名:</b>

```go
func AfterLast(s, char string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/1TegARrb8Yn)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.AfterLast("foo", "")
    result2 := strutil.AfterLast("foo", "foo")
    result3 := strutil.AfterLast("foo/bar", "/")
    result4 := strutil.AfterLast("foo/bar/baz", "/")
    result5 := strutil.AfterLast("foo/bar/foo/baz", "foo")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)

    // Output:
    // foo
    //
    // bar
    // baz
    // /baz
}
```

### <span id="Before">Before</span>

<p>返回源字符串中指定字符串第一次出现时的位置之前的子字符串。</p>

<b>函数签名:</b>

```go
func Before(s, char string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/JAWTZDS4F5w)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.Before("foo", "")
    result2 := strutil.Before("foo", "foo")
    result3 := strutil.Before("foo/bar", "/")
    result4 := strutil.Before("foo/bar/baz", "/")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)

    // Output:
    // foo
    //
    // foo
    // foo
}
```

### <span id="BeforeLast">BeforeLast</span>

<p>返回源字符串中指定字符串最后一次出现时的位置之前的子字符串。</p>

<b>函数签名:</b>

```go
func BeforeLast(s, char string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/pJfXXAoG_Te)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.BeforeLast("foo", "")
    result2 := strutil.BeforeLast("foo", "foo")
    result3 := strutil.BeforeLast("foo/bar", "/")
    result4 := strutil.BeforeLast("foo/bar/baz", "/")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)

    // Output:
    // foo
    //
    // foo
    // foo/bar
}
```

### <span id="CamelCase">CamelCase</span>

<p>将字符串转换为驼峰式字符串，首字母小写, 非字母和数字会被忽略。</p>

<b>函数签名:</b>

```go
func CamelCase(s string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/9eXP3tn2tUy)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    strings := []string{"", "foobar", "&FOO:BAR$BAZ", "$foo%", "Foo-#1😄$_%^&*(1bar"}

    for _, v := range strings {
        s := strutil.CamelCase(v)
        fmt.Println(s)
    }

    // Output:
    //
    // foobar
    // fooBarBaz
    // foo
    // foo11Bar
}
```

### <span id="UpperCamelCase">UpperCamelCase</span>

<p>将字符串转换为大写驼峰式字符串，首字母大写写, 非字母和数字会被忽略。</p>

<b>函数签名:</b>

```go
func UpperCamelCase(s string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/65Q6iYhLRTa)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    strings := []string{"", "foobar", "&FOO:BAR$BAZ", "$foo%", "Foo-#1😄$_%^&*(1bar"}

	for _, v := range strings {
		s := strutil.UpperCamelCase(v)
		fmt.Println(s)
	}
	// Output:
	//
	// Foobar
	// FooBarBaz
	// Foo
	// Foo11Bar
}
```

### <span id="KebabCase">KebabCase</span>

<p>将字符串转换为kebab-case, 非字母和数字会被忽略。</p>

<b>函数签名:</b>

```go
func KebabCase(s string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/dcZM9Oahw-Y)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    strings := []string{"", "foo-bar", "Foo Bar-", "FOOBAR", "Foo-#1😄$_%^&*(1bar"}

    for _, v := range strings {
        s := strutil.KebabCase(v)
        fmt.Println(s)
    }

    // Output:
    //
    // foo-bar
    // foo-bar
    // foobar
    // foo-1-1-bar
}
```

### <span id="UpperKebabCase">UpperKebabCase</span>

<p>将字符串转换为大写KEBAB-CASE, 非字母和数字会被忽略。</p>

<b>函数签名:</b>

```go
func UpperKebabCase(s string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/zDyKNneyQXk)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    strings := []string{"", "foo-bar", "Foo Bar-", "FooBAR", "Foo-#1😄$_%^&*(1bar"}

    for _, v := range strings {
        s := strutil.UpperKebabCase(v)
        fmt.Println(s)
    }

    // Output:
    //
    // FOO-BAR
    // FOO-BAR
    // FOO-BAR
    // FOO-1-1-BAR
}
```

### <span id="Capitalize">Capitalize</span>

<p>将字符串的第一个字符转换为大写。</p>

<b>函数签名:</b>

```go
func Capitalize(s string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/2OAjgbmAqHZ)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    strings := []string{"", "Foo", "_foo", "fooBar", "foo-bar"}

    for _, v := range strings {
        s := strutil.Capitalize(v)
        fmt.Println(s)
    }

    // Output:
    //
    // Foo
    // _foo
    // Foobar
    // Foo-bar
}
```

### <span id="IsString">IsString</span>

<p>判断传入参数的数据类型是否为字符串。</p>

<b>函数签名:</b>

```go
func IsString(v any) bool
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/IOgq7oF9ERm)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.IsString("")
    result2 := strutil.IsString("a")
    result3 := strutil.IsString(1)
    result4 := strutil.IsString(true)
    result5 := strutil.IsString([]string{"a"})

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)

    // Output:
    // true
    // true
    // false
    // false
    // false
}
```

### <span id="LowerFirst">LowerFirst</span>

<p>将字符串的第一个字符转换为小写。</p>

<b>函数签名:</b>

```go
func LowerFirst(s string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/CbzAyZmtJwL)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    strings := []string{"", "bar", "BAr", "Bar大"}

    for _, v := range strings {
        s := strutil.LowerFirst(v)
        fmt.Println(s)
    }

    // Output:
    //
    // bar
    // bAr
    // bar大
}
```

### <span id="UpperFirst">UpperFirst</span>

<p>将字符串的第一个字符转换为大写形式。</p>

<b>函数签名:</b>

```go
func UpperFirst(s string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/sBbBxRbs8MM)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    strings := []string{"", "bar", "BAr", "bar大"}

    for _, v := range strings {
        s := strutil.UpperFirst(v)
        fmt.Println(s)
    }

    // Output:
    //
    // Bar
    // BAr
    // Bar大
}
```

### <span id="Pad">Pad</span>

<p>如果字符串长度短于size，则在左右两侧填充字符串。</p>

<b>函数签名:</b>

```go
func Pad(source string, size int, padStr string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/NzImQq-VF8q)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.Pad("foo", 1, "bar")
    result2 := strutil.Pad("foo", 2, "bar")
    result3 := strutil.Pad("foo", 3, "bar")
    result4 := strutil.Pad("foo", 4, "bar")
    result5 := strutil.Pad("foo", 5, "bar")
    result6 := strutil.Pad("foo", 6, "bar")
    result7 := strutil.Pad("foo", 7, "bar")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)
    fmt.Println(result6)
    fmt.Println(result7)
    // Output:
    // foo
    // foo
    // foo
    // foob
    // bfoob
    // bfooba
    // bafooba
}
```

### <span id="PadEnd">PadEnd</span>

<p>如果字符串长度短于size，则在右侧填充字符串。</p>

<b>函数签名:</b>

```go
func PadEnd(source string, size int, padStr string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/9xP8rN0vz--)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.PadEnd("foo", 1, "bar")
    result2 := strutil.PadEnd("foo", 2, "bar")
    result3 := strutil.PadEnd("foo", 3, "bar")
    result4 := strutil.PadEnd("foo", 4, "bar")
    result5 := strutil.PadEnd("foo", 5, "bar")
    result6 := strutil.PadEnd("foo", 6, "bar")
    result7 := strutil.PadEnd("foo", 7, "bar")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)
    fmt.Println(result6)
    fmt.Println(result7)

    // Output:
    // foo
    // foo
    // foo
    // foob
    // fooba
    // foobar
    // foobarb
}
```

### <span id="PadStart">PadStart</span>

<p>如果字符串长度短于size，则在左侧填充字符串。</p>

<b>函数签名:</b>

```go
func PadStart(source string, size int, padStr string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/xpTfzArDfvT)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.PadStart("foo", 1, "bar")
    result2 := strutil.PadStart("foo", 2, "bar")
    result3 := strutil.PadStart("foo", 3, "bar")
    result4 := strutil.PadStart("foo", 4, "bar")
    result5 := strutil.PadStart("foo", 5, "bar")
    result6 := strutil.PadStart("foo", 6, "bar")
    result7 := strutil.PadStart("foo", 7, "bar")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)
    fmt.Println(result6)
    fmt.Println(result7)

    // Output:
    // foo
    // foo
    // foo
    // bfoo
    // bafoo
    // barfoo
    // barbfoo
}
```

### <span id="Reverse">Reverse</span>

<p>返回字符顺序与给定字符串相反的字符串。</p>

<b>函数签名:</b>

```go
func Reverse(s string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/adfwalJiecD)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    s := "foo"
    rs := strutil.Reverse(s)

    fmt.Println(s)
    fmt.Println(rs)

    // Output:
    // foo
    // oof
}
```

### <span id="SnakeCase">SnakeCase</span>

<p>将字符串转换为snake_case形式, 非字母和数字会被忽略。</p>

<b>函数签名:</b>

```go
func SnakeCase(s string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/tgzQG11qBuN)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    strings := []string{"", "foo-bar", "Foo Bar-", "FOOBAR", "Foo-#1😄$_%^&*(1bar"}

    for _, v := range strings {
        s := strutil.SnakeCase(v)
        fmt.Println(s)
    }

    // Output:
    //
    // foo_bar
    // foo_bar
    // foobar
    // foo_1_1_bar
}
```

### <span id="UpperSnakeCase">UpperSnakeCase</span>

<p>将字符串转换为大写SNAKE_CASE形式, 非字母和数字会被忽略。</p>

<b>函数签名:</b>

```go
func UpperSnakeCase(s string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/4COPHpnLx38)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    strings := []string{"", "foo-bar", "Foo Bar-", "FooBAR", "Foo-#1😄$_%^&*(1bar"}

    for _, v := range strings {
        s := strutil.UpperSnakeCase(v)
        fmt.Println(s)
    }

    // Output:
    //
    // FOO_BAR
    // FOO_BAR
    // FOO_BAR
    // FOO_1_1_BAR
}
```

### <span id="SplitEx">SplitEx</span>

<p>分割字符串为切片，removeEmptyString参数指定是否去除空字符串。</p>

<b>函数签名:</b>

```go
func SplitEx(s, sep string, removeEmptyString bool) []string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/Us-ySSbWh-3)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.SplitEx(" a b c ", "", true)

    result2 := strutil.SplitEx(" a b c ", " ", false)
    result3 := strutil.SplitEx(" a b c ", " ", true)

    result4 := strutil.SplitEx("a = b = c = ", " = ", false)
    result5 := strutil.SplitEx("a = b = c = ", " = ", true)

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)

    // Output:
    // []
    // [ a b c ]
    // [a b c]
    // [a b c ]
}
```

### <span id="Substring">Substring</span>

<p>根据指定的位置和长度截取字符串。</p>

<b>函数签名:</b>

```go
func Substring(s string, offset int, length uint) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/q3sM6ehnPDp)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.Substring("abcde", 1, 3)
    result2 := strutil.Substring("abcde", 1, 5)
    result3 := strutil.Substring("abcde", -1, 3)
    result4 := strutil.Substring("abcde", -2, 2)
    result5 := strutil.Substring("abcde", -2, 3)
    result6 := strutil.Substring("你好，欢迎你", 0, 2)

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)
    fmt.Println(result6)

    // Output:
    // bcd
    // bcde
    // e
    // de
    // de
    // 你好
}
```

### <span id="Wrap">Wrap</span>

<p>用另一个字符串包裹一个字符串。</p>

<b>函数签名:</b>

```go
func Wrap(str string, wrapWith string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/KoZOlZDDt9y)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.Wrap("foo", "")
    result2 := strutil.Wrap("foo", "*")
    result3 := strutil.Wrap("'foo'", "'")
    result4 := strutil.Wrap("", "*")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)

    // Output:
    // foo
    // *foo*
    // ''foo''
    //
}
```

### <span id="Unwrap">Unwrap</span>

<p>用另一个字符串解开包裹一个字符串。</p>

<b>函数签名:</b>

```go
func Unwrap(str string, wrapToken string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/Ec2q4BzCpG-)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.Unwrap("foo", "")
    result2 := strutil.Unwrap("*foo*", "*")
    result3 := strutil.Unwrap("*foo", "*")
    result4 := strutil.Unwrap("foo*", "*")
    result5 := strutil.Unwrap("**foo**", "*")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)

    // Output:
    // foo
    // foo
    // *foo
    // foo*
    // *foo*
}
```

### <span id="SplitWords">SplitWords</span>

<p>将字符串拆分为单词，只支持字母字符单词。</p>

<b>函数签名:</b>

```go
func SplitWords(s string) []string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/KLiX4WiysMM)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.SplitWords("a word")
    result2 := strutil.SplitWords("I'am a programmer")
    result3 := strutil.SplitWords("Bonjour, je suis programmeur")
    result4 := strutil.SplitWords("a -b-c' 'd'e")
    result5 := strutil.SplitWords("你好，我是一名码农")
    result6 := strutil.SplitWords("こんにちは，私はプログラマーです")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)
    fmt.Println(result6)

    // Output:
    // [a word]
    // [I'am a programmer]
    // [Bonjour je suis programmeur]
    // [a b-c' d'e]
    // []
    // []
}
```

### <span id="WordCount">WordCount</span>

<p>返回有意义单词的数量，只支持字母字符单词。</p>

<b>函数签名:</b>

```go
func WordCount(s string) int
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/bj7_odx3vRf)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.WordCount("a word")
    result2 := strutil.WordCount("I'am a programmer")
    result3 := strutil.WordCount("Bonjour, je suis programmeur")
    result4 := strutil.WordCount("a -b-c' 'd'e")
    result5 := strutil.WordCount("你好，我是一名码农")
    result6 := strutil.WordCount("こんにちは，私はプログラマーです")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)
    fmt.Println(result6)

    // Output:
    // 2
    // 3
    // 4
    // 3
    // 0
    // 0
}
```

### <span id="RemoveNonPrintable">RemoveNonPrintable</span>

<p>删除字符串中不可打印的字符。</p>

<b>函数签名:</b>

```go
func RemoveNonPrintable(str string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/og47F5x_jTZ)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.RemoveNonPrintable("hello\u00a0 \u200bworld\n")
    result2 := strutil.RemoveNonPrintable("你好😄")

    fmt.Println(result1)
    fmt.Println(result2)

    // Output:
    // hello world
    // 你好😄
}
```

### <span id="StringToBytes">StringToBytes</span>

<p>在不分配内存的情况下将字符串转换为字节片。</p>

<b>函数签名:</b>

```go
func StringToBytes(str string) (b []byte)
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/7OyFBrf9AxA)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.StringToBytes("abc")
    result2 := reflect.DeepEqual(result1, []byte{'a', 'b', 'c'})

    fmt.Println(result1)
    fmt.Println(result2)
    // Output:
    // [97 98 99]
    // true
}
```

### <span id="BytesToString">BytesToString</span>

<p>在不分配内存的情况下将字节切片转换为字符串。</p>

<b>函数签名:</b>

```go
func BytesToString(bytes []byte) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/6c68HRvJecH)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    bytes := []byte{'a', 'b', 'c'}
    result := strutil.BytesToString(bytes)

    fmt.Println(result)

    // Output:
    // abc
}
```

### <span id="IsBlank">IsBlank</span>

<p>检查字符串是否为空格或空。</p>

<b>函数签名:</b>

```go
func IsBlank(str string) bool
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/6zXRH_c0Qd3)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.IsBlank("")
    result2 := strutil.IsBlank("\t\v\f\n")
    result3 := strutil.IsBlank(" 中文")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)

    // Output:
    // true
    // true
    // false
}
```

### <span id="IsNotBlank">IsNotBlank</span>

<p>Checks if a string is not whitespace or not empty.</p>

<b>函数签名:</b>

```go
func IsNotBlank(str string) bool
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/e_oJW0RAquA)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.IsNotBlank("")
    result2 := strutil.IsNotBlank("    ")
    result3 := strutil.IsNotBlank("\t\v\f\n")
    result4 := strutil.IsNotBlank(" 中文")
    result5 := strutil.IsNotBlank("     world    ")
    
    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)
    // Output:
    // false
    // false
    // false
    // true
    // true
}
```

### <span id="HasPrefixAny">HasPrefixAny</span>

<p>检查字符串是否以指定字符串数组中的任何一个开头。</p>

<b>函数签名:</b>

```go
func HasPrefixAny(str string, prefixes []string) bool
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/8UUTl2C5slo)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.HasPrefixAny("foo bar", []string{"fo", "xyz", "hello"})
    result2 := strutil.HasPrefixAny("foo bar", []string{"oom", "world"})

    fmt.Println(result1)
    fmt.Println(result2)

    // Output:
    // true
    // false
}
```

### <span id="HasSuffixAny">HasSuffixAny</span>

<p>检查字符串是否以指定字符串数组中的任何一个结尾。</p>

<b>函数签名:</b>

```go
func HasSuffixAny(str string, suffixes []string) bool
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/sKWpCQdOVkx)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.HasSuffixAny("foo bar", []string{"bar", "xyz", "hello"})
    result2 := strutil.HasSuffixAny("foo bar", []string{"oom", "world"})

    fmt.Println(result1)
    fmt.Println(result2)

    // Output:
    // true
    // false
}
```

### <span id="IndexOffset">IndexOffset</span>

<p>将字符串偏移idxFrom后，返回字符串中第一个 substr 实例的索引，如果字符串中不存在 substr，则返回 -1。</p>

<b>函数签名:</b>

```go
func IndexOffset(str string, substr string, idxFrom int) int
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/qZo4lV2fomB)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    str := "foo bar hello world"

    result1 := strutil.IndexOffset(str, "o", 5)
    result2 := strutil.IndexOffset(str, "o", 0)
    result3 := strutil.IndexOffset(str, "d", len(str)-1)
    result4 := strutil.IndexOffset(str, "d", len(str))
    result5 := strutil.IndexOffset(str, "f", -1)

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)
    fmt.Println(result5)

    // Output:
    // 12
    // 1
    // 18
    // -1
    // -1
}
```

### <span id="ReplaceWithMap">ReplaceWithMap</span>

<p>返回`str`的副本，以无序的方式被map替换，区分大小写。</p>

<b>函数签名:</b>

```go
func ReplaceWithMap(str string, replaces map[string]string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/h3t7CNj2Vvu)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    str := "ac ab ab ac"
    replaces := map[string]string{
        "a": "1",
        "b": "2",
    }

    result := strutil.ReplaceWithMap(str, replaces)

    fmt.Println(result)
    // Output:
    // 1c 12 12 1c
}
```

### <span id="Trim">Trim</span>

<p>从字符串的开头和结尾去除空格（或其他字符）。 可选参数 characterMask 指定额外的剥离字符。</p>

<b>函数签名:</b>

```go
func Trim(str string, characterMask ...string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/Y0ilP0NRV3j)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.Trim("\nabcd")

    str := "$ ab    cd $ "

    result2 := strutil.Trim(str)
    result3 := strutil.Trim(str, "$")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)

    // Output:
    // abcd
    // $ ab    cd $
    // ab    cd
}
```

### <span id="SplitAndTrim">SplitAndTrim</span>

<p>将字符串str按字符串delimiter拆分为一个切片，并对该数组的每个元素调用Trim。忽略Trim后为空的元素。</p>

<b>函数签名:</b>

```go
func SplitAndTrim(str, delimiter string, characterMask ...string) []string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/ZNL6o4SkYQ7)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    str := " a,b, c,d,$1 "

    result1 := strutil.SplitAndTrim(str, ",")
    result2 := strutil.SplitAndTrim(str, ",", "$")

    fmt.Println(result1)
    fmt.Println(result2)

    // Output:
    // [a b c d $1]
    // [a b c d 1]
}
```

### <span id="HideString">HideString</span>

<p>使用参数`replaceChar`隐藏源字符串中的一些字符。替换范围是 origin[start : end]。</p>

<b>函数签名:</b>

```go
func HideString(origin string, start, end int, replaceChar string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/pzbaIVCTreZ)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    str := "13242658976"

    result1 := strutil.HideString(str, 3, 3, "*")
    result2 := strutil.HideString(str, 3, 4, "*")
    result3 := strutil.HideString(str, 3, 7, "*")
    result4 := strutil.HideString(str, 7, 11, "*")

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)
    fmt.Println(result4)

    // Output:
    // 13242658976
    // 132*2658976
    // 132****8976
    // 1324265****
}
```

### <span id="ContainsAll">ContainsAll</span>

<p>判断字符串是否包括全部给定的子字符串切片。</p>

<b>函数签名:</b>

```go
func ContainsAll(str string, substrs []string) bool
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/KECtK2Os4zq)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    str := "hello world"

    result1 := strutil.ContainsAll(str, []string{"hello", "world"})
    result2 := strutil.ContainsAll(str, []string{"hello", "abc"})

    fmt.Println(result1)
    fmt.Println(result2)

    // Output:
    // true
    // false
}
```

### <span id="ContainsAny">ContainsAny</span>

<p>判断字符串是否包括给定的子字符串切片中任意一个子字符串。</p>

<b>函数签名:</b>

```go
func ContainsAny(str string, substrs []string) bool
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/dZGSSMB3LXE)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    str := "hello world"

    result1 := strutil.ContainsAny(str, []string{"hello", "world"})
    result2 := strutil.ContainsAny(str, []string{"hello", "abc"})
    result3 := strutil.ContainsAny(str, []string{"123", "abc"})

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)

    // Output:
    // true
    // true
    // false
}
```

### <span id="RemoveWhiteSpace">RemoveWhiteSpace</span>

<p>删除字符串中的空格，当设置repalceAll为true时，删除全部空格，为false时，替换多个空格为1个空格。</p>

<b>函数签名:</b>

```go
func RemoveWhiteSpace(str string, repalceAll bool) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/HzLC9vsTwkf)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    str := " hello   \r\n    \t   world"

    result1 := strutil.RemoveWhiteSpace(str, true)
    result2 := strutil.RemoveWhiteSpace(str, false)

    fmt.Println(result1)
    fmt.Println(result2)

    // Output:
    // helloworld
    // hello world
}
```

### <span id="SubInBetween">SubInBetween</span>

<p>获取字符串中指定的起始字符串start和终止字符串end直接的子字符串。</p>

<b>函数签名:</b>

```go
func SubInBetween(str string, start string, end string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/EDbaRvjeNsv)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    str := "abcde"

    result1 := strutil.SubInBetween(str, "", "de")
    result2 := strutil.SubInBetween(str, "a", "d")

    fmt.Println(result1)
    fmt.Println(result2)

    // Output:
    // abc
    // bc
}
```

### <span id="HammingDistance">HammingDistance</span>

<p>计算两个字符串之间的汉明距离。汉明距离是指对应符号不同的位置数。</p>

<b>函数签名:</b>

```go
func HammingDistance(a, b string) (int, error)
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/glNdQEA9HUi)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {

    result1, _ := strutil.HammingDistance("de", "de")
    result2, _ := strutil.HammingDistance("a", "d")

    fmt.Println(result1)
    fmt.Println(result2)

    // Output:
    // 0
    // 1
}

```
### <span id="Concat">Concat</span>

<p>拼接字符串。length是拼接后字符串的长度，如果不确定则传0或负数。</p>

<b>函数签名:</b>

```go
func Concat(length int, str ...string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/gD52SZHr4Kp)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.Concat(12, "Hello", " ", "World", "!")
    result2 := strutil.Concat(11, "Go", " ", "Language")
    result3 := strutil.Concat(0, "An apple a ", "day，", "keeps the", " doctor away")
    
    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)

    // Output:
    // Hello World!
    // Go Language
    // An apple a day，keeps the doctor away
}
```

### <span id="Ellipsis">Ellipsis</span>

<p>将字符串截断到指定长度，并在末尾添加省略号。</p>

<b>函数签名:</b>

```go
func Ellipsis(str string, length int) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/i1vbdQiQVRR)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.Ellipsis("hello world", 5)
    result2 := strutil.Ellipsis("你好，世界!", 2)
    result3 := strutil.Ellipsis("😀😃😄😁😆", 3)

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)

    // Output:
    // hello...
    // 你好...
    // 😀😃😄...
}
```

### <span id="Shuffle">Shuffle</span>

<p>打乱给定字符串中的字符顺序。</p>

<b>函数签名:</b>

```go
func Shuffle(str string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/iStFwBwyGY7)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result := strutil.Shuffle("hello")
    fmt.Println(result)  //olelh (random order)
}
```

### <span id="Rotate">Rotate</span>

<p>按指定的字符数旋转字符串。</p>

<b>函数签名:</b>

```go
func Rotate(str string, shift int) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/Kf03iOeT5bd)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result1 := strutil.Rotate("Hello", 0)
    result2 := strutil.Rotate("Hello", 1)
    result3 := strutil.Rotate("Hello", 2)

    fmt.Println(result1)
    fmt.Println(result2)
    fmt.Println(result3)

    // Output:
    // Hello
    // oHell
    // loHel
}
```

### <span id="TemplateReplace">TemplateReplace</span>

<p>将模板字符串中的占位符替换为map中的相应值。占位符括在花括号中，例如 {key}。例如，模板字符串为“Hello, {name}!”，map为{"name": "world"}，结果将为“Hello, world!”。</p>

<b>函数签名:</b>

```go
func TemplateReplace(template string, data map[string]string) string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/cXSuFvyZqv9)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    template := `Hello, my name is {name}, I'm {age} years old.`
    data := map[string]string{
        "name": "Bob",
        "age":  "20",
    }

    result := strutil.TemplateReplace(template, data)

    fmt.Println(result)

    // Output:
    // Hello, my name is Bob, I'm 20 years old.
}
```

### <span id="RegexMatchAllGroups">RegexMatchAllGroups</span>

<p>使用正则表达式匹配字符串中的所有子组并返回结果。</p>

<b>函数签名:</b>

```go
func RegexMatchAllGroups(pattern, str string) [][]string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/JZiu0RXpgN-)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    pattern := `(\w+\.+\w+)@(\w+)\.(\w+)`
    str := "Emails: john.doe@example.com and jane.doe@example.com"

    result := strutil.RegexMatchAllGroups(pattern, str)

    fmt.Println(result[0])
    fmt.Println(result[1])

    // Output:
    // [john.doe@example.com john.doe example com]
    // [jane.doe@example.com jane.doe example com]
}
```

### <span id="ExtractContent">ExtractContent</span>

<p>提取两个标记之间的内容。</p>

<b>函数签名:</b>

```go
func ExtractContent(s, start, end string) []string
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/Ay9UIk7Rum9)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    html := `<span>content1</span>aa<span>content2</span>bb<span>content1</span>`

    result := strutil.ExtractContent(html, "<span>", "</span>")

    fmt.Println(result)

    // Output:
    // [content1 content2 content1]
}
```

### <span id="FindAllOccurrences">FindAllOccurrences</span>

<p>返回子字符串在字符串中所有出现的位置。</p>

<b>函数签名:</b>

```go
func FindAllOccurrences(str, substr string) []int
```

<b>示例:<span style="float:right;display:inline-block;">[运行](https://go.dev/play/p/uvyA6azGLB1)</span></b>

```go
import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    result := strutil.FindAllOccurrences("ababab", "ab")

    fmt.Println(result)

    // Output:
    // [0 2 4]
}
```