---
title: ParagraphFormat.LinesToDrop
second_title: Aspose.Words for .NET API 参考
description: ParagraphFormat 财产. 获取或设置用于计算首字下沉高度的段落文本行数
type: docs
weight: 200
url: /zh/net/aspose.words/paragraphformat/linestodrop/
---
## ParagraphFormat.LinesToDrop property

获取或设置用于计算首字下沉高度的段落文本行数。

```csharp
public int LinesToDrop { get; set; }
```

### 例子

显示如何设置首字下沉的大小。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 修改“LinesToDrop”属性，将段落指定为首字下沉，
// 这将把它变成一个大写字母来装饰下一段。
// 将此属性的值设置为 4，以使首字下沉的高度为四行文本。
builder.ParagraphFormat.LinesToDrop = 4;
builder.Writeln("H");

// 将“LinesToDrop”属性重置为 0，将下一段变为普通段落。
// 本段中的文本将环绕首字下沉。
builder.ParagraphFormat.LinesToDrop = 0;
builder.Writeln("ello world!");

doc.Save(ArtifactsDir + "ParagraphFormat.LinesToDrop.odt");
```

### 也可以看看

* class [ParagraphFormat](../)
* 命名空间 [Aspose.Words](../../paragraphformat/)
* 部件 [Aspose.Words](../../../)


