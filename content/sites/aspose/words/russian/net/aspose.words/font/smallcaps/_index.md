---
title: Font.SmallCaps
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Истинно если шрифт отформатирован как маленькие заглавные буквы.
type: docs
weight: 360
url: /ru/net/aspose.words/font/smallcaps/
---
## Font.SmallCaps property

Истинно, если шрифт отформатирован как маленькие заглавные буквы.

```csharp
public bool SmallCaps { get; set; }
```

### Примеры

Показывает, как отформатировать прогон, чтобы его содержимое отображалось заглавными буквами.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// Есть два способа заставить run отображать строчный текст в верхнем регистре без изменения содержимого.
// 1 - Установите флаг AllCaps для отображения всех символов обычными прописными буквами:
Run run = new Run(doc, "all capitals");
run.Font.AllCaps = true;
para.AppendChild(run);

para = (Paragraph)para.ParentNode.AppendChild(new Paragraph(doc));

// 2 - Установите флаг SmallCaps для отображения всех символов маленькими прописными буквами:
// Если символ в нижнем регистре, он будет отображаться в верхнем регистре
// но будет иметь ту же высоту, что и нижний регистр (высота x шрифта).
// Символы, которые изначально были в верхнем регистре, будут выглядеть так же.
run = new Run(doc, "Small Capitals");
run.Font.SmallCaps = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.Caps.docx");
```

### Смотрите также

* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


