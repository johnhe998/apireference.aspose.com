---
title: Paragraph.GetEffectiveTabStops
second_title: Справочник по API Aspose.Words для .NET
description: Paragraph метод. Возвращает массив всех позиций табуляции примененных к этому абзацу в том числе примененных косвенно с помощью стилей или списков.
type: docs
weight: 250
url: /ru/net/aspose.words/paragraph/geteffectivetabstops/
---
## Paragraph.GetEffectiveTabStops method

Возвращает массив всех позиций табуляции, примененных к этому абзацу, в том числе примененных косвенно с помощью стилей или списков.

```csharp
public TabStop[] GetEffectiveTabStops()
```

### Примеры

Показывает, как установить пользовательские позиции табуляции для абзаца.

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;

// Если мы находимся в абзаце без позиций табуляции в этой коллекции,
// курсор будет перемещаться на 36 пунктов каждый раз, когда мы нажимаем клавишу Tab в Microsoft Word.
Assert.AreEqual(0, doc.FirstSection.Body.FirstParagraph.GetEffectiveTabStops().Length);

// Мы можем добавить собственные позиции табуляции в Microsoft Word, если включим линейку на вкладке «Вид».
// Каждая единица на этой линейке — это две позиции табуляции по умолчанию, что составляет 72 точки.
// Мы можем программно добавить пользовательские позиции табуляции следующим образом.
TabStopCollection tabStops = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.TabStops;
tabStops.Add(72, TabAlignment.Left, TabLeader.Dots);
tabStops.Add(216, TabAlignment.Center, TabLeader.Dashes);
tabStops.Add(360, TabAlignment.Right, TabLeader.Line);

// Мы можем увидеть эти позиции табуляции в Microsoft Word, включив линейку через «Просмотр» -> "Показать" -> "Правитель".
Assert.AreEqual(3, para.GetEffectiveTabStops().Length);

// Любые символы табуляции, которые мы добавляем, будут использовать позиции табуляции на линейке и могут,
// в зависимости от значения ведущей вкладки оставить линию между пунктами отправления и прибытия вкладки.
para.AppendChild(new Run(doc, "\tTab 1\tTab 2\tTab 3"));

doc.Save(ArtifactsDir + "Paragraph.TabStops.docx");
```

### Смотрите также

* class [TabStop](../../tabstop/)
* class [Paragraph](../)
* пространство имен [Aspose.Words](../../paragraph/)
* сборка [Aspose.Words](../../../)


