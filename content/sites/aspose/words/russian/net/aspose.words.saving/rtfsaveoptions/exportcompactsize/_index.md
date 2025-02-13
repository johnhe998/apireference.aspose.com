---
title: RtfSaveOptions.ExportCompactSize
second_title: Справочник по API Aspose.Words для .NET
description: RtfSaveOptions свойство. Позволяет уменьшить размер выходных RTFдокументов но если они содержат RTL справа налево текст он не будет отображаться корректно. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 20
url: /ru/net/aspose.words.saving/rtfsaveoptions/exportcompactsize/
---
## RtfSaveOptions.ExportCompactSize property

Позволяет уменьшить размер выходных RTF-документов, но если они содержат RTL (справа налево) текст, он не будет отображаться корректно. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool ExportCompactSize { get; set; }
```

### Примечания

Если документ, который вы хотите преобразовать в RTF с помощью Aspose.Words, не содержит текста с написанием справа налево на таких языках, как арабский, вы можете установить для этого параметра значение`истинный` , чтобы уменьшить размер результирующего файла RTF.

### Примеры

Показывает, как сохранить документ в формате .rtf с пользовательскими параметрами.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Создайте объект «RtfSaveOptions», чтобы передать его методу «Сохранить» документа, чтобы изменить способ его сохранения в формате RTF.
RtfSaveOptions options = new RtfSaveOptions();

Assert.AreEqual(SaveFormat.Rtf, options.SaveFormat);

// Установите для свойства "ExportCompactSize" значение "true", чтобы
// уменьшить размер сохраненного документа за счет совместимости текста справа налево.
options.ExportCompactSize = true;

// Установите для свойства «ExportImagesFotOldReaders» значение «true», чтобы использовать дополнительные ключевые слова, чтобы убедиться, что наш документ
// совместим с программами чтения до Microsoft Word 97 и WordPad.
// Установите для свойства «ExportImagesFotOldReaders» значение «false», чтобы уменьшить размер документа,
// но препятствуют тому, чтобы старые читатели могли читать любые неметафайловые или BMP-изображения, которые могут содержаться в документе.
options.ExportImagesForOldReaders = exportImagesForOldReaders;

doc.Save(ArtifactsDir + "RtfSaveOptions.ExportImages.rtf", options);
```

### Смотрите также

* class [RtfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../rtfsaveoptions/)
* сборка [Aspose.Words](../../../)


