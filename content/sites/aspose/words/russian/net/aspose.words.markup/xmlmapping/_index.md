---
title: Class XmlMapping
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Markup.XmlMapping сорт. Определяет информацию которая используется для установления соответствия между тегом структурированного документа parent и элементом XML хранящимся в пользовательской части данных XML в документе.
type: docs
weight: 3860
url: /ru/net/aspose.words.markup/xmlmapping/
---
## XmlMapping class

Определяет информацию, которая используется для установления соответствия между тегом структурированного документа parent и элементом XML, хранящимся в пользовательской части данных XML в документе.

```csharp
public class XmlMapping
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [CustomXmlPart](../../aspose.words.markup/xmlmapping/customxmlpart/) { get; } | Возвращает пользовательскую часть данных XML, с которой сопоставлен тег родительского структурированного документа. |
| [IsMapped](../../aspose.words.markup/xmlmapping/ismapped/) { get; } | Возвращает **истинный** если тег родительского структурированного документа успешно сопоставлен с данными XML. |
| [PrefixMappings](../../aspose.words.markup/xmlmapping/prefixmappings/) { get; } | Возвращает сопоставления префиксов пространств имен XML для оценки[`XPath`](./xpath/) . |
| [StoreItemId](../../aspose.words.markup/xmlmapping/storeitemid/) { get; } | Указывает идентификатор пользовательских данных XML для пользовательской части данных XML, которая должна использоваться для оценки[`XPath`](./xpath/) выражение. |
| [XPath](../../aspose.words.markup/xmlmapping/xpath/) { get; } | Возвращает выражение XPath, которое оценивается для поиска пользовательского узла XML node , сопоставленного с тегом родительского структурированного документа. |

## Методы

| Имя | Описание |
| --- | --- |
| [Delete](../../aspose.words.markup/xmlmapping/delete/)() | Удаляет сопоставление родительского структурированного документа с данными XML. |
| [SetMapping](../../aspose.words.markup/xmlmapping/setmapping/)(CustomXmlPart, string, string) | Задает сопоставление между тегом родительского структурированного документа и узлом XML пользовательской части данных XML. |

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

* пространство имен [Aspose.Words.Markup](../../aspose.words.markup/)
* сборка [Aspose.Words](../../)


