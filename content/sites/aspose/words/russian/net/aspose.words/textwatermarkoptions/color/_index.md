---
title: TextWatermarkOptions.Color
second_title: Справочник по API Aspose.Words для .NET
description: TextWatermarkOptions свойство. Получает или устанавливает цвет шрифта. Значение по умолчанию  Color.Silver. .
type: docs
weight: 20
url: /ru/net/aspose.words/textwatermarkoptions/color/
---
## TextWatermarkOptions.Color property

Получает или устанавливает цвет шрифта. Значение по умолчанию — Color.Silver. .

```csharp
public Color Color { get; set; }
```

### Примеры

Показывает, как создать текстовый водяной знак.

```csharp
Document doc = new Document();

// Добавляем простой текстовый водяной знак.
doc.Watermark.SetText("Aspose Watermark");

// Если мы хотим отредактировать форматирование текста, используя его как водяной знак,
// мы можем сделать это, передав объект TextWatermarkOptions при создании водяного знака.
TextWatermarkOptions textWatermarkOptions = new TextWatermarkOptions();
textWatermarkOptions.FontFamily = "Arial";
textWatermarkOptions.FontSize = 36;
textWatermarkOptions.Color = Color.Black;
textWatermarkOptions.Layout = WatermarkLayout.Diagonal;
textWatermarkOptions.IsSemitrasparent = false;

doc.Watermark.SetText("Aspose Watermark", textWatermarkOptions);

doc.Save(ArtifactsDir + "Document.TextWatermark.docx");

// Мы можем удалить водяной знак из такого документа.
if (doc.Watermark.Type == WatermarkType.Text)
    doc.Watermark.Remove();
```

### Смотрите также

* class [TextWatermarkOptions](../)
* пространство имен [Aspose.Words](../../textwatermarkoptions/)
* сборка [Aspose.Words](../../../)


