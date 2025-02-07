---
title: BorderCollection.LineStyle
second_title: Справочник по API Aspose.Words для .NET
description: BorderCollection свойство. Получает или задает стиль границы.
type: docs
weight: 80
url: /ru/net/aspose.words/bordercollection/linestyle/
---
## BorderCollection.LineStyle property

Получает или задает стиль границы.

```csharp
public LineStyle LineStyle { get; set; }
```

### Примечания

Возвращает стиль первой рамки в коллекции.

Устанавливает стиль всех границ в коллекции, кроме диагональных границ.

### Примеры

Показывает, как создать зеленую волнистую границу страницы с тенью.

```csharp
Document doc = new Document();
PageSetup pageSetup = doc.Sections[0].PageSetup;

pageSetup.Borders.LineStyle = LineStyle.DoubleWave;
pageSetup.Borders.LineWidth = 2;
pageSetup.Borders.Color = Color.Green;
pageSetup.Borders.DistanceFromText = 24;
pageSetup.Borders.Shadow = true;

doc.Save(ArtifactsDir + "PageSetup.PageBorders.docx");
```

### Смотрите также

* enum [LineStyle](../../linestyle/)
* class [BorderCollection](../)
* пространство имен [Aspose.Words](../../bordercollection/)
* сборка [Aspose.Words](../../../)


