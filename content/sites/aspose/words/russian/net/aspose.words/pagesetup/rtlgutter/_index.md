---
title: PageSetup.RtlGutter
second_title: Справочник по API Aspose.Words для .NET
description: PageSetup свойство. Получает или задает использует ли Microsoft Word промежутки для раздела на основе языка с письмом справа налево или языка с письмом слева направо.
type: docs
weight: 370
url: /ru/net/aspose.words/pagesetup/rtlgutter/
---
## PageSetup.RtlGutter property

Получает или задает, использует ли Microsoft Word промежутки для раздела на основе языка с письмом справа налево или языка с письмом слева направо.

```csharp
public bool RtlGutter { get; set; }
```

### Примеры

Показывает, как установить поля желоба.

```csharp
Document doc = new Document();

// Вставляем текст, занимающий несколько страниц.
DocumentBuilder builder = new DocumentBuilder(doc);
for (int i = 0; i < 6; i++)
{
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                  "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
    builder.InsertBreak(BreakType.PageBreak);
}

// Желоб добавляет пробелы к левому или правому полю страницы,
// что компенсирует сгибание страниц по центру в книге, вторгающееся в макет страницы.
PageSetup pageSetup = doc.Sections[0].PageSetup;

 // Определяем, сколько места на наших страницах есть для текста на полях, а затем добавляем количество для заполнения поля.
Assert.AreEqual(470.30d, pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin, 0.01d);

pageSetup.Gutter = 100.0d;

// Установите для свойства "RtlGutter" значение "true", чтобы поместить поле в более подходящее положение для текста, написанного справа налево.
pageSetup.RtlGutter = true;

// Установите для свойства "MultiplePages" значение "MultiplePagesType.MirrorMargins" для чередования
// положение полей слева/справа на каждой странице.
pageSetup.MultiplePages = MultiplePagesType.MirrorMargins;

doc.Save(ArtifactsDir + "PageSetup.Gutter.docx");
```

### Смотрите также

* class [PageSetup](../)
* пространство имен [Aspose.Words](../../pagesetup/)
* сборка [Aspose.Words](../../../)


