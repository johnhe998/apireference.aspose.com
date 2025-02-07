---
title: OleFormat.GetRawData
second_title: Справочник по API Aspose.Words для .NET
description: OleFormat метод. Получает необработанные данные объекта OLE.
type: docs
weight: 150
url: /ru/net/aspose.words.drawing/oleformat/getrawdata/
---
## OleFormat.GetRawData method

Получает необработанные данные объекта OLE.

```csharp
public byte[] GetRawData()
```

### Примеры

Показывает, как получить доступ к необработанным данным встроенного объекта OLE.

```csharp
Document doc = new Document(MyDir + "OLE objects.docx");

foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    OleFormat oleFormat = shape.OleFormat;
    if (oleFormat != null)
    {
        Console.WriteLine($"This is {(oleFormat.IsLink ? "a linked" : "an embedded")} object");
        byte[] oleRawData = oleFormat.GetRawData();

        Assert.AreEqual(24576, oleRawData.Length);
    }
}
```

### Смотрите также

* class [OleFormat](../)
* пространство имен [Aspose.Words.Drawing](../../oleformat/)
* сборка [Aspose.Words](../../../)


