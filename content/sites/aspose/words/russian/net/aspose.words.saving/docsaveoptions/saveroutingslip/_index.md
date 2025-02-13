---
title: DocSaveOptions.SaveRoutingSlip
second_title: Справочник по API Aspose.Words для .NET
description: DocSaveOptions свойство. КогдаЛОЖЬ  данные RoutingSlip не сохраняются в выходной документ. Значение по умолчанию истинный .
type: docs
weight: 60
url: /ru/net/aspose.words.saving/docsaveoptions/saveroutingslip/
---
## DocSaveOptions.SaveRoutingSlip property

Когда`ЛОЖЬ` , данные RoutingSlip не сохраняются в выходной документ. Значение по умолчанию: **истинный** .

```csharp
public bool SaveRoutingSlip { get; set; }
```

### Примеры

Показывает, как установить параметры сохранения для старых форматов Microsoft Word.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Hello world!");

DocSaveOptions options = new DocSaveOptions(SaveFormat.Doc);

// Установите пароль, который защитит загрузку документа Microsoft Word или Aspose.Words.
// Обратите внимание, что это никоим образом не шифрует содержимое документа.
options.Password = "MyPassword";

// Если документ содержит маршрутный лист, мы можем сохранить его при сохранении, установив для этого флага значение true.
options.SaveRoutingSlip = true;

doc.Save(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc", options);

// Чтобы иметь возможность загрузить документ,
// нам нужно будет применить пароль, который мы указали в объекте DocSaveOptions, в объекте LoadOptions.
Assert.Throws<IncorrectPasswordException>(() => doc = new Document(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc"));

LoadOptions loadOptions = new LoadOptions("MyPassword");
doc = new Document(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc", loadOptions);

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Смотрите также

* class [DocSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../docsaveoptions/)
* сборка [Aspose.Words](../../../)


