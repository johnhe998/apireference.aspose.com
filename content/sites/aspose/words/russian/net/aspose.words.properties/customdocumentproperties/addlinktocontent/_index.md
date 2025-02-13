---
title: CustomDocumentProperties.AddLinkToContent
second_title: Справочник по API Aspose.Words для .NET
description: CustomDocumentProperties метод. Создает новое настраиваемое свойство документа связанное с содержимым.
type: docs
weight: 20
url: /ru/net/aspose.words.properties/customdocumentproperties/addlinktocontent/
---
## CustomDocumentProperties.AddLinkToContent method

Создает новое настраиваемое свойство документа, связанное с содержимым.

```csharp
public DocumentProperty AddLinkToContent(string name, string linkSource)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| name | String | Имя свойства. |
| linkSource | String | Источник имущества. |

### Возвращаемое значение

Вновь созданный объект свойства или null, если linkSource недействителен.

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

* class [DocumentProperty](../../documentproperty/)
* class [CustomDocumentProperties](../)
* пространство имен [Aspose.Words.Properties](../../customdocumentproperties/)
* сборка [Aspose.Words](../../../)


