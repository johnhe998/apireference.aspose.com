---
title: XmlMapping.PrefixMappings
second_title: Справочник по API Aspose.Words для .NET
description: XmlMapping свойство. Возвращает сопоставления префиксов пространств имен XML для оценкиXPath .
type: docs
weight: 30
url: /ru/net/aspose.words.markup/xmlmapping/prefixmappings/
---
## XmlMapping.PrefixMappings property

Возвращает сопоставления префиксов пространств имен XML для оценки[`XPath`](../xpath/) .

```csharp
public string PrefixMappings { get; }
```

### Примечания

Указывает набор сопоставлений префиксов, которые должны использоваться для интерпретации выражения XPath , когда выражение XPath оценивается по сравнению с пользовательскими частями данных XML в документе.

### Примеры

Показывает, как установить сопоставления XML для пользовательских частей XML.

```csharp
Document doc = new Document();

// Создайте часть XML, содержащую текст, и добавьте ее в коллекцию CustomXmlPart документа.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

Assert.AreEqual("<root><text>Text element #1</text><text>Text element #2</text></root>", 
    Encoding.UTF8.GetString(xmlPart.Data));

// Создайте тег структурированного документа, который будет отображать содержимое нашего CustomXmlPart.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);

// Установить сопоставление для нашего тега структурированного документа. Это сопоставление будет инструктировать
// тег нашего структурированного документа для отображения части текстового содержимого части XML, на которую указывает XPath.
// В данном случае это будет содержимое второго "<text>" элемент первого "<root>" element: "Текстовый элемент #2".
tag.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", "xmlns:ns='http://www.w3.org/2001/XMLSchema'");

Assert.True(tag.XmlMapping.IsMapped);
Assert.AreEqual(xmlPart, tag.XmlMapping.CustomXmlPart);
Assert.AreEqual("/root[1]/text[2]", tag.XmlMapping.XPath);
Assert.AreEqual("xmlns:ns='http://www.w3.org/2001/XMLSchema'", tag.XmlMapping.PrefixMappings);

// Добавьте тег структурированного документа в документ, чтобы отобразить содержимое из нашей пользовательской части.
doc.FirstSection.Body.AppendChild(tag);
doc.Save(ArtifactsDir + "StructuredDocumentTag.XmlMapping.docx");
```

### Смотрите также

* class [XmlMapping](../)
* пространство имен [Aspose.Words.Markup](../../xmlmapping/)
* сборка [Aspose.Words](../../../)


