---
title: OleFormat.SourceItem
second_title: Справочник по API Aspose.Words для .NET
description: OleFormat свойство. Получает или задает строку которая используется для идентификации части исходного файла на которую делается ссылка.
type: docs
weight: 110
url: /ru/net/aspose.words.drawing/oleformat/sourceitem/
---
## OleFormat.SourceItem property

Получает или задает строку, которая используется для идентификации части исходного файла, на которую делается ссылка.

```csharp
public string SourceItem { get; set; }
```

### Примечания

Значение по умолчанию — пустая строка.

Например, если исходный файл представляет собой книгу Microsoft Excel,`SourceItem` Свойство может возвращать «Workbook1!R3C1:R4C2», если объект OLE содержит только несколько ячеек из рабочего листа.

### Примеры

Показывает, как вставлять связанные и несвязанные объекты OLE.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Встроить рисунок Microsoft Visio в документ как объект OLE.
builder.InsertOleObject(ImageDir + "Microsoft Visio drawing.vsd", "Package", false, false, null);

// Вставляем ссылку на файл в локальную файловую систему и отображаем ее в виде значка.
builder.InsertOleObject(ImageDir + "Microsoft Visio drawing.vsd", "Package", true, true, null);

// При вставке объектов OLE создаются фигуры, в которых хранятся эти объекты.
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);
Assert.AreEqual(2, shapes.Count(s => s.ShapeType == ShapeType.OleObject));

// Если фигура содержит объект OLE, она будет иметь действительное свойство "OleFormat",
// который мы можем использовать для проверки некоторых аспектов фигуры.
OleFormat oleFormat = shapes[0].OleFormat;

Assert.AreEqual(false, oleFormat.IsLink);
Assert.AreEqual(false, oleFormat.OleIcon);

oleFormat = shapes[1].OleFormat;

Assert.AreEqual(true, oleFormat.IsLink);
Assert.AreEqual(true, oleFormat.OleIcon);

Assert.True(oleFormat.SourceFullName.EndsWith(@"Images" + Path.DirectorySeparatorChar + "Microsoft Visio drawing.vsd"));
Assert.AreEqual("", oleFormat.SourceItem);

Assert.AreEqual("Microsoft Visio drawing.vsd", oleFormat.IconCaption);

doc.Save(ArtifactsDir + "Shape.OleLinks.docx");

// Если объект содержит данные OLE, мы можем получить к ним доступ с помощью потока.
using (MemoryStream stream = oleFormat.GetOleEntry("\x0001CompObj"))
{
    byte[] oleEntryBytes = stream.ToArray();
    Assert.AreEqual(76, oleEntryBytes.Length);
}
```

### Смотрите также

* class [OleFormat](../)
* пространство имен [Aspose.Words.Drawing](../../oleformat/)
* сборка [Aspose.Words](../../../)


