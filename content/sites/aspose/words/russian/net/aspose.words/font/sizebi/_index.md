---
title: Font.SizeBi
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Получает или задает размер шрифта в пунктах используемый в документе с письмом справа налево.
type: docs
weight: 350
url: /ru/net/aspose.words/font/sizebi/
---
## Font.SizeBi property

Получает или задает размер шрифта в пунктах, используемый в документе с письмом справа налево.

```csharp
public double SizeBi { get; set; }
```

### Примеры

Показывает, как определить отдельные наборы настроек шрифта для текста, написанного справа налево и справа налево.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Определяем набор настроек шрифта для текста слева направо.
builder.Font.Name = "Courier New";
builder.Font.Size = 16;
builder.Font.Italic = false;
builder.Font.Bold = false;
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;

// Определить другой набор настроек шрифта для текста, написанного справа налево.
builder.Font.NameBi = "Andalus";
builder.Font.SizeBi = 24;
builder.Font.ItalicBi = true;
builder.Font.BoldBi = true;
builder.Font.LocaleIdBi = new CultureInfo("ar-AR", false).LCID;

// Мы можем использовать флаг Bidi, чтобы указать, будет ли текст, который мы собираемся добавить,
// с конструктором документов справа налево. Когда мы добавляем текст с этим флагом, установленным в true,
// он будет отформатирован с использованием набора настроек шрифта справа налево.
builder.Font.Bidi = true;
builder.Write("مرحبًا");

// Установите флаг в false, а затем добавьте текст слева направо.
// Конструктор документов отформатирует их, используя набор настроек шрифта слева направо.
builder.Font.Bidi = false;
builder.Write(" Hello world!");

doc.Save(ArtifactsDir + "Font.Bidi.docx");
```

### Смотрите также

* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


