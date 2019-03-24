# DroidBeta C# 格式规范

C# 是由 Microsoft Corp. 开发的新一代面向对象的程序设计语言，在桌面开发中广泛使用。养成良好的格式规范对学好 C# 语言有很大帮助。

DroidBeta C# 格式规范基于 C 系列语言的 Allman 编码格式制定，由强制规范与建议规范组成。

## 强制规范

> 下列规范在平时代码书写时应时刻遵守，对养成良好的代码习惯有促进作用。

* 关于缩进

DroidBeta 建议使用 Tab 字符（ `\t` ， `	`）作为缩进字符，并将 Tab 宽度设为 4 个半角空格。若 Tab 显示不正常也可直接使用 4 个半角空格代替，但在发布至团队协作项目或开源时应替换为 Tab 字符。

在定义方法、使用多行语句时，左大括号应在方法类型定义或语句头下一行，并与函数类型左对齐。方法体或语句体应在大括号基础上缩进一个 Tab 字符。

* 关于引用外部命名空间

允许使用 using 语句精简类名，但是除非另有需要，不应使用 using static 语句，以减少命名空间污染。

* 关于命名

原则上命名空间、类（结构体）、构造函数、析构函数、方法、常量名使用 Pascal 命名法，即每个单词首字母大写，无下划线分隔。

变量名、字段名、参数名使用 Camel 命名法，即除开头单词首字母小写以外，每个单词首字母大写，无下划线分隔。

接口名使用 Hungarian 命名法，即在名称开头加入 `I` 以与其他语法元素区分。

无论何种语法结构都应避免使用诸如 `a` 、 `s` 、 `Func` 、 `Obj` 之类的含糊名称。应尽量使用具体的、完整的英文单词或者规范的单词缩写（仅在不引起歧义的情况下）表示。在命名中，冠词与 be 动词应当省略。

运算符与前后变量或常量间保留一个空格，但成员运算符（点号， `.` ）和圆括号、方括号前后不空格；逗号、分号前面空格，但后面不空格。

```Csharp

using System;

namespace MyConsoleApplication

{

public class MyConsole

{

public static void Main()

{

int sum, addend1, addend2;

string outputString;

addend1 = Convert.ToInt32(Console.ReadLine());

addend2 = Convert.ToInt32(Console.ReadLine());

sum = addend1 + addend2;

outputString = String.Format("{0} + {1} = {2}", addend1, addend2, sum);

Console.WriteLine(outputString);

}

}

}

```

* 关于语句跨行问题

尽量避免使用过长语句。除非语句长度过长（超过40字符），不应使单行语句跨行。长字符串赋值请使用如下方式。为了使显示清晰， += 所在语句也应追加一个 Tab 字符缩进。

```Csharp

string s = "A very long string ";

s += "and it will be even longer ";

s += "until it reaches the end.";

```

如果语句无法避免地跨行，请在每一个新行前追加 Tab 字符。

```Csharp

VeryLongObject.RatherLongerMethod

(WithLongestParameterInDroidBeta);

```

在制作方法简介时，应使用如下的 XML 格式：

```Csharp

///<summary>

///Method <c>Sum(int, int)</c> returns an int value of the sum of the input numbers.

///</summary>

int Sum(int a, int b)

{

return a + b;

}

```

## 建议规范

> 以下规范不是必须达到的，但是为了代码简明、准确，应尽量在修订时使代码遵守此部分规范，在团队内外公开发布的类库中尤应如此

* 词性选用

在代码中，词性具有非常重要的表示作用。例如，一个动词表示一种行为，一个形容词表示一种状态。英语中大量词汇在不同语境下有不同形式。

在 C# 代码中，方法名应使用动词或动词短语，`bool`类型的属性名与变量名应使用形容词或形容词性短语，非`bool`类型的属性名与变量名以及类名、对象名应使用名词或名词短语，某些具体使用语境下应根据实际情况使用最合适的词性。

