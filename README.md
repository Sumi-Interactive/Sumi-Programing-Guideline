Sumi Programing Guideline
=========================

## 文件命名

### 工程、代码文件、Xcode项目相关文件

使用 Pascal 命名法（大驼峰式命名法）
	
> * MyGreatApp
> * SIAlertView.h
> * Settings.storyboard
> * Tweets.xcdatamodeld
> * Images.xcassets
> * Info.plist

### 资源文件

* 用`-`连接的**小写**单词。
* 命名遵循规则：*[[模块-]类型-]*名字*[-状态]*

> * button-submit-normal.png
> * home-button-refresh-highlighted.png
> * icon-accounts.png
> * home-graphic-cover.jpg
> * user-config.plist

### 备注

* 所有文件的后缀名**小写**
* 使用有意义的命名，一般不要用缩写。
* 专有缩略词按照应用规则后首字母的大小写来统一。
`AFJSONRequestOperation`,`pdfPresentation`,`XMLHTTPRequest`


## 目录命名

* 使用 Pascal 命名法
* 用类型名称归类，映射到 Xcode 的 Group。
* 使用复数

> * Images
> * Fonts
> * Sounds
> * Videos
> * Strings
> * Plist
> * ...


## 代码命名

### 类、常量、枚举

使用 Pascal 命名法

`UIViewController`, `UIApplicationDidEnterBackgroundNotification`, `NSDateFormatterLongStyle`

### 方法、属性、变量、参数

* 驼峰式命名法

`layoutSubviews`, `contentView`, `selectedIndex`

* 实例变量要以`_`开头

```
@implementation MyClass {
    BOOL _showsTitle;
}
```

### 函数

使用 Pascal 命名法

`UIImagePNGRepresentation(image)`, `CGPointMake(x, y)`

### 静态变量

* 局部静态变量用驼峰式命名法

```
static dispatch_once_t onceToken;
dispatch_once(&onceToken, ^{

});
```

* 全局静态变量用`__`开头，`_`连接**小写**单词

```
static NSMutableArray *__visible_alerts;
```

### 宏

#### 常量

使用 Pascal 命名法

`NSUIntegerMax`, `M_PI`

#### 函数

* 用`_`连接的**大写**单词

`IS_LANDSCAPE`, `UI_USER_INTERFACE_IDIOM()`, `MIN()`

#### 编译器宏

* 用`__`开头, `_`连接的**大写**单词

`__IPHONE_7_0`, `__OSX_AVAILABLE_STARTING()`


## 代码格式化风格

```
int main(int argc, char *argv[])
{
    ...
    while (x == y) {
        something();
        somethingelse();

        if (some_error) {
            do_correct();
        } else {
            continue_as_usual();
        }
    }

    finalthing();
    ...
}
```

1. K&R 代码风格。
2. 不要省略 `{}`。
3. 中括号和小括号前后不要留空格 `[]()`。
4. 比较符、等号、冒号、逗号和大括号前后要保留一个空格 `> = : , { }`。Objective-C的消息参数中的冒号是一个例外，不要空格。
5. `*`,`^` 后不要空格。
6. 行尾不要留空格。
7. 用 4 个空格缩进。设置 Xcode 的 Tab Size 和 Indent Size 为 4
8. 编译器指令不缩进。
9. 不要垂直对齐。
10. 方法之间空一行。

*说明：应用以上规则时如果产生冲突，以后出现的规则为准。*


## Git

### 分支命名

* 用姓名的缩写开头。
* 用`-`连接小写单词。

> `kc-new-feature`, `vz-fix-dst`

### Commit

* 第一行写标题。如果需要，空一行，再写详细描述。
* 宽度限制72个字符。
* 用英文写的话不要用被动时态。
