---
title: TxtSaveOptions.AddBidiMarks
second_title: Aspose.Words for .NET API 参考
description: TxtSaveOptions 财产. 指定以纯文本格式导出时是否在每次 BiDi 运行之前添加双向标记
type: docs
weight: 20
url: /zh/net/aspose.words.saving/txtsaveoptions/addbidimarks/
---
## TxtSaveOptions.AddBidiMarks property

指定以纯文本格式导出时是否在每次 BiDi 运行之前添加双向标记。

默认值为 **错误的**.

```csharp
public bool AddBidiMarks { get; set; }
```

### 例子

显示如何在文本中的每个双向运行之前插入 Unicode 字符“RIGHT-TO-LEFT MARK”(U+200F)。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");

// 创建一个“TxtSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改我们如何将文档保存为纯文本。
TxtSaveOptions saveOptions = new TxtSaveOptions { Encoding = System.Text.Encoding.Unicode};

// 将“AddBidiMarks”属性设置为“true”以在运行前添加标记
// 用从右到左的文本来表示事实。
// 将“AddBidiMarks”属性设置为“false”以从左到右写入
// 并且从右到左运行相同，没有任何迹象表明哪个是哪个。
saveOptions.AddBidiMarks = addBidiMarks;

doc.Save(ArtifactsDir + "TxtSaveOptions.AddBidiMarks.txt", saveOptions);

string docText = System.Text.Encoding.Unicode.GetString(File.ReadAllBytes(ArtifactsDir + "TxtSaveOptions.AddBidiMarks.txt"));

if (addBidiMarks)
{
    Assert.AreEqual("\uFEFFHello world!‎\r\nשלום עולם!‏\r\nمرحبا بالعالم!‏\r\n\r\n", docText);
    Assert.True(docText.Contains("\u200f"));
}
else
{
    Assert.AreEqual("\uFEFFHello world!\r\nשלום עולם!\r\nمرحبا بالعالم!\r\n\r\n", docText);
    Assert.False(docText.Contains("\u200f"));
}
```

### 也可以看看

* class [TxtSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../txtsaveoptions/)
* 部件 [Aspose.Words](../../../)


