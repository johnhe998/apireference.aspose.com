---
title: TextWatermarkOptions.FontSize
second_title: Справочник по API Aspose.Words для .NET
description: TextWatermarkOptions свойство. Получает или задает размер шрифта. Значение по умолчанию 0  auto.
type: docs
weight: 40
url: /ru/net/aspose.words/textwatermarkoptions/fontsize/
---
## TextWatermarkOptions.FontSize property

Получает или задает размер шрифта. Значение по умолчанию 0 - auto.

```csharp
public float FontSize { get; set; }
```

### Исключения

| исключение | условие |
| --- | --- |
| ArgumentOutOfRangeException | Выдает, когда аргумент находится вне диапазона допустимых значений. |

### Примечания

Допустимые значения находятся в диапазоне от 0 до 65,5 включительно.

Автоматический размер шрифта означает, что водяной знак будет масштабироваться до максимальной ширины и максимальной высоты относительно полей страницы.

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


