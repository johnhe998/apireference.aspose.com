---
title: Watermark.SetText
second_title: Справочник по API Aspose.Words для .NET
description: Watermark метод. Добавляет текстовый водяной знак в документ.
type: docs
weight: 40
url: /ru/net/aspose.words/watermark/settext/
---
## SetText(string) {#settext}

Добавляет текстовый водяной знак в документ.

```csharp
public void SetText(string text)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| text | String | Текст, отображаемый в виде водяного знака. |

### Исключения

| исключение | условие |
| --- | --- |
| ArgumentOutOfRangeException | Выдает, когда длина текста выходит за пределы диапазона или текст содержит только пробелы. |
| ArgumentNullException | Выдает, когда текст равен нулю. |

### Примечания

Длина текста должна быть в диапазоне от 1 до 200 включительно. Текст не может быть нулевым или содержать только пробелы.

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

* class [Watermark](../)
* пространство имен [Aspose.Words](../../watermark/)
* сборка [Aspose.Words](../../../)

---

## SetText(string, TextWatermarkOptions) {#settext_1}

Добавляет текстовый водяной знак в документ.

```csharp
public void SetText(string text, TextWatermarkOptions options)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| text | String | Текст, отображаемый в виде водяного знака. |
| options | TextWatermarkOptions | Определяет дополнительные параметры текстового водяного знака. |

### Исключения

| исключение | условие |
| --- | --- |
| ArgumentOutOfRangeException | Выдает, когда длина текста выходит за пределы диапазона или текст содержит только пробелы. |
| ArgumentNullException | Выдает, когда текст равен нулю. |

### Примечания

Длина текста должна быть в диапазоне от 1 до 200 включительно. Текст не может быть нулевым или содержать только пробелы.

Если[`TextWatermarkOptions`](../../textwatermarkoptions/) имеет значение null, водяной знак будет установлен с параметрами по умолчанию.

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

* class [TextWatermarkOptions](../../textwatermarkoptions/)
* class [Watermark](../)
* пространство имен [Aspose.Words](../../watermark/)
* сборка [Aspose.Words](../../../)


