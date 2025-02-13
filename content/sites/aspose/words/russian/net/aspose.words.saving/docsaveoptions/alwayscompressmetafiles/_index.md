---
title: DocSaveOptions.AlwaysCompressMetafiles
second_title: Справочник по API Aspose.Words для .NET
description: DocSaveOptions свойство. КогдаЛОЖЬ  небольшие метафайлы не сжимаются из соображений производительности. Значение по умолчанию истинный  все метафайлы сжимаются независимо от их размера.
type: docs
weight: 20
url: /ru/net/aspose.words.saving/docsaveoptions/alwayscompressmetafiles/
---
## DocSaveOptions.AlwaysCompressMetafiles property

Когда`ЛОЖЬ` , небольшие метафайлы не сжимаются из соображений производительности. Значение по умолчанию: **истинный** , все метафайлы сжимаются независимо от их размера.

```csharp
public bool AlwaysCompressMetafiles { get; set; }
```

### Примеры

Показывает, как изменить сжатие метафайлов в документе при сохранении.

```csharp
// Откройте документ, содержащий формулу Microsoft Equation 3.0.
Document doc = new Document(MyDir + "Microsoft equation object.docx");

// Когда мы сохраняем документ, метафайлы меньшего размера не сжимаются из соображений производительности.
// Мы можем установить флаг в объекте SaveOptions для сжатия каждого метафайла при сохранении.
// Некоторые редакторы, такие как LibreOffice, не могут читать несжатые метафайлы.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.AlwaysCompressMetafiles = compressAllMetafiles;

doc.Save(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx", saveOptions);

if (compressAllMetafiles)
    Assert.That(10000, Is.LessThan(new FileInfo(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx").Length));
else
    Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx").Length));
```

### Смотрите также

* class [DocSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../docsaveoptions/)
* сборка [Aspose.Words](../../../)


