---
title: Fill.Solid
second_title: Справочник по API Aspose.Words для .NET
description: Fill метод. Устанавливает заливку однородным цветом.
type: docs
weight: 200
url: /ru/net/aspose.words.drawing/fill/solid/
---
## Solid() {#solid}

Устанавливает заливку однородным цветом.

```csharp
public void Solid()
```

### Примечания

Используйте этот метод для преобразования любой заливки обратно в сплошную заливку.

### Смотрите также

* class [Fill](../)
* пространство имен [Aspose.Words.Drawing](../../fill/)
* сборка [Aspose.Words](../../../)

---

## Solid(Color) {#solid_1}

Устанавливает заливку указанным однородным цветом.

```csharp
public void Solid(Color color)
```

### Примечания

Используйте этот метод для преобразования любой заливки обратно в сплошную заливку.

### Примеры

Показывает, как преобразовать любую из заливок обратно в сплошную заливку.

```csharp
Document doc = new Document(MyDir + "Two color gradient.docx");

// Получить объект Fill для шрифта первого запуска.
Fill fill = doc.FirstSection.Body.Paragraphs[0].Runs[0].Font.Fill;

// Проверяем свойства заливки шрифта.
Console.WriteLine("The type of the fill is: {0}", fill.FillType);
Console.WriteLine("The foreground color of the fill is: {0}", fill.ForeColor);
Console.WriteLine("The fill is transparent at {0}%", fill.Transparency * 100);

// Изменить тип заливки на сплошную с равномерным зеленым цветом.
fill.Solid(Color.Green);
Console.WriteLine("\nThe fill is changed:");
Console.WriteLine("The type of the fill is: {0}", fill.FillType);
Console.WriteLine("The foreground color of the fill is: {0}", fill.ForeColor);
Console.WriteLine("The fill transparency is {0}%", fill.Transparency * 100);

doc.Save(ArtifactsDir + "Drawing.FillSolid.docx");
```

### Смотрите также

* class [Fill](../)
* пространство имен [Aspose.Words.Drawing](../../fill/)
* сборка [Aspose.Words](../../../)


