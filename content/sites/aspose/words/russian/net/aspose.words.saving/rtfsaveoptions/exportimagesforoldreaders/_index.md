---
title: RtfSaveOptions.ExportImagesForOldReaders
second_title: Справочник по API Aspose.Words для .NET
description: RtfSaveOptions свойство. Указывает записываются ли ключевые слова для старых читателей в RTF или нет. Это может существенно повлиять на размер документа RTF. Значение по умолчаниюистинный .
type: docs
weight: 30
url: /ru/net/aspose.words.saving/rtfsaveoptions/exportimagesforoldreaders/
---
## RtfSaveOptions.ExportImagesForOldReaders property

Указывает, записываются ли ключевые слова для «старых читателей» в RTF или нет. Это может существенно повлиять на размер документа RTF. Значение по умолчанию:`истинный` .

```csharp
public bool ExportImagesForOldReaders { get; set; }
```

### Примечания

«Старые программы чтения» — это приложения, выпущенные до Microsoft Word 97, а также WordPad. Если этот параметр установлен`истинный` Aspose.Words записывает дополнительные ключевые слова RTF. Эти ключевые слова позволяют корректно отображать документ при открытии в "старом" приложении для чтения, но могут значительно увеличить размер документа.

Если вы установите этот параметр на`ЛОЖЬ`, то в "старых ридерах" будут отображаться только изображения в форматах WMF, EMF и BMP .

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


