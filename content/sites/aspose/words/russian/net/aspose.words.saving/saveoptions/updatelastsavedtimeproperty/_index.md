---
title: SaveOptions.UpdateLastSavedTimeProperty
second_title: Справочник по API Aspose.Words для .NET
description: SaveOptions свойство. Получает или задает значение определяющееLastSavedTime свойство обновляется перед сохранением.
type: docs
weight: 190
url: /ru/net/aspose.words.saving/saveoptions/updatelastsavedtimeproperty/
---
## SaveOptions.UpdateLastSavedTimeProperty property

Получает или задает значение, определяющее,[`LastSavedTime`](../../../aspose.words.properties/builtindocumentproperties/lastsavedtime/) свойство обновляется перед сохранением.

```csharp
public bool UpdateLastSavedTimeProperty { get; set; }
```

### Примеры

Показывает, как определить, следует ли сохранять свойство документа «Время последнего сохранения» при сохранении.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(new DateTime(2021, 5, 11, 6, 32, 0), 
    doc.BuiltInDocumentProperties.LastSavedTime);

// Когда мы сохраняем документ в формате OOXML, мы можем создать объект OoxmlSaveOptions
// и затем передаем его в метод сохранения документа, чтобы изменить способ сохранения документа.
// Установите для свойства «UpdateLastSavedTimeProperty» значение «true», чтобы
// установить встроенное свойство выходного документа «Время последнего сохранения» на текущую дату/время.
// Установите для свойства "UpdateLastSavedTimeProperty" значение "false", чтобы
// сохранить исходное значение встроенного свойства входного документа "Время последнего сохранения".
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.UpdateLastSavedTimeProperty = updateLastSavedTimeProperty;

doc.Save(ArtifactsDir + "OoxmlSaveOptions.LastSavedTime.docx", saveOptions);

doc = new Document(ArtifactsDir + "OoxmlSaveOptions.LastSavedTime.docx");
DateTime lastSavedTimeNew = doc.BuiltInDocumentProperties.LastSavedTime;

if (updateLastSavedTimeProperty)
    Assert.That(DateTime.Now, Is.EqualTo(lastSavedTimeNew).Within(1).Days);
else
    Assert.AreEqual(new DateTime(2021, 5, 11, 6, 32, 0), 
        lastSavedTimeNew);
```

### Смотрите также

* class [SaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../saveoptions/)
* сборка [Aspose.Words](../../../)


