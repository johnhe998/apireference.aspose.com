---
title: BorderCollection.Equals
second_title: Справочник по API Aspose.Words для .NET
description: BorderCollection метод. Сравнивает наборы границ.
type: docs
weight: 150
url: /ru/net/aspose.words/bordercollection/equals/
---
## BorderCollection.Equals method

Сравнивает наборы границ.

```csharp
public bool Equals(BorderCollection brColl)
```

### Примеры

Показывает, как коллекции границ могут совместно использовать элементы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Paragraph 1.");
builder.Write("Paragraph 2.");

// Так как мы использовали ту же конфигурацию границы при создании
// эти абзацы, их наборы границ имеют одни и те же элементы.
BorderCollection firstParagraphBorders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;
BorderCollection secondParagraphBorders = builder.CurrentParagraph.ParagraphFormat.Borders;

for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsTrue(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());
    Assert.False(firstParagraphBorders[i].IsVisible);
}

foreach (Border border in secondParagraphBorders)
    border.LineStyle = LineStyle.DotDash;

// После изменения стиля линий границ только во втором абзаце,
// коллекции границ больше не содержат одни и те же элементы.
for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsFalse(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreNotEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());

    // Изменение внешнего вида пустой границы делает ее видимой.
    Assert.True(secondParagraphBorders[i].IsVisible);
}

doc.Save(ArtifactsDir + "Border.SharedElements.docx");
```

### Смотрите также

* class [BorderCollection](../)
* пространство имен [Aspose.Words](../../bordercollection/)
* сборка [Aspose.Words](../../../)


