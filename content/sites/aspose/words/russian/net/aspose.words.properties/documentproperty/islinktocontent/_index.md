---
title: DocumentProperty.IsLinkToContent
second_title: Справочник по API Aspose.Words для .NET
description: DocumentProperty свойство. Показывает связано ли это свойство с контентом или нет.
type: docs
weight: 10
url: /ru/net/aspose.words.properties/documentproperty/islinktocontent/
---
## DocumentProperty.IsLinkToContent property

Показывает, связано ли это свойство с контентом или нет.

```csharp
public bool IsLinkToContent { get; }
```

### Примеры

Показывает, как связать пользовательское свойство документа с закладкой.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("MyBookmark");
builder.Write("Hello world!");
builder.EndBookmark("MyBookmark");

// Связать новое пользовательское свойство с закладкой. Стоимость этого свойства
// будет содержимым закладки, на которую он ссылается в элементе «LinkSource».
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");

Assert.AreEqual(true, customProperty.IsLinkToContent);
Assert.AreEqual("MyBookmark", customProperty.LinkSource);
Assert.AreEqual("Hello world!", customProperty.Value);

doc.Save(ArtifactsDir + "DocumentProperties.LinkCustomDocumentPropertiesToBookmark.docx");
```

### Смотрите также

* class [DocumentProperty](../)
* пространство имен [Aspose.Words.Properties](../../documentproperty/)
* сборка [Aspose.Words](../../../)


