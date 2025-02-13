---
title: BorderCollection.Color
second_title: Справочник по API Aspose.Words для .NET
description: BorderCollection свойство. Получает или задает цвет границы.
type: docs
weight: 20
url: /ru/net/aspose.words/bordercollection/color/
---
## BorderCollection.Color property

Получает или задает цвет границы.

```csharp
public Color Color { get; set; }
```

### Примечания

Возвращает цвет первой границы в коллекции.

Задает цвет всех границ в коллекции, кроме диагональных границ.

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

* class [BorderCollection](../)
* пространство имен [Aspose.Words](../../bordercollection/)
* сборка [Aspose.Words](../../../)


