---
title: PlainTextDocument.CustomDocumentProperties
second_title: Справочник по API Aspose.Words для .NET
description: PlainTextDocument свойство. получаетCustomDocumentProperties документа.
type: docs
weight: 30
url: /ru/net/aspose.words/plaintextdocument/customdocumentproperties/
---
## PlainTextDocument.CustomDocumentProperties property

получает`CustomDocumentProperties` документа.

```csharp
public CustomDocumentProperties CustomDocumentProperties { get; }
```

### Примеры

Показывает, как загрузить содержимое документа Microsoft Word в виде обычного текста, а затем получить доступ к пользовательским свойствам исходного документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
doc.CustomDocumentProperties.Add("Location of writing", "123 Main St, London, UK");

doc.Save(ArtifactsDir + "PlainTextDocument.CustomDocumentProperties.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.CustomDocumentProperties.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
Assert.AreEqual("123 Main St, London, UK", plaintext.CustomDocumentProperties["Location of writing"].Value);
```

### Смотрите также

* class [CustomDocumentProperties](../../../aspose.words.properties/customdocumentproperties/)
* class [PlainTextDocument](../)
* пространство имен [Aspose.Words](../../plaintextdocument/)
* сборка [Aspose.Words](../../../)


