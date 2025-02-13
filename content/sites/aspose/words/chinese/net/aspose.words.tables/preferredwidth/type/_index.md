---
title: PreferredWidth.Type
second_title: Aspose.Words for .NET API 参考
description: PreferredWidth 财产. 获取用于此首选宽度值的测量单位
type: docs
weight: 40
url: /zh/net/aspose.words.tables/preferredwidth/type/
---
## PreferredWidth.Type property

获取用于此首选宽度值的测量单位。

```csharp
public PreferredWidthType Type { get; }
```

### 例子

显示如何验证表格单元格的首选宽度类型和值。

```csharp
Document doc = new Document(MyDir + "Tables.docx");

Table table = doc.FirstSection.Body.Tables[0];
Cell firstCell = table.FirstRow.FirstCell;

Assert.AreEqual(PreferredWidthType.Percent, firstCell.CellFormat.PreferredWidth.Type);
Assert.AreEqual(11.16d, firstCell.CellFormat.PreferredWidth.Value);
```

### 也可以看看

* enum [PreferredWidthType](../../preferredwidthtype/)
* class [PreferredWidth](../)
* 命名空间 [Aspose.Words.Tables](../../preferredwidth/)
* 部件 [Aspose.Words](../../../)


