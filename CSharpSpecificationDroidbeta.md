# Droidbeta C# 格式规范

C# 是由 Microsoft Corp. 开发的新一代面向对象的程序设计语言，在桌面开发中广泛使用。养成良好的格式规范对学好 C# 语言有很大帮助。

Droidbeta C# 格式规范基于 C 系列语言的 Allman 编码格式制定，由强制规范与建议规范组成。

## 强制规范

Droidbeta 建议使用 Tab 字符（ '\t' ， '	'）作为缩进字符，并将 Tab 宽度设为 4 个半角空格。若 Tab 显示不正常也可直接使用 4 个半角空格代替，但在发布至团队协作项目或开源时应替换为 Tab 字符。

允许使用 using 语句精简类名，但是除非另有需要，不应使用 using static 语句，以减少命名空间污染。

在定义方法、使用多行语句时，左大括号应在方法类型定义或语句头下一行，并与函数类型左对齐。方法体或语句体应在大括号基础上缩进一个 Tab 字符。

原则上命名空间、类（结构体）、方法、常量名使用 Pascal 命名法，即每个单词首字母大写，无下划线分隔。

变量名使用 Camel 命名法，即除开头单词首字母小写以外，每个单词首字母大写，无下划线分隔。

无论何种语法结构都应避免使用诸如 a 、 s 、 Func 之类的含糊名称。应尽量使用完整的英文单词或者（不引起歧义的情况下）单词缩写表示。

运算符与前后变量或常量间保留一个空格。

```C#
using System;
namespace MyConsoleApplication
{
	public class MyConsole
    {
        public static void Main ()
        {
            int sum, a, b;
            string outputString;
            a = Convert.ToInt32 (Console.ReadLine ());
            b = Convert.ToInt32 (Console.ReadLine ());
            sum = a + b;
            outputString = String.Format ("{0} + {1} = {2}", a, b, sum);
            Console.WriteLine (outputString);
        }
    }
}
```

除非语句长度过长，否则不应使单行语句跨行。过长字符串赋值请使用如下方式。为了使显示清晰， += 所在语句也应追加一个 Tab 字符缩进。

```C#
string s = "A very long string ";
    s += "and it will be even longer ";
    s += "until it reaches the end.";
```

如果语句无法避免地跨行，请在每一个新行前追加 Tab 字符。

```C#
AVeryLongObject.
    ARatherLongerMethod
    (WithTheLongestParameterInDroidbeta);
```

在制作方法简介时，应使用如下的XML格式：

```C#
///<summary>
///This method returns an int value of 0.
///</summary>
```

## 建议规范