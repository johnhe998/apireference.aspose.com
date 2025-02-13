---
title: PageSetup.LineNumberCountBy
second_title: Aspose.Words for .NET API 参考
description: PageSetup 财产. 返回或设置行号的数字增量
type: docs
weight: 210
url: /zh/net/aspose.words/pagesetup/linenumbercountby/
---
## PageSetup.LineNumberCountBy property

返回或设置行号的数字增量。

```csharp
public int LineNumberCountBy { get; set; }
```

### 例子

显示如何为部分启用行号。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 我们可以使用部分的 PageSetup 对象在部分文本行的左侧显示数字。
// 这与 List 对象的行为相同，
// 但它涵盖了整个部分并且不会以任何方式修改文本。
// 我们的部分将在每个新页面上从 1 重新开始编号并显示编号，
// 如果是 3 的倍数，则在该行左侧 50pt 处。
PageSetup pageSetup = builder.PageSetup;
pageSetup.LineStartingNumber = 1;
pageSetup.LineNumberCountBy = 3;
pageSetup.LineNumberRestartMode = LineNumberRestartMode.RestartPage;
pageSetup.LineNumberDistanceFromText = 50.0d;

for (int i = 1; i <= 25; i++)
    builder.Writeln($"Line {i}.");

// 行计数器将跳过任何“SuppressLineNumbers”标志设置为“true”的段落。
// 这一段在第 15 行，是 3 的倍数，因此通常会显示一个行号。
// 该节的行计数器也会忽略这一行，将下一行视为第 15 行，
// 并从该点开始继续计数。
doc.FirstSection.Body.Paragraphs[14].ParagraphFormat.SuppressLineNumbers = true;

doc.Save(ArtifactsDir + "PageSetup.LineNumbers.docx");
```

### 也可以看看

* class [PageSetup](../)
* 命名空间 [Aspose.Words](../../pagesetup/)
* 部件 [Aspose.Words](../../../)


