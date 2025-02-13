---
title: Font.LineSpacing
second_title: Aspose.Words for .NET API 参考
description: Font 财产. 返回此字体的行距以磅为单位
type: docs
weight: 190
url: /zh/net/aspose.words/font/linespacing/
---
## Font.LineSpacing property

返回此字体的行距（以磅为单位）。

```csharp
public double LineSpacing { get; }
```

### 例子

显示如何获取字体的行间距（以磅为单位）。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 为 DocumentBuilder 设置不同的字体并验证它们的行距。
builder.Font.Name = "Calibri";
Assert.AreEqual(14.6484375d, builder.Font.LineSpacing);

builder.Font.Name = "Times New Roman";
Assert.AreEqual(13.798828125d, builder.Font.LineSpacing);
```

### 也可以看看

* class [Font](../)
* 命名空间 [Aspose.Words](../../font/)
* 部件 [Aspose.Words](../../../)


