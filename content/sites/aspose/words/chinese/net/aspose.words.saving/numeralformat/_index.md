---
title: Enum NumeralFormat
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.NumeralFormat 枚举. 表示在呈现为固定页面格式时用于表示数字 的符号集
type: docs
weight: 5030
url: /zh/net/aspose.words.saving/numeralformat/
---
## NumeralFormat enumeration

表示在呈现为固定页面格式时用于表示数字 的符号集。

```csharp
public enum NumeralFormat
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| European | `0` | 欧洲数字：0123456789. |
| ArabicIndic | `1` | 阿拉伯语中使用的数字：٠١٢٣٤٥٦٧٨٩. Unicode 范围 U+0660 - u+0669. |
| EasternArabicIndic | `2` | 波斯语和乌尔都语中使用的数字： 012334566778۹. Unicode 范围 U+06F0 - u+06F9. |
| Context | `3` | 符号集由上下文（语言环境和 RTL 属性）决定。 |
| System | `4` | 不支持此选项。 符号集由区域设置决定。 |

### 例子

显示如何设置保存为 PDF 时使用的数字格式。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = new CultureInfo("ar-AR").LCID;
builder.Writeln("1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 50, 100");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions options = new PdfSaveOptions();

// 将“NumeralFormat”属性设置为“NumeralFormat.ArabicIndic”以
// 使用 U+0660 到 U+0669 范围内的字形作为数字。
// 将“NumeralFormat”属性设置为“NumeralFormat.Context”以
// 查找语言环境以确定要使用的字形数量。
// 将“NumeralFormat”属性设置为“NumeralFormat.EasternArabicIndic”以
// 使用 U+06F0 到 U+06F9 范围内的字形作为数字。
// 将“NumeralFormat”属性设置为“NumeralFormat.European”以使用欧洲数字。
// 将“NumeralFormat”属性设置为“NumeralFormat.System”，以根据区域设置确定符号集。
options.NumeralFormat = numeralFormat;

doc.Save(ArtifactsDir + "PdfSaveOptions.SetNumeralFormat.pdf", options);
```

### 也可以看看

* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


